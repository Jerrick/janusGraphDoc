# 第一节 JanusGraph的好处

JanusGraph是为了满足海量图数据的存储和处理而设计，针对图数据的实时遍历和分析查询是JanusGraph的基础优势。
本节将讨论JanusGraph及其持久性解决方案的各种特定优势。

## 1.1. JanusGraph的常见好处

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

## 1.2. JanusGraph与Apache Cassandra的好处
## 1.3. JanusGraph与HBase结合的好处
## 1.4. JanusGraph和CAP定理