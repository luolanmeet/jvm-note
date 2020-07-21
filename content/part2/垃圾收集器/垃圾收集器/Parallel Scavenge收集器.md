### Parallel Scavenge 收集器

新生代收集器，使用标记-复制算法，并行收集。

`Parallel Scavenge`收集器的目标是达到一个可控的吞吐量（`Throughput`）。

`Parallel Scavenge`收集器拥有自适应的调节策略（`GC Ergonomics`）。

#### 参数

| 参数                         | 作用                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| `-XX:MaxGCPauseMillis`       | 允许的值为一个大于0的毫秒数<br />收集器将尽力保证内存回收花费的时间不超过设置的值。<br />更关注停顿时间可设置此值。 |
| `-XX:GCTimeRatio`            | 允许的值为一个大于0小于100的数<br />设置垃圾收集时间占总时间的比率。<br />1 : x，设置的就是x的值，占比时间为 1 / (1 + x)。<br />更关注吞吐量可设置此值。 |
| `-XX:+UseAdaptiveSizePolicy` | 自适应调节策略参数，开启后就不需要人工指定<br />新生代的大小（`-Xmn`）、<br />`Eden`与`Survisor`区的比例（`-XX:SurvivorRatio`）、<br />晋升老年代对象大小（`-XX:PretenureSizeThreshold`） |

