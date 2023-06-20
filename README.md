# 通过langchain的llms类实现tigerbot-chatapi远程调用的方法

在langchain中提供了llms这个类，旨在让我们使用更多非langchain官方集成的大语言模型来处理业务。
tigerbot不仅提供了开源的大语言模型，同时也提供了模型api在线调用的方法。
这对本地硬件算力无法实现模型加载，又期望学习langchain框架的同学提供了很好的机会。

##这个例子都做了什么

首先我们来看下有关[llms](https://python.langchain.com/docs/modules/model_io/models/llms/how_to/custom_llm)这个类在langchain官方的解释：

如何编写自定义LLM包装器#
本笔记介绍如何创建自定义LLM包装器，以便您可以使用自己的LLM或与LangChain支持的不同包装器。

自定义LLM仅需要实现一件必需的事情：

一个 _call 方法，它接收一个字符串，一些可选的停用词，并返回一个字符串
它还可以实现第二个可选项：
一个 _identifying_params 属性，用于帮助打印该类。应该返回一个字典。


所以我们只需要在类中声明一个叫 _call 的方法，然后将chat对话的请求参数从方法中取出，交给云端tigerbot的chatapi处理之后，再将得到的请求返回中，data.result.[0]的内容返回。即可完成langchain中llms的定义了。

#需要注意的地方：

在使用之前，请先登陆[Tigerbot](https://www.tigerbot.com/)注册apikey。并将获得的apikey复制到代码中
API_KEY=''
↑将key写到此处。

然后在控制台中执行 
py tigerbot_chatapi.py
就可以直接输入问题，来测试效果了



           
