### volatile的特殊规则

当一个变量被定义称`volatile`之后，它将具备两项特性：

* 保证此变量对所有线程的可见性，这里的可见性是指当一个线程修改了

  这个变量的值，新值对于其他线程来说是可以立即得知的。而普通变量

  并不能做到这点，普通变量的值在线程间传递均需要通过主内存来完成。

* 禁止指令重排，<span style="border-bottom:2px dashed yellow;">普通的变量仅会保证在该方法的执行过程中所有依赖赋值</span>

  <span style="border-bottom:2px dashed yellow;">结果的地方都能获取到正确的结果，而不能保证变量赋值操作的顺序与程序</span>

  <span style="border-bottom:2px dashed yellow;">代码中的执行顺序一致。</span>因为在同一个线程的方法执行过程中无法感知到这点，

  这就是`Java`内存模型中描述的所谓“线程内表现为串行的语义”（`Within-Thread As-If-Serial Semantics`）



#### 实现原理

使用`volatile`修饰的变量，赋值后会多执行一个`lock add1 $0x0,(%esp)`操作，

这个操作的作用相当于一个内存屏障（`Memory Barrier`或`Memory Fence`），<span style="border-bottom:2px dashed yellow;">指令</span>

<span style="border-bottom:2px dashed yellow;">重排时不能把后面的指令重排序到内存屏障之前的位置。</span>

`lock add1 $0x0,(%esp)`把`ESP`寄存器的值加0，显然是一个空操作。<span style="border-bottom:2px dashed yellow;">作用是将本处理器</span>

<span style="border-bottom:2px dashed yellow;">的缓存写入内存，该写入工作会引起别的处理器或别的内核无效化（`Invalidate`）其缓存，</span>

这种操作相当于对缓存中的变量做了一次`Java`内存模型中所说的`store`和`write`操作。

通过这么个空操作，可以让`volatile`变量的修改对其他处理器立即可见。

<span style="border-bottom:2px dashed yellow;">`lock add1 $0x0,(%esp)`指令把修改同步到内存时，意味着所有之前的操作都已经执行完成，</span>

<span style="border-bottom:2px dashed yellow;">这样便形成了“指令重排无法越过内存屏障”的效果。</span>



