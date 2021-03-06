### Class的访问标志、类、父类、接口索引

#### Class的访问标志

常量池结束后的后两个字节代表访问标志（`access_flags`），用于识别一些类或接口层次的访问信息。

包括：

* 这个`Class`是类还是接口
* 是否定义为`pulbic`类型
* 是否定义为`abstract`类型
* 如果是类，是否声明为`final`
* ...

因为是个`u2`，所以有16个标志位可以使用。



#### 类索引、父类索引、接口索引集合

类索引（`this_class`）和父类索引（`super_class`）都是一个`u2`类型的数据，

接口索引集合（`interfaces`）是一组`u2`类型的数据的集合。

> 这些都是为了找到全限定名。
>
> 除了`java.lang.Object`外，所有`Java`类都有父类，父类索引都不为0

![](img\类索引查找全限定名的过程.png)