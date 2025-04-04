# 1. 资源
- Improving Retrieval for RAG based Question Answering Models on Financial Documents
- https://arxiv.org/pdf/2404.07221.pdf

# 2. 摘要

大型语言模型（LLMs）能否精准回复，很大程度上取决于输入内容的质量，尤其是在运用检索增强生成（RAG）技术时。RAG 通过选取最相关的文本片段来加强 LLMs 的查询基础。即便近年来 LLMs 的回复质量有了显著提升，用户偶尔仍会碰到错误或不相关的信息，这通常是由于 RAG 在文本片段检索上的不足，而非 LLMs 本身的问题。因此，精炼 RAG 流程对于提升 LLMs 的效果非常关键。本文分析了 RAG 操作链的局限性，并提出了提升文本检索效率的方法。文章探讨了先进分块技术、查询扩展、加入元数据注释、应用重新排序算法和调整嵌入算法等策略。通过这些策略的实施，可以显著提高检索的准确性，进而增强 LLMs 在处理和回应问题时的整体表现和信赖度。

![](.02_金融文档优化RAG系统_images/结构.png)

# 3. 当前RAG流程的缺陷和不足
RAG目前和Agent应用一样，是大语言模型最火的应用领域之一，但是目前主流的RAG架构在处理知识密集型和特定领域的问答务时仍然有很多缺陷和不足。

• 均等分割问答的不足： RAG流程通常将文档均等分割，这样切分忽视了文档的结构和内容。这种分割方式虽然简单，却可能导致关键信息的遗漏。例如，如果问题的答案分布在几个语义上不相似的段落中，传统的RAG流程可能无法准确抓取相关信息。

• 余弦相似度的缺陷： RAG的核心机制之一是通过余弦相似性进行语义搜索，但这一方法也存在问题，比如可能检索到不相关或相反的信息，这反映了模型对语言细微差别的敏感性及意外结果的出现。最相似的文本块并非总是最相关的，但许多RAG流程却基于这一假设进行操作。此外，标准的嵌入算法通常缺乏特定领域的知识，从而忽略了特定领域词汇或短语的细微差别。

• 多文档问答任务的不足： 在处理单一长文本作为知识库时，如书籍或文章，基本的块划分策略和相似性搜索可能会取得不错的效果。但在实际应用中，我们更希望与多种结构复杂的文档进行交流，如包含标题和表格的文档。当所有文本块被平等对待并输入到单一的向量数据库中时，重要的信息往往会丢失。例如，文档集可能是不同公司的财务报告，或者跨越多年的报告。文本块的位置不同，可能就不会包含关于公司信息或特定年份的指标数据，这可能导致提供的信息不准确或过时。

• 问题相似检索的不足： 传统的检索算法缺乏处理多个不同文档的高级问答所需的细微差别和推理能力。它们通常只是基于原始问题的相似性搜索，而不会像人类那样通过逻辑推理来找到相关信息。例如，财务分析师在计算某个指标时，会通过多步骤的逻辑推理过程来确定如何计算指标以及信息在文档中的具体位置。这种复杂性无法仅通过问题的相似性搜索来捕捉。查询本身可能并未提供足够的信息来指导模型找到最相关的文本块，而是需要更多的信息和逻辑推理。

# 4. 如何在金融领域提升RAG效果

## 4.1 如何处理文档分块

分块技术对于检索过程至关重要，因为它决定了算法返回的上下文内容和质量。不当的分块可能会导致提供的信息过多或不足。大多数RAG流程采用固定大小的分块，这可能无法适应不同查询的需求。理想的分块策略应当根据知识库中的文档特性和模型预期处理的查询长度来定制。

递归分块是一种更为灵活的策略，它利用标点等语言特征来动态调整分块。这种方法虽然保持了块的大致均等大小，但通过额外的参数确保了文本不会被不当地切割，例如，避免了在句中切割。借助Spacy和NLTK等Python库，我们可以采用更高级的句子分割技术，这些技术利用自然语言处理来更好地理解文档上下文。

在处理财务报告时，这些文档通常篇幅较长，并包含复杂的结构，如表格。类似性质的文档，比如10-k报告，通常遵循一定的格式，其结构可以通过文档的标题和副标题来标识。鉴于财务报告的特殊性，采用考虑这些特点的基于元素的分块方法，可以进一步提升检索的准确性。这篇论文中，作者探讨Unstructured论文中的策略：

当遇到标题元素时，就开始一个新的块；当遇到表格元素时，也启动新块，并保留整个表格。这样的策略确保了每个上下文都能提供恰当的信息量，以有效解答用户的疑问。

## 4.2 如何做查询扩展

查询扩展或查询转换指的是对输入RAG流程的问题进行改造，以便不仅仅根据用户最初的问题来寻找相关的信息块。这是因为用户的问题有时候并不包含足够的信息来明确指导算法在文档中寻找上下文，尤其是在采用余弦相似性搜索时。有时候，仅凭用户的问题可能会误导算法，使其搜索到错误的信息块。在处理更复杂的问题和文档时，需要更多的逻辑推理步骤来确定搜索的位置，而标准的RAG流程在这方面存在不足。

