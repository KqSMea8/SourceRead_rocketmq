# RocketMQ存储特点

       RocketMQ 的消息持久化是基于文件系统，而从效率来看文件系统 &gt; kv 存储 &gt; 关系型数据库。那么，到底是如何存储的

（一）首先看下结构图

![&#x5B58;&#x50A8;&#x5C42;&#x7684;&#x6574;&#x4F53;&#x7ED3;&#x6784; ](.gitbook/assets/image%20%282%29.png)

（二）MappedFile 类   
 对于 commitlog、 consumequeue、 index 三类大文件进行磁盘读写操作，均是通过 MapedFile 类来完成。这个类相当于 MappedByteBuffer 的包装类。 

{% code-tabs %}
{% code-tabs-item title="主要成员变量" %}
```java
//默认页大小为4k
    public static final int OS_PAGE_SIZE = 1024 * 4;
    protected static final Logger log = LoggerFactory.getLogger(LoggerName.STORE_LOGGER_NAME);
    //JVM中映射的虚拟内存总大小  
    private static final AtomicLong TOTAL_MAPPED_VIRTUAL_MEMORY = new AtomicLong(0);
    //JVM中mmap的数量  
    private static final AtomicInteger TOTAL_MAPPED_FILES = new AtomicInteger(0);
    //当前写文件的位置
    protected final AtomicInteger wrotePosition = new AtomicInteger(0);
    //ADD BY ChenYang
    protected final AtomicInteger committedPosition = new AtomicInteger(0);
    private final AtomicInteger flushedPosition = new AtomicInteger(0);
    //映射文件的大小
    protected int fileSize;
    //映射的fileChannel对象
    protected FileChannel fileChannel;
    /**
     * Message will put to here first, and then reput to FileChannel if writeBuffer is not null.
     */
    protected ByteBuffer writeBuffer = null;
    protected TransientStorePool transientStorePool = null;
    //映射的文件名
    private String fileName;
    //映射的起始偏移量
    private long fileFromOffset;
    //映射的文件
    private File file;
    //映射的内存对象
    private MappedByteBuffer mappedByteBuffer;
    //最后一条消息保存时间  
    private volatile long storeTimestamp = 0;
    //是不是刚刚创建的
    private boolean firstCreateInQueue = false;
```
{% endcode-tabs-item %}
{% endcode-tabs %}



