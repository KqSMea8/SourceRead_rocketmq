# Broker的Buffer满了怎么办？

Broker的Buffer通常指的是Broker中一个队列的内存Buffer大小，这类Buffer通常大小有限，如果Buffer满了以后怎么办？

下面是CORBA Notification规范中处理方式：

1. RejectNewEvents

拒绝新来的消息，向Producer返回RejectNewEvents错误码。

1. 按照特定策略丢弃已有消息

**AnyOrder** - Any event may be discarded on overflow. This is the default setting for this

property.

**FifoOrder** - The first event received will be the first discarded.

**LifoOrder** - The last event received will be the first discarded.

**PriorityOrder** - Events should be discarded in priority order, such that lower priority

events will be discarded before higher priority events.

**DeadlineOrder** - Events should be discarded in the order of shortest expiry deadline first.

RocketMQ没有内存Buffer概念，RocketMQ的队列都是持久化磁盘，数据定期清除。

