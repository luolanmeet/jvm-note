

### ☕️Java虚拟机 

* [前言](README.md)

### 🍔内存区域

* [运行时数据区域](content/part1/运行时数据区域.md)
  * [程序计数器](content/part1/运行时数据区域/程序计数器.md)
  * [Java虚拟机栈](content/part1/运行时数据区域/Java虚拟机栈.md)
  * [本地方法栈](content/part1/运行时数据区域/本地方法栈.md)
  * [Java堆](content/part1/运行时数据区域/Java堆.md)
  * [方法区](content/part1/运行时数据区域/方法区.md)
  * [直接内存](content/part1/运行时数据区域/直接内存.md)
  
* [对象的知识](content/part1/对象的知识.md)
  * [对象的生命周期](content/part1/对象的知识/对象的生命周期.md)
  * [对象的内存布局](content/part1/对象的知识/对象的内存布局.md)
  * [对象的访问定位](content/part1/对象的知识/对象的访问定位.md)

### 🍨垃圾收集器

* [垃圾收集器](content/part2/垃圾收集器.md)
  * [对象存活的判断](content/part2/垃圾收集器/对象存活的判断.md)
  * [回收方法区](content/part2/垃圾收集器/回收方法区.md)
  * [垃圾收集算法](content/part2/垃圾收集器/垃圾收集算法.md)
    * [标记-清除算法](content/part2/垃圾收集器/垃圾收集算法/标记-清除算法.md)
    * [标记-复制算法](content/part2/垃圾收集器/垃圾收集算法/标记-复制算法.md)
    * [标记-整理算法](content/part2/垃圾收集器/垃圾收集算法/标记-整理算法.md)
  * [算法实现细节](content/part2/垃圾收集器/算法实现细节.md)
    * [根节点枚举](content/part2/垃圾收集器/算法实现细节/根节点枚举.md)
    * [安全点](content/part2/垃圾收集器/算法实现细节/安全点.md)
    * [安全区域](content/part2/垃圾收集器/算法实现细节/安全区域.md)
    * [记忆集与卡表](content/part2/垃圾收集器/算法实现细节/记忆集与卡表.md)
    * [写屏障](content/part2/垃圾收集器/算法实现细节/写屏障.md)
    * [并发可达性分析](content/part2/垃圾收集器/算法实现细节/并发可达性分析.md)
  * [垃圾收集器](content/part2/垃圾收集器/垃圾收集器.md)
    * [Serial 收集器](content/part2/垃圾收集器/垃圾收集器/Serial收集器.md)
    * [ParNew 收集器](content/part2/垃圾收集器/垃圾收集器/ParNew收集器.md)
    * [Parallel Scavenge 收集器](content/part2/垃圾收集器/垃圾收集器/Parallel Scavenge收集器.md)
    * [Serial Old 收集器](content/part2/垃圾收集器/垃圾收集器/Serial Old收集器.md)
    * [Parallel Old 收集器](content/part2/垃圾收集器/垃圾收集器/Parallel Old收集器.md)
    * [CMS 收集器](content/part2/垃圾收集器/垃圾收集器/CMS收集器.md)
    * [Garbage First 收集器](content/part2/垃圾收集器/垃圾收集器/Garbage First收集器.md)

### 🍥虚拟机执行子系统

