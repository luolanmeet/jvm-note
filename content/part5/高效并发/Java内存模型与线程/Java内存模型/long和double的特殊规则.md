### long和double的特殊规则

`Java`内存模型要求lock、unlock、read、load、assign、use、store、write这8种操作都具有原子性，

但对于64位的数据类型（`long`和`double`），在模型中定义了一条宽松的规定：

允许虚拟机将没有被`volatile`修饰的64位数据的读写操作划分为两次32位的操作来进行，

即允许虚拟机实现自行选择是否要保证64位数据类型的`load`、`store`、`read`和`write`的原子性，

这就是`long`和`double`的非原子性协定（`Non-Atomic Treatment of double and long Variables`）。



#### 引发的问题

如果有多个线程共享一个并未声明为`volatile`的`long`或`double`类型的变量，并且同时对它们进行

读取和修改操作，那么某些线程可能会读到一个即不是原值，也不是其他线程修改值的代表了

“半个变量”的数值。