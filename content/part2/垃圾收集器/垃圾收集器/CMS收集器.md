### CMS 收集器

老年代垃圾收集器，使用标记-清除算法，**并发**收集。

`CMS`（`Concurrent Mark Sweep`）收集器是一种以获取最短回收停顿时间为目标的收集器。

被称为“并发低停顿收集器”

![](img\Concurrent Mark Sweep 收集器.png)

#### 收集过程

1. 初始标记（`CMS initial mark`）`stw`
2. 并发标记（`CMS concurrent mark`）
3. 重新标记（`CMS remark`） `stw`
4. 并发清除（`CMS concurrent sweep`）

整个过程中耗时最长的是并发标记和并发清除过程。但这两个过程用户线程都不需要停顿。