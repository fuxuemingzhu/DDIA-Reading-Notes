# DDIA-Reading-Notes

本仓库是《数据密集型应用系统设计》精华整理，字数为原书的 1/5 左右。图文并茂，适合阅读。

# 目录

 [**第一章：可靠性，可扩展性，可维护性**](chapter1.md) 

 [**第二章：数据模型与查询语言**](chapter2.md) 

 [**第三章：存储与检索**](chapter3.md) 

 [**第四章：数据编码与演化**](chapter4.md) 

 [**第五章：数据复制**](chapter5.md) 

 [**第六章：分区**](chapter6.md) 

 [**第七章：事务**](chapter7.md) 

 [**第八章：分布式系统的挑战**](chapter8.md) 

 [**第九章：一致性与共识**](chapter9.md) 

 [**第十章：批处理**](chapter10.md) 

 [**第十一章：流处理**](chapter11.md) 

 [**第十二章：数据系统的未来**](chapter12.md) 

更优雅的阅读方式：[《数据密集型应用系统设计》读书笔记](https://fuxuemingzhu.cn/ddia/)

# 推荐

**《数据密集型应用系统设计》**，英文名称是 **《Designing Data-Intensive Application》**  ，也被简称为 **DDIA**。
这是本神书，豆瓣评分高达 9.7 分。
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640422511100-c244e105-53f4-4716-b7ad-8581cb21218f.png)
这本书的适合所有后台开发工程师、大数据工程师，也很适合面试前复习系统设计的同学。

什么是「**数据密集型应用系统**」？

> 当数据（数据量、数据复杂度、数据变化速度）是一个应用的主要挑战，那么可以把这个应用称为数据密集型的。与之相对的是计算密集型——处理器速度是主要瓶颈。

其实我们平时遇到的大部分系统都是数据密集型的——应用代码访问内存、硬盘、数据库、消息队列中的数据，经过业务逻辑处理，再返回给用户。
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640422789721-bf3ea9ed-5bee-4f28-9292-56be953c8c28.png)

- 很多应用都是在解决不同场景下的数据存储和检索问题——**MySQL，Redis，HBase，Kafka，ElasticSearch……**
- 还有很多技术是围绕着数据展开——**索引，编码（JSON, XML, Thrift, ProtoBuffer），行列存储……**
- 当数据在分布式处理时，要考虑——**数据复制，分区，事务……**
- 大数据场景下，我们会使用——**MapReduce，Spark，Flink 等批处理、流处理框架。**

只要是个程序员，就肯定跟数据打过交道，也都或多或少对上述软件与技术有所了解。
我之前在阿里巴巴的主要工作就是处理数据，但我对数据相关的技术只是处于「看山是山」的阶段，远远没有达到融会贯通的地步。

当我们学知识的时候，往往都是分门别类地学：这本书讲 MySQL 的，那本书讲 Redis 的。**这种学习方法使知识割裂，很难让我们掌握不同的技术之间的区别和联系。**
在购物网站上搜「**数据库**」出来的基本都是某种数据库的用法。
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640447091871-955246e3-14bc-40be-9953-1aa3586ee7f9.png)
**《数据密集型应用系统设计》这本书，把所有跟「数据」有关的知识点做了剖析、整理、总结，从一个很高的层次把各项技术的共性和区别讲得透彻。** 当我们懂了底层原理之后，就明白了每项技术产生的背景是什么，解决了什么问题，有什么适用场景。

这本书既有理论也有实践，基本没有公式，图很多，阅读起来很流畅，比较容易理解。

这本书分为了三部分：

- 第一部分：**数据系统的基石**，包括数据模型与查询语言、存储与检索、数据编码与演化；
- 第二部分：**分布式数据**，包括复制、分片、事务、一致性与共识；
- 第三部分：**衍生数据**，包括批处理、流处理、数据系统的未来。

