### ConstantValue 属性

`ConstantValue` 属性的作用是通知虚拟机自动为静态变量赋值，值域被`static`关键字修饰的变量（类变量）

才可以使用这项属性。

`ConstantValue`的属性值只限于基本类型和`String`。

> 关于类变量有两种赋值的方式，在类构造器`<clinit>()`方法中或者使用`ConstantValue`属性。
>
> 目前`Oracle`实现的`Javac`编译器的选择是，如果同时使用`final`和`static`来修饰一个变量（其实已经是常量了），
>
> 并且这个变量的数据类型是基本类型或`java.lang.String`，将会生成`ConstantValue`属性来进行初始化。
>
> 如果没有被`final`修饰或并非基本类型及字符串，则将会在`<clinit>()`方法中进行初始化。