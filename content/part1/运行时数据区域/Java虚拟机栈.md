### Java虚拟机栈（Java Virtual Machine Stack）

描述的是Java方法执行的线程内存模型：每个方法被执行的时候，Java虚拟机都会同步创建一个栈桢（`Stack Frame`）用于存储局部变量表、操作数栈、动态连接、方法出口等。

>  每一个方法被调用直至执行完毕的过程，就对应着一个栈桢在虚拟机栈中入栈和出栈的过程。



#### 栈桢的构成

|            | 内容                                                         |
| ---------- | ------------------------------------------------------------ |
| 局部变量表 | 存放方法的参数、局部变量<br />（基本数据类型【boolean/byte/char/short/int/float/long/double】、<br />对象引用【reference】、returnAddress类型【指向一条字节码指令的地址】） |
| 操作数栈   | 存放操作数<br />局部变量表中的变量是不能直接使用的，需要先加载到操作数栈 |
| ...        | ...                                                          |

> 局部变量表中的存储空间以局部变量槽（`Slot`）来表示，**其中64位长度的`long`和`double`类型的数据需要占用两个变量槽，其余的数据类型只占用一个**。
>
> 局部变量表所需的内存空间在编译期间完成分配，当进入一个方法时，这个方法需要在栈桢中分配多大的局部变量空间是完全确定的，在方法运行期间不会改变局部变量表的大小。**这里的大小是指变量槽的数量**，一个变量槽占多少个比特由具体虚拟机决定。



#### 相关参数

|        | 作用                           |
| ------ | ------------------------------ |
| `-Xss` | `-Xss128k`设置每个线程的栈大小 |

思考

* 递归容易出现栈溢出。
* 方法入参太多时，对应的栈桢大小也会较大，可将参数封装在对象中。用引用传递，降低栈桢大小。



#### 栈溢出代码

```Java
/**
 * HosSpot虚拟机中并不区分虚拟机栈和本地方法栈，
 * 因此-Xoss（设置本地方法栈大小）没有效果。
 * 栈容量只有-Xss参数设定。
 *
 * 如果线程请求的栈深度大于虚拟机所允许的最大深度，将抛出StackOverflowError。
 * 如果虚拟机栈内存允许动态扩展，当扩展到无法申请到足够内存时，将抛出OutOfMemoryError
 * HotSpot是选择不动态扩展的，虚拟机栈是不会有OOM的
 *
 * -Xss128k
 */
public class JavaVMStackSOF {

    int stackLength = 1;

    public void stackLeak() {
        stackLength++;
        stackLeak();
    }

    public static void main(String[] args) {

        JavaVMStackSOF oom = new JavaVMStackSOF();

        try {
            oom.stackLeak();
        } catch (Throwable e) {
            System.out.println("stack length：" + oom.stackLength);
            throw e;
        }
    }
}
```