![数据密集型应用系统设计三部分.001.png](https://picture-bed-1251805293.file.myqcloud.com/1640481447408-d7fb792f-35b6-4809-87a5-e84a6271c76e.png)
第三章「存储与检索」真是精华，从一个最简单的数据库开始，越讲越深入，把常见数据库的存储与检索方式都讲完了。按照第三章的讲解，可以自己动手实现一个数据库，并且这个项目是能写到简历里面的。

我在读《数据密集型应用系统设计》的时候，一边读，一边做笔记。虽然读得比较慢，但是收获确实很多。这种神书根本就读不快啊！里面到处都是我从未看到过的知识点，只能一边读一边思考。

不过，**这时间花得值，解决了之前我对「数据」的理解只浮于表面、而没有深究的问题。**
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640422921278-c676e774-7ad2-45be-9346-70487aff6692.png)
强烈推荐《数据密集型应用系统设计》这本书！大家在阅读的同时也做好笔记，增加知识与大脑的「摩擦」可以记得更牢哦！

这个专栏，就是我的阅读笔记，我是把全书的内容重点摘抄了一遍。采用一问一答的形式，并且用列表形式整理了原文。
笔记的内容大概是原文的 1/5 ~ 1/3，所以你如果没有很多时间看书的话，看我的笔记也就够了！

# 阅读指南

这本书比较厚，概念也比较多，而且很少有代码，基本都是在讲逻辑，因此有些「**太干了**」。

我给出一些阅读的建议和资料，供大家参考。

## 阅读建议

首先，我强烈建议买书！中文版的翻译比开源翻译强很多。开源翻译的有很多错误，而且不符合阅读习惯。比如数据库中 「join 操作」，在开源翻译成了「连接操作」，而中文版的书里确实写的是「join 操作」。

在阅读中文版书籍的时候，也发现了书中的一处翻译错误，所以最好还是读英文版。

我在阅读的过程中，也参考了这本书的英文版，不得不说，英文原版是最流畅、最准确的！**有能力的同学都去读英文原版！**

推荐的阅读选择为 **《DDIA 英文版》 > 《数据密集型应用系统设计中文书籍》 > 开源翻译仓库**。

另外，这本书的内容大而多，每一章都可以成为一本单独的书。如果你时间精力有限，不妨阅读你感兴趣的重点章节。

- **如果你对数据的编码、存储感兴趣，可以阅读第 1~4 章；**
  - **这些是比较基础的内容，解密了数据库的原理，对工作比较有帮助**
- **如果你对分布式系统感兴趣（如分布式复制、分区、事务等），可以阅读第 5~9 章；**
  - **这部分内容比较偏向于概念和思维，挺抽象的，属于进阶内容，帮助拓展思维（和准备面试）。**
- **如果你对大数据计算（批处理、流处理）感兴趣，可以阅读第 10~12 章。**
  - **这部分内容工程实践比较强，如果你工作中用到了 Spark, Flink 等，可以在这些章节了解它们的原理**



**阅读这本书要什么前置知识吗？**

- 我觉得不需要哈，前 4 章还是比较通俗易懂的；分布式部分有点难理解，但是认真看也能看懂。
- 最好了解过一些基本的概念，比如哈希表、B+树、JSON、ProtoBuffer 等。

## 阅读资源

这是一些阅读资源：

