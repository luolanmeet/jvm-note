### Parallel Old 收集器

老年代收集器，使用标记-整理算法，并行收集。

`Parallel Old`收集器是`Parallel Scavenge`收集器的老年代版本，直到`JDK6`才开始提供，之前新生代的`Parallel Scavenge`收集器只能与`Serial Old`收集器组合使用，现在多了`Parallel Old`这个选择。

![]()![Parallel Old收集器运行示意图](img\Parallel Old收集器运行示意图.png)