为了模拟人类分析师在检索时可能采用的逻辑，可以采用假设文档嵌入（HyDE）技术。与传统的仅使用用户原始问题进行相似性搜索不同，HyDE利用LLM生成一个假设性的文档，然后结合原始问题和这个假设性的答案进行搜索。这种技术已经证明能够超越传统的检索器，并且不需要定制的嵌入算法，但有时也可能因为依赖另一个LLM来提供额外上下文而得出错误的结果。

## 4.3 元数据标注与索引优化

在处理众多文档的交互时，传统的检索算法可能会错失元数据中的重要数据点。我们之前尝试与多个文档进行互动时遇到的问题是，标准的RAG流程容易将不同文档的区块混淆。为了解决这一问题，我们为每个文档建立了独立的向量数据库。但这在大规模应用中并不实用，尤其是当用户需要在多个文档间切换或同时与多个文档互动时。元数据标注是一种有效的方法，它能够帮助我们跨越这一障碍，进一步提升信息检索的精确度。

在进行元数据标注时，应结合分块策略进行考虑。比如，我们会根据文档的元素进行分块，因此可以在标注中加入关于每个元素的详细信息。例如，如果一个表格被单独作为一个区块，元数据可以指明这是一个什么类型的表格（如损益表、现金流量表等）。此外，为了提供更多的上下文信息，通常还会在元数据标注中添加摘要和关键词。

## 4.4 重排序策略

在使用传统的RAG流程时，我们可以设定算法返回的文档或数据块的数量，从而决定提供多少数据块作为查询的上下文。通常情况下，最靠前的1或2个数据块会被纳入上下文，它们是基于余弦相似度或k-最近邻搜索得到的结果。然而，这种方法虽然能找到最相似的数据块，但这些数据块未必是最相关的上下文信息。

重新排序策略是一种将数据块的相关性置于相似度之上的方法。简单来说，余弦相似度等方法可能会对前10个最相似的数据块进行排序，但另一个独立的算法会根据相关性对这些数据块重新排序，之后选择重排后最前面的一两个数据块作为输入查询的上下文。

## 4.5 微调Embedding算法

嵌入算法负责将文本转换为数学表达，在RAG流程中的关键步骤。通过利用领域特定的知识对嵌入算法进行优化，可以提升在特定领域内的检索效率。Embedding表示还可以是动态的，能够根据上下文的微妙变化调整词义。例如，OpenAI提供的嵌入表示就能够依据上下文的变化而相应调整。不过，要进行领域特定的模型微调，就需要包含查询、文本语料及领域相关文档的综合数据集。

# 5. 如何测评RAG系统

在评价RAG系统性能时，主要关注模型在检索相关上下文的准确性以及根据上下文回答问题的能力。金融分析师提供的、作为真实答案基准的上下文和答案。将模型的输出与这些真实答案进行比较称为结构化评估；

若无真实答案作为基准，则称为非结构化评估。尽管结构化评估在确定模型精确度方面更为可靠，非结构化评估也能帮助我们评价块和答案的质量，尤其是在大多数实际情况下，我们无法获取真实答案时。

## 5.1 检索质量
在结构化数据中，评估检索质量的主要方法是检验页面级别和段落级别的准确度。由于我们可以访问完整的文档和分析师引用的部分，我们会将这部分内容与检索算法返回的数据块进行比较。如果引用的上下文和算法检索的上下文位于同一页，那么检索准确度就很高；段落级别的准确度也是基于相似的逻辑。

在非结构化数据中，我们依据RAGAS框架定义的上下文相关性来评价检索到的数据块。这个指标要求LLM统计上下文中与问题回答相关的句子数目。上下文中提取出的相关句子数量与总句子数的比例，被称为上下文相关性得分。这个得分机制旨在减少重复信息的权重，同时奖励那些大多数句子都能提供有用信息以回答问题的数据块。

## 5.2 大语言模型回答的准确性
在结构化评估中，我们通过比较模型生成的答案与数据集中的真实答案来评估其准确性。我们采用的标准评价指标包括BLEU、Rouge-L得分和余弦相似度。但这些指标并不擅长比较两个不同答案的语义内容，有时可能会产生误导。因此，我们还采用了一种特定的LLM评估方法，通过特定的提示让模型（如GPT4）自行评估候选答案相对于真实答案的准确性。

我们还可以采用非结构化的方法来评估生成器的答案质量与检索到的上下文之间的关系。RAGAS框架提供的答案忠实度指标可以衡量模型答案与上下文的契合程度，通过计算答案中由上下文支持的陈述数与答案中总句子数的比值来得出。这个得分也可以用来评估模型是否在没有真实答案作为参考的情况下虚构信息。高得分表明生成的答案几乎完全基于上下文，即模型没有添加任何文档之外的额外信息。

# 参考

[1] 如何针对金融文档优化RAG系统，https://mp.weixin.qq.com/s/ieyjFp0oQc1nIDm_EagUHg
