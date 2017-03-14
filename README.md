# Java性能优化方案
记录一下项目过程中，学习和选用的优化方案

##典型的性能问题
如页面响应慢、接口超时，服务器负载高、并发数低，数据库频繁死锁等。

##Java 应用性能的瓶颈点
比如磁盘、内存、网络 I/O 等系统因素，Java 应用代码，JVM GC，数据库，缓存等。

##Java 性能优化分为 4 个层级：应用层、数据库层、框架层、JVM 层。
>1. 比如应用层需要理解代码逻辑，通过 Java 线程栈定位有问题代码行等；
>2. 数据库层面需要分析 SQL、定位死锁等；
>3. 框架层需要懂源代码，理解框架机制；
>4. JVM 层需要对 GC 的类型和工作机制有深入了解，对各种 JVM 参数作用了然于胸；

##围绕 Java 性能优化，有两种最基本的分析方法：现场分析法和事后分析法
>1. 现场分析法通过保留现场，再采用诊断工具分析定位。现场分析对线上影响较大，部分场景（特别是涉及到用户关键的在线业务时）不太合适。
>2. 事后分析法需要尽可能多收集现场数据，然后立即恢复服务，同时针对收集的现场数据进行事后分析和复现。

###JVM层优化
[JVM层优化实例](https://github.com/pgy1/optimize/blob/master/JVM%E5%B1%82%E4%BC%98%E5%8C%96/JVM%E5%B1%82%E4%BC%98%E5%8C%96%E5%AE%9E%E4%BE%8B.md)

[JVM层要点](https://github.com/pgy1/optimize/blob/master/JVM%E5%B1%82%E4%BC%98%E5%8C%96/JVM%E5%B1%82%E8%A6%81%E7%82%B9.md)

###前端优化
[前端优化实例](https://github.com/pgy1/optimize/blob/master/%E5%89%8D%E7%AB%AF%E4%BC%98%E5%8C%96/%E5%89%8D%E7%AB%AF%E4%BC%98%E5%8C%96%E5%AE%9E%E4%BE%8B.md)

###应用层优化
[应用层优化实例](https://github.com/pgy1/optimize/blob/master/%E5%BA%94%E7%94%A8%E5%B1%82%E4%BC%98%E5%8C%96/%E5%BA%94%E7%94%A8%E5%B1%82%E4%BC%98%E5%8C%96%E5%AE%9E%E4%BE%8B.md)

###数据库层优化
[数据库层优化实例](https://github.com/pgy1/optimize/blob/master/%E6%95%B0%E6%8D%AE%E5%BA%93%E5%B1%82%E4%BC%98%E5%8C%96/%E6%95%B0%E6%8D%AE%E5%BA%93%E5%B1%82%E4%BC%98%E5%8C%96%E5%AE%9E%E4%BE%8B.md)

###框架层优化
[框架层优化实例](https://github.com/pgy1/optimize/blob/master/%E6%A1%86%E6%9E%B6%E5%B1%82%E4%BC%98%E5%8C%96/%E6%A1%86%E6%9E%B6%E5%B1%82%E4%BC%98%E5%8C%96%E5%AE%9E%E4%BE%8B.md)

#内存监控、测试分析工具
1.[Jprofile](http://www.ej-technologies.com/download/jprofiler/files) 可用于观察JVM的内存使用情况、GC情况等等

2.[SoapUI](https://www.soapui.org/) 可以测试（HTTP、SOAP、REST）服务接口，性能测试、压力测试等等

