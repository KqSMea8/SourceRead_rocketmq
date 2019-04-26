# Message Filter

* Broker端消息过滤

在Broker中，按照Consumer的要求做过滤，优点是减少了对于Consumer无用消息的网络传输。

缺点是增加了Broker的负担，实现相对复杂。

1. 淘宝Notify支持多种过滤方式，包含直接按照消息类型过滤，灵活的语法表达式过滤，几乎可以满足最苛刻的过滤需求。
2. 淘宝RocketMQ只支持按照简单的消息类型过滤。
3. CORBA Notification规范中也支持灵活的语法表达式过滤。

* Consumer端消息过滤

这种过滤方式可由应用完全自定义实现， 但是缺点是很多无用的消息要传输到Consumer端。

