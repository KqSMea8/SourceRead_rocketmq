# 专业术语

* **Producer**

消息生产者，负责产生消息，一般由业务系统负责产生消息。

* **Consumer**

消息消费者，负责消费消息，一般是后台系统负责异步消费。

* **Push Consumer**
* **Pull Consumer**
* **Producer Group**

一类Producer的集合名称，这类Producer通常发送一类消息，且发送逻辑一致。

* **Consumer Group**

一类Consumer的集合名称，这类Consumer通常消费一类消息，且消费逻辑一致。

* **Broker**

消息中转角色，负责存储消息，转发消息，一般也称为Server。在JMS规范中称为Provider。

* **广播消费**

一条消息被多个Consumer消费，即使这些Consumer属于同一个Consumer Group，消息也会被Consumer Group中的每个Consumer都消费一次，广播消费中的Consumer Group概念可以认为在消息划分方面无意义。

在CORBA Notification规范中，消费方式都属于广播消费。

* **集群消费**

一个Consumer Group中的Consumer实例平均分摊消费消息。例如某个Topic有9条消息，其中一个Consumer Group有3个实例（可能是3个进程，或者3台机器），那么每个实例只消费其中的3条消息。

* **主动消费**

Consumer主动向Broker发起获取消息请求，控制权完全在于Consumer应用。

类似于JMS规范中描述的Synchronously方式消费、CORBA规范中的PullConsumer。

* **被动消费**

Consumer注册一个Callback接口，由RocketMQ后台自动从Broker接收消息，并回调Callback接口。

类似于JMS规范中的描述的Asynchronously方式消费、CORBA规范中的PushConsumer。

* **顺序消息**

消费消息的顺序要同发送消息的顺序一致，在RocketMQ中，主要指的是局部顺序，即一类消息为满足顺序性，必须Producer单线程顺序发送，且发送到同一个队列，这样Consumer就可以按照Producer发送的顺序去消费消息。

* **普通顺序消息**

顺序消息的一种，正常情况下可以保证完全的顺序消息，但是一旦发生通信异常，Broker重启，由于队列总数发生变化，哈希取模后定位的队列会变化，产生短暂的消息顺序不一致。

如果业务能容忍在集群异常情况（如某个Broker宕机或者重启）下，消息短暂的乱序，使用普通顺序方式比较合适。

* **严格顺序消息**

顺序消息的一种，无论正常异常情况都能保证顺序，但是牺牲了分布式Failover特性。如果服务器部署为同步双写模式，此缺陷可通过备机自动切换为主避免，不过仍然会存在几分钟的服务不可用。

* **Message Queue**

在RocketMQ中，所有消息队列都是持久化，长度无限的数据结构，所谓长度无限是指队列中的每个存储单元都是定长，访问其中的存储单元使用Offset来访问，offset为java long类型，64位，理论上在100年内不会溢出，所以认为是长度无限，另外队列中只保存最近几天的数据，之前的数据会按照过期时间来删除。

在Metaq2.x之前版本，队列也称为“**分区**”，两者描述的是一个概念。但是按照2.x的实现，使用队列描述更合适。

