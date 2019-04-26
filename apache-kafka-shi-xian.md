# Apache Kafka实现

      Apache Kafka is a distributed publish-subscribe messaging system. It is designed to support the following.

* Persistent messaging with O\(1\) disk structures that provide constant time performance even with many TB of stored messages.
* High-throughput: even with very modest hardware Kafka can support hundreds of thousands of messages per second.
* Explicit support for partitioning messages over Kafka servers and distributing consumption over a cluster of consumer machines while maintaining per-partition ordering semantics.
* Support for parallel data load into Hadoop.

Kafka provides a publish-subscribe solution that can handle all activity stream data and processing on a consumer-scale web site. This kind of activity \(page views, searches, and other user actions\) are a key ingredient in many of the social feature on the modern web. This data is typically handled by "logging" and ad hoc log aggregation solutions due to the throughput requirements. This kind of ad hoc solution is a viable solution to providing logging data to an offline analysis system like Hadoop, but is very limiting for building real-time processing. Kafka aims to unify offline and online processing by providing a mechanism for parallel load into Hadoop as well as the ability to partition real-time consumption over a cluster of machines.

The use for activity stream processing makes Kafka comparable to Facebook's Scribe or Apache Flume \(incubating\), though the architecture and primitives are very different for these systems and make Kafka more comparable to a traditional messaging system. See our design page for more details.

以上文字摘自Apache Kafka官方网站，Kafka详细资料，请参照官方网站，此文不再详述。

[http://kafka.apache.org/](http://kafka.apache.org/)

Kafka是一个实现非常特别的消息中间件，同我们的典型实现区别较大，跳出了各种消息中间件规范定义的思维模式，按照我的理解总结如下：

1. Kafka的设计初衷消息是面向堆积需求的，读优先级高于写优先级，优先为读消息准备，所以无论堆积的消息多少，消费能力都很强。（前提是分区数在一定范围内）
2. Kafka是面向广播消费类型的，对广播支持友好，并且也支持集群消费模式。
3. 不维护单个消息的消费状态，无论是否消费，只要超过保留时间就删除。
4. 分区数是一个重要的功能、性能指标，分区数支持过少会影响消费的并行度，以及单机能支持的topic数。
5. 很适合日志收集类应用。

