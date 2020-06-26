### Serial Old 收集器

老年代收集器、使用标记-整理算法、单线程。

`Serial Old`收集器是`Serial`收集器的老年代版本。

![](img\Serial收集器.png)

用途

* 在`JDK5`以及之前的版本，与`Parallel Scavenge`收集器搭配使用
* 作为`CMS`收集器发生失败是的后备预案，在发生`Concurrent Mode Failure`时使用。

