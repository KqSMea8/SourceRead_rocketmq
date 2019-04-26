# RocketMQ是什么？

![RocketMQ&#x662F;&#x4EC0;&#x4E48;](.gitbook/assets/image%20%281%29.png)

是一个队列模型的消息中间件，具有高性能、高可靠、高实时、分布式特点。

* Producer、Consumer、队列都可以分布式。
* Producer向一些队列轮流发送消息，队列集合称为Topic，Consumer如果做广播消费，则一个consumer实例消费这个Topic对应的所有队列，如果做集群消费，则多个Consumer实例平均消费这个topic对应的队列集合。

