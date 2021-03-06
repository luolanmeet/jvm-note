### Java堆（Java Heap）

虚拟机所管理的内存中最大的一块，**在虚拟机启动时创建。此内存唯一的目的就是存放对象**。

> 几乎所有对象实例以及数组都应当在堆上分配。除了栈上分配、标量替换等情况。



#### 堆的构成-回收内存角度

许多垃圾收集器都基于“经典分代”来设计的，需要将`Java`堆划分为新生代、老年代、永久代。

然后也需要新生代、老年代收集器搭配才能工作。



#### 堆的构成-内存分配角度

堆是所有线程共享的，但也有线程私有的空间（`Thread Local Allocation Buffer`, `TLAB`）。



#### 相关参数

|        | 作用                                                         |
| ------ | ------------------------------------------------------------ |
| `-Xmx` | `-Xmx2g`设置堆的最大可用内存                                 |
| `-Xms` | `-Xms500m`设置堆的初始内存<br />一般设置和`-Xmx`值相同，防止内存抖动 |



#### 堆溢出代码

```Java
/**
 * 堆中存储Java对象，只需不断创建对象，并且保证GC Roots到对象之间有可达路径
 * 避免被回收即可产生内存溢出异常。
 *
 * -verbose:gc -Xms20M -Xmx20M -Xmn10M -XX:+PrintGCDetails -XX:SurvivorRatio=8
 */
public class HeadOOM {

    public static void main(String[] args) {

        List<HeadOOM> list = new ArrayList<>();
        while (true) {
            list.add(new HeadOOM());
        }
    }
}
```