- 《数据密集型应用系统设计》开源翻译仓库（9.3K star）：[https://github.com/Vonng/ddia](https://github.com/Vonng/ddia)
- 开源版本在线阅读：[https://vonng.gitbooks.io/ddia-cn/content/](https://vonng.gitbooks.io/ddia-cn/content/)
- 负雪明烛的读书笔记：[数据密集型应用系统设计](https://www.yuque.com/fuxuemingzhu/cdpqne?view=doc_embed)
- 《数据密集型应用系统设计》纸质书（翻译水平比开源在线阅读版好很多，**强烈建议买书**）：[京东购买链接](https://union-click.jd.com/jdc?e=&p=JF8BAMIJK1olXDYCV1tfDkwUBl9MRANLAjZbERscSkAJHTdNTwcKBlMdBgABFksUBm0OHFgQQl9HCANtcz9TdjBcE0F1HE57VzUCSQhgfmx-a1cZbQcyV19dDUkeAW4BEmslXQEyAjBdCUoWAm4MH14dbQcyVFlYCU4UAWsME1kQWDYFVFdt0c6528WTzPKqi7SoZG5tC3snM284GGtXMw4CBl1YW0IQAjtfTl4dCQJRXAxbAR5CBTwBTwwcXQ5RZFxcCU8eMw)

<img src="https://picture-bed-1251805293.file.myqcloud.com/1640423370576-4df0183f-c521-4bba-96c9-19bff3f684ac.png" alt="image.png" style="zoom:50%;" />

## 辅助资料

### ddia-references

这个仓库包含了《数据密集型应用系统设计》每章后面的所有参考文献对应的 pdf。
地址是：[https://github.com/ept/ddia-references](https://github.com/ept/ddia-references)
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1643010807665-03279e24-3792-4021-a2c0-39e683a97d5d.png)

### Book Review

这里有个很不错的 Book Review，是一个小哥讲了《DDIA》每一章的概述，作者很用心。
全英文的，在油管可以看到。地址是：
[https://www.youtube.com/watch?v=PdtlXdse7pw&list=PL4KdJM8LzAMecwInbBK5GJ3Anz-ts75RQ](https://www.youtube.com/watch?v=PdtlXdse7pw&list=PL4KdJM8LzAMecwInbBK5GJ3Anz-ts75RQ)

![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640427269497-f6ed35f7-26ee-48df-9c48-0a5ce4a98c86.png)

### MIT6.824

看这本书的时候，你可以结合 MIT6.824 分布式系统课程。油管上这门课程的视频版本，地址：
[https://www.youtube.com/channel/UC_7WrbZTCODu1o_kfUMq88g/videos](https://www.youtube.com/channel/UC_7WrbZTCODu1o_kfUMq88g/videos) 
![](https://picture-bed-1251805293.file.myqcloud.com/1640425227868-08c31709-4425-4266-8947-ce4398cee310.webp)
这门课程是全英文的，英文字幕。

在 B 站有这个课程的中文字幕翻译合集，地址：[https://www.bilibili.com/video/av91748150](https://www.bilibili.com/video/av91748150)
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640425390433-572cbfb5-f4d6-47f9-919c-00aebd7263b6.png)

这门课程的中文文字版，地址：[https://mit-public-courses-cn-translatio.gitbook.io/mit6-824/ ](https://mit-public-courses-cn-translatio.gitbook.io/mit6-824/ )
![](https://picture-bed-1251805293.file.myqcloud.com/1640425227842-c62b4372-e96e-4eac-9e97-5f958946258a.webp)

### 读书经验分享

找到了油管上的一个 DDIA 读书分享，大概讲了这本书每章节的主要内容。不过分享者的普通话不是太好，有兴趣可以看下，[https://www.youtube.com/watch?v=5G_JHHSvmS0](https://www.youtube.com/watch?v=5G_JHHSvmS0)
![image.png](https://picture-bed-1251805293.file.myqcloud.com/1640425712169-08344807-e200-45d1-b4dc-2b3d4d02ea11.png)

### 第三章辅助资料

第三章讲解数据存储与检索，我们常说的 mysql，leveldb 的基本原理都能在这里找到。

### 第五章辅助资料

这篇文章异地多活的文章，讲了分布式下怎么搞数据复制，能明显看出是参考《DDIA》写的。文章很不错，推荐阅读。

## 交流群

我组织了一个《DDIA 共读群》，大家在一起阅读打卡，交流经验。

进群之后，你可以获得：

1. 电子书、读书笔记、参考资料；
2. 和群友一起讨论；
3. 大咖直播讲解书中的内容；
4. 每天阅读打卡监督。

是付费群，起始价格是 10 元/永久，每满 50 人涨价 10 元，目前价格是 20 元。

如果想要进群交流的，可以加我微信：**fuxuemingzhu**，我拉你进群。





