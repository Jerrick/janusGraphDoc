# 第一节 JanusGraph的优点

JanusGraph主要是为了满足海量图数据的存储和处理而设计，针对图数据的实时遍历和分析查询是JanusGraph的主要优势。
本节将讨论JanusGraph及其持久化方案的各种特定优势。

## 1.1. JanusGraph的常见优点

* 支持大图，JanusGraph支持横向扩展，存储能力与集群中的机器数量成比例。
* 支持高并发事务和图计算。 JanusGraph的事务处理能力随着集群中的机器数量而变化，在巨大的图上的复杂遍历查询可以在毫秒级响应。
* 通过Hadoop支持全局图分析和批量图处理。
* 在非常大的图上可以支持地理、数字区间和全文搜索顶点和边。
* 支持Apache TinkerPop的属性图模型。
* 支持图形遍历语言Gremlin。
* 集成了Gremlin Server，支持不同编程语言的连接。
* 多种图形级别的配置，轻松进行性能调优。
* 以顶点为中心的索引提供了顶点级别的查询来缓解臭名昭着的超级节点问题。
* 优化磁盘以便提高存储效率和访问速度。
* 基于Apache 2 license开源，比较自由。

## 1.2. JanusGraph与Apache Cassandra结合的优点

* 高可用，没用单点故障问题。
* 因为没有Master/Slave架构，所以也不存在读写瓶颈。
* 弹性可扩展，允许引入和移除机器。
* 缓存层确保热数据在内存中可用。
* 通过向集群添加更多机器来增加缓存的大小。
* 与Apache Hadoop继承。
* 基于Apache 2 license开源。

## 1.3. JanusGraph与HBase结合的优点

* 与Apache Hadoop生态系统紧密集成。
* 原生支持强一致性。
* 线性可扩展。
* 严格一致的读写。
* 通过MapReduce处理HBase表有丰富的接口。
* 支持通过JMX导入监控指标。
* 基于Apache 2 license开源。


## 1.4. JanusGraph和CAP定理


在使用数据库时，应该充分考虑 [CAP定理](https://baike.baidu.com/item/CAP%E5%8E%9F%E5%88%99/5712863?fr=aladdin)（C=一致性，A=可用性，P=分区容错性）。 
JanusGraph可以支持三种后端存储：Apache Cassandra，Apache HBase和Oracle Berkeley DB(Java版)。 
需要注意的是BerkeleyDB(Java版)是一个非分布式数据库，通常仅用于测试或者研究中。

在CAP的选择上，HBase选择了CP，实现了强一致性，但是降低了可用性，RegionServer的故障会影响读写可用性； 
Cassandra更倾向于AP，基于Quorum Consistency，代价是读取时为了获取完整/正确结果时的read repair.

Cassandra可以通过配置支持差不多十种不同级别的一致性，“可以支持”但不意味着它擅长这些场景，原来的优势可能荡然无存。
HBase在高可用性方面也做了一些努力，如Region Replica特性，提升Read的高可用性，但会牺牲Read的一致性。

>特别感谢：毕杰山老师的指导

更多讨论请查看[cassandra与hbase的利弊分析？适用场景？社区环境？](https://www.zhihu.com/question/20152327)