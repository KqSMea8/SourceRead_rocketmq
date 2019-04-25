# 分布式事务

已知的几个分布式事务规范，如XA，JTA等。其中XA规范被各大数据库厂商广泛支持，如Oracle，Mysql等。其中XA的TM实现佼佼者如Oracle Tuxedo，在金融、电信等领域被广泛应用。

RocketMQ的存储结构是文件记录形式，通过Offset递增进行访问数据，缺乏KV存储具有的update能力，如果要支持事务，必须引入类似于KV存储的模块才可以。

RocketMQ目前不支持分布式事务。

