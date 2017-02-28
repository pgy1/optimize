# JVM 层优化方案

###JVM参数调优

-Xms256m  // 初始化堆（ 物理内存  1/64）

-Xmx512m // 最大堆（ 物理内存  1/4）

-Xmn96m // 年轻代大小(1.4or lator)增大年轻代后,将会减小年老代大小.推荐配置为整个堆的3/8

-Xss128k // 每个线程的堆栈大小

-XX:PermSize=256m // 持久化初始值（ 物理内存  1/64）

-XX:MaxPermSize=512m // 持久代最大值（ 物理内存  1/4）

-XX:MaxTenuringThreshold // 垃圾最大年龄

-XX:PretenureSizeThreshold // 对象超过多大是直接在旧生代分配

-XX:+UseParNewGC // 设置年轻代为并行收集

-XX:+UseParallelGC // 选择垃圾收集器为并行收集器.此配置仅对年轻代有效.

-XX:+UseParallelOldGC // 选择垃圾收集器为并行收集器.对主次GC都有效.


-XX:+PrintGC // 打印GC信息

-XX:+PrintGCDetails// 打印GC详情


###实例：
---

-Xms128m

-Xmx512m

-Xmn64m

-XX:PermSize=192m

-XX:MaxPermSize=256m

-XX:PretenureSizeThreshold=5m

-XX:MaxTenuringThreshold=5

-XX:+UseParNewGC

-XX:+PrintGCTimeStamps

-XX:+PrintGC

-XX:+PrintHeapAtGC

-Xloggc:logs\zhbk_gc.log

---