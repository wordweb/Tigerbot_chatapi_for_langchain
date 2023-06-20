# 通过langchain的llms类实现tigerbot-chatapi远程调用的方法

在langchain中提供了llms这个类，旨在让我们使用更多非langchain官方集成的大语言模型来处理业务。
tigerbot不仅提供了开源的大语言模型，同时也提供了模型api在线调用的方法。
这对本地硬件算力无法实现模型加载，又期望学习langchain框架的同学提供了很好的机会。

##这个例子都做了什么

首先我们来看下有关[llms](https://python.langchain.com/docs/modules/model_io/models/llms/how_to/custom_llm)这个类在langchain官方的解释：
