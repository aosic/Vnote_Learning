





作者：匿名用户  
链接：https://www.zhihu.com/question/292840506/answer/494206423  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

个人见解：

  

**Scala的编程风格和Haskell很大程度上是不相容的，请不要走弯路，试图混淆两者的学习路径。**

  

Haskell的常规路径大概是：

文法 --\> lambda运算 --> 简单类型和函数类型 --> 代数数据类型 --> 类型类，高阶类型和范畴 --> 面向组合子编程 --> 编译器魔法，DSL和协议建模等等 --> 程序正确性证明（雾

  

而Scala的合理路径大概是：

面向对象 --> 高阶函数 --> 简单的代数数据类型+模式匹配 --\> 函数类型，子类型及协变/逆变（Scala对象和类型系统的重点） --> 接口和泛型，更优雅的设计模式 --> 命名空间和模块设计 --> 分布式和高并发场景的业务实现；

  

两者的交集，无非就是一些类似fold的函数，类似Either或Maybe的基础结构，模式匹配，匿名函数，没了。可以说Scala不过提供了一些函数式的语法糖，简化了Java中常见的boilerplate，同时引入了不少最佳实践，让你更简单优雅地写Java罢了。

  

两者的内核一个是函数式，一个是进阶版的面向对象，仍然有本质区别。

  

根据现有经验看，在Scala中引入任何**高级**的特性都可能成为项目杀手，没有编码规范，各种重载运算符、隐式上下文甚至宏早晚把项目搞成灯谜大会。

  

可以说，把Scala当作JVM上的Rust更合适。Scala当初诞生过程过于狂野，导致特性太多，编译器性能跟不上，编程实践也是五花八门难以统一...... 马丁奥德老司机近年来一直着力于重新寻找Scala的理论立足点，正在筹备发布Scala 3，挺期待~

  

然而Kotlin已经开始大量侵吞JVM语言份额，很多公司的Scala项目也挂掉了，Java也越来越成熟，Scala前景可谓非常迷茫（摊手

