* [虚拟机执行子系统](content/part3/虚拟机执行子系统.md)
  * [类文件结构](content/part3/虚拟机执行子系统/类文件结构.md)
    * [魔数与Class文件的版本](content/part3/虚拟机执行子系统/类文件结构/魔数与Class文件的版本.md)
    * [常量池](content/part3/虚拟机执行子系统/类文件结构/常量池.md)
    * [Class的访问标志、类、父类、接口索引](content/part3/虚拟机执行子系统/类文件结构/Class的访问标志、类、父类、接口索引.md)
    * [字段表集合](content/part3/虚拟机执行子系统/类文件结构/字段表集合.md)
    * [方法表集合](content/part3/虚拟机执行子系统/类文件结构/方法表集合.md)
    * [属性表](content/part3/虚拟机执行子系统/类文件结构/属性表.md)
      * [Code 属性](content/part3/虚拟机执行子系统/类文件结构/属性表/Code 属性.md)
      * [Exceptions 属性](content/part3/虚拟机执行子系统/类文件结构/属性表/Exceptions 属性.md)
      * [ConstantValue 属性](content/part3/虚拟机执行子系统/类文件结构/属性表/ConstantValue 属性.md)
    * [编译后生成的类文件](content/part3/虚拟机执行子系统/类文件结构/编译后生成的类文件.md)
  * [字节码指令简介](content/part3/虚拟机执行子系统/字节码指令简介.md)
    * [加载和存储指令](content/part3/虚拟机执行子系统/字节码指令简介/加载和存储指令.md)
      * [运算指令](content/part3/虚拟机执行子系统/字节码指令简介/运算指令.md)
      * [类型转换指令](content/part3/虚拟机执行子系统/字节码指令简介/类型转换指令.md)
      * [对象创建与访问指令](content/part3/虚拟机执行子系统/字节码指令简介/对象创建与访问指令.md)
      * [操作数栈管理指令](content/part3/虚拟机执行子系统/字节码指令简介/操作数栈管理指令.md)
      * [方法调用和返回指令](content/part3/虚拟机执行子系统/字节码指令简介/方法调用和返回指令.md)
      * [同步指令](content/part3/虚拟机执行子系统/字节码指令简介/同步指令.md)
  * [虚拟机类加载机制](content/part3/虚拟机执行子系统/虚拟机类加载机制.md)
  * [类加载的时机](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的时机.md)
  
    * [类加载的过程](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的过程.md)
      * [加载](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的过程/加载.md)
        * [验证](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的过程/验证.md)
      * [准备](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的过程/准备.md)
      * [解析](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的过程/解析.md)
      * [初始化](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载的过程/初始化.md)
      * [类加载器](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载器.md)
      * [双亲委派模型](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载器/双亲委派模型.md)
  
        * [破坏双亲委派模型](content/part3/虚拟机执行子系统/虚拟机类加载机制/类加载器/破坏双亲委派模型.md)
  * [虚拟机字节码执行引擎](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎.md)
      * [运行时栈桢结构](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/运行时栈桢结构.md)
        * [局部变量表](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/运行时栈桢结构/局部变量表.md)
        * [操作数栈](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/运行时栈桢结构/操作数栈.md)
        * [动态连接&方法返回地址&附加信息](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/运行时栈桢结构/动态连接&方法返回地址&附加信息.md)
      
      * [方法调用](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/方法调用.md)
        * [解析调用](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/方法调用/解析调用.md)
        * [分派调用](content/part3/虚拟机执行子系统/虚拟机字节码执行引擎/方法调用/分派调用.md)

### 🍜程序编译与代码优化

* [程序编译与代码优化](content/part4/程序编译与代码优化.md)
  * [前端编译与优化](content/part4/程序编译与代码优化/前端编译与优化.md)
  * [后端编译与优化](content/part4/程序编译与代码优化/后端编译与优化.md)
    * [即时编译器](content/part4/程序编译与代码优化/后端编译与优化/即时编译器.md)
    * [编译器优化技术](content/part4/程序编译与代码优化/后端编译与优化/编译器优化技术.md)
      * [方法内联](content/part4/程序编译与代码优化/后端编译与优化/编译器优化技术/方法内联.md)
      * [逃逸分析](content/part4/程序编译与代码优化/后端编译与优化/编译器优化技术/逃逸分析.md)
      * [公共子表达式消除](content/part4/程序编译与代码优化/后端编译与优化/编译器优化技术/公共子表达式消除.md)

### 🥗高效并发

* [高效并发](content/part5/高效并发.md)
  * [Java内存模型与线程](content/part5/高效并发/Java内存模型与线程.md)
    * [Java内存模型](content/part5/高效并发/Java内存模型与线程/Java内存模型.md)
      * [volatile的特殊规则](content/part5/高效并发/Java内存模型与线程/Java内存模型/volatile的特殊规则.md)
      * [long和double的特殊规则](content/part5/高效并发/Java内存模型与线程/Java内存模型/long和double的特殊规则.md)
      * [先行发生原则](content/part5/高效并发/Java内存模型与线程/Java内存模型/先行发生原则.md)
    * [Java与线程](content/part5/高效并发/Java内存模型与线程/Java与线程.md)
  * [线程安全与锁优化](content/part5/高效并发/线程安全与锁优化.md)
    * [线程安全](content/part5/高效并发/线程安全与锁优化/线程安全.md)
      * [互斥同步](content/part5/高效并发/线程安全与锁优化/线程安全/互斥同步.md)
      * [非阻塞同步](content/part5/高效并发/线程安全与锁优化/线程安全/非阻塞同步.md)
      * [无同步方案](content/part5/高效并发/线程安全与锁优化/线程安全/无同步方案.md)
    * [锁优化](content/part5/高效并发/线程安全与锁优化/锁优化.md)
      * [自旋锁与自适应自旋](content/part5/高效并发/线程安全与锁优化/锁优化/自旋锁与自适应自旋.md)
      * [锁消除&锁粗化](content/part5/高效并发/线程安全与锁优化/锁优化/锁消除&锁粗化.md)
      * [轻量级锁](content/part5/高效并发/线程安全与锁优化/锁优化/轻量级锁.md)
      * [偏向锁](content/part5/高效并发/线程安全与锁优化/锁优化/偏向锁.md)

