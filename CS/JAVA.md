


 #  官方资源https://docs.oracle.com/javase/8/docs/api/
 

[目前 Java 后端有哪些不是很有必要去学的？https://www.zhihu.com/question/305924723/answer/557800752](https://www.zhihu.com/question/305924723/answer/557800752)

https://docs.oracle.com/javase/8/docs/api/overview-summary.html

本人19本科应届生，专注Java后台学习，已签腾讯WXG的offer（日后转c++)。

众所周知，鹅厂后台一直以C++为重，面试官也是做C++开发。但是语言只是工具，对代码的理解才是核心。面试时重点考察的是基础知识，以及解题的思考过程。凭借着对Java的理解去回答，也受到了面试官的认可，最终幸运的拿到offer。

一直以来，通过知乎这个程序员大牛聚集地，学习到了很多经验方法，也少走了很多弯路。感谢这个平台给予我的帮助，同时也分享一下我的Java学习经验。

## **Java基础**

做java开发，java基础是最需要下功夫的一项。在校招时最注重的就是基础，拿不出像样的项目没关系，但是基础万万不可不牢固。

1.  想要基础扎实，看书沉淀是必须的，有一些编程基础的同学推荐阅读**《JAVA核心技术 卷1》**，可以跳过图形程序设计、事件处理、Swing、applet以及部分日志章节，如果比较吃力也可以先跳过多线程章节。
2.  看完一本书，一定要多加练习去理解和吸收。科班的同学可以用java写实验，写的同时一定要多多运用学到的特性。练习阶段各种设计模式套上去用，不要怕笨重，即使是滥用特性和设计模式也是一种有效的学习。
3.  有了一定量的编程经验后，可以再回过头将**《JAVA核心技术 卷1》**速读一遍，查漏补缺。同时我们开始扩宽我们的知识领域，开始进行JavaWeb的学习。

## **JavaWeb基础**

JavaWeb是一系列技术的综合，也是大多数Java学习者日后的技术方向。及早的了解JavaWeb也有利于更深层面理解，Java在完整的应用中，是如何与各个模块交互并发挥作用的。

基础篇包括Servlet和JSP的学习、tomcat的使用、理解MVC分层模式、mysql的基础用法及JDBC、了解http协议。

1.  这部分的学习，我是通过**《Head First Servlets and JSP》** 。这本书轻松幽默读起来很愉快，但是实在是很厚，而且部分技术已经过时，有时间的同学可以选读。
2.  可以看到这部分的内容是很杂且多的，此阶段注重广度的基础学习，日后慢慢深入。这里推荐个在线教程：

-   ***[Servlet系列教材 （一）- 基础 - 教程：开发第一个Servlet - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/servlet/servlet-eclipse/558.html%3Fp%3D974)***
-   ***[mysql系列教材 （一）- 安装mysql-server - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/mysql/mysql-install/377.html%3Fp%3D974)***
-   ***[Tomcat系列教材 （一）- 教程 - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/tomcat/tomcat-tutorial/541.html%3Fp%3D974)***
-   ***[JSP系列教材 （一）- 教程 - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/jsp/jsp-tutorials/530.html%3Fp%3D974)***
-   ***[HTTP协议系列教材 （一）- 教程 - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/http/http-tutorials/568.html%3Fp%3D974)***
-   ***[JDBC系列教材 （一）- Java 使用JDBC之前，先要准备mysql](http://link.zhihu.com/?target=http%3A//how2j.cn/k/jdbc/jdbc-mysql/386.html%3Fp%3D974)***
-   ***[MVC系列教材 （一）- 教程 - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/mvc/mvc-tutorials/561.html%3Fp%3D974)***

3\. 重点要理解Servlet的原理以及生命周期。在完成这一部分的学习后，可以简单的做个小网站，包括注册登陆，增删改查等功能。如果想继续折腾，可以考虑将项目部署在阿里云或者腾讯云上，一个完整可供他人访问的项目，所获得的成就感是非凡的。

***[部署到Linux系列教材 （一）- 介绍 - 如何把J2EE应用部署到Linux - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/deploy2linux/deploy2linux-breif/1591.html%3Fp%3D974)***

## **Java进阶**

Java始终是我们JavaWeb开发体系中最核心的一环，唯有不停地探索，才能把握住方向和机遇。

1.  在做完一个简单完整的JavaWeb项目后，我们对代码的认知和理解会提高不少，这对接下来的深入学习打下基础。Java圣经：**《JAVA编程思想》** 值得仔细品读，作者的功力十分深厚，即使很多内容还无法理解，但每次读完一定会有所收获。同样建议跳过“图形化用户界面“章节，这是一本伴随我们技术成长的好书，买一本放在旁边，摸着就有底气。
2.  读完编程思想，建议写一个有一定复杂度和代码量的后台项目。可以是一个http服务器，一个大型聊天室，也可以参考我的项目实现一个DBMS：***[wwwyanxin/wyxDBMS](http://link.zhihu.com/?target=https%3A//github.com/wwwyanxin/wyxDBMS)*** 这一部分要强化我们的Java基础，同时也为日后的招聘积累项目经验。
3.  做完项目我们又该看书沉淀技术了，此时我推荐**《Effective Java》**，这本书并不厚但是干货十足，作者讲述Java的最佳实践和经验规则。它能帮助我们写出清晰、健壮、高效的代码，同时这本书涵盖了非常多的面试考点，一定要牢记于心！
4.  最后还要深入学习Java多线程技术以及Java虚拟机原理，这两部分难度较大，理解起来比较抽象。也许日后工作中，我们很少遇到并发问题，不一定有机会进行JVM调优，但是这部分一定要认真对待，越理解底层写出的代码越高效，查bug时越准确，另外更重要的是面试常考！推荐两本书**《Java并发编程的艺术》《深入理解Java虚拟机》，**以及并发编程网：***[并发编程网 \- ifeve.com](http://link.zhihu.com/?target=http%3A//ifeve.com/)*** 重点掌握java内存模型，各种锁的原理及应用，JVM GC垃圾回收原理。

## **JavaWeb进阶**

围绕整个java体系学习，我们要筑起高高的城墙。

1.  **Linux**，现在的服务器基本都是Linux系统，也不存在图形化操作界面。作为开发工程师推荐阅读**《The Linux Command Line》**，有中文在线免费版本**[TLCL](http://link.zhihu.com/?target=http%3A//billie66.github.io/TLCL/index.html)。**那本《鸟哥的Linux私房菜》更适合运维工程师，就不推荐给大家了。学习的时候，可以去阿里云或腾讯云租一个学生服务器，每个月大概10元左右，直接ssh到云服务器上操作，能更好地模拟公司的开发及生产环境。
2.  **操作系统原理**，主要学习进程控制调度、进程通信、存储和设备管理、文件管理以及系统安全。这一部分可以通过看教材或者自行找一些网课补充。
3.  **数据库**，可以买一本**《MySQL必知必会》**小册子作为基础入门，没有什么理论的堆砌，是一本实践指南。学习数据库原理可以阅读**《MySQL技术内幕》**索引优化、事务、锁、范式都是重点。
4.  **网络协议**，入门可以读**《图解HTTP》《图解TCP/IP》**如果要深入研究可以读**《UNIX网络编程 卷1》**和**《TCP/IP详解 卷1》**大多数开发者接触http和tcp、udp、ip协议比较多，但是对整体网络协议栈有个完整了解是必要的。
5.  **数据结构与算法，**数据结构是算法的基础，一定要清晰明了。算法则是笔试面试中无法绕过的难关，推荐去LeetCode刷题，现在也有了中文官方网站：***[力扣 (LeetCode) 中国官网 - 全球极客挚爱的技术成长平台](http://link.zhihu.com/?target=https%3A//leetcode-cn.com/)*** 从easy难度开始刷起，积累一定题量之后，做算法题会很快找到类型方法。
6.  **SSM框架**，Spring+SpringMVC+MyBatis可以说是开发必备了，但框架只是锦上添花，不要太依赖框架进行学习。当我们能不依赖任何框架开发完整项目时，才是真正掌握了它。最为重要的是理解Spring的两个特性：IOC 反转控制和DI 依赖注入。明白实现原理以及为什么要使用Spring，只有这样才能在层出不穷的框架中灵活应对，立于不败之地。

-   [Spring系列教材 （一）- 教程 - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/spring/spring-ioc-di/87.html%3Fp%3D974)
-   [Spring MVC系列教材 （一）- 教程](http://link.zhihu.com/?target=http%3A//how2j.cn/k/springmvc/springmvc-springmvc/615.html%3Fp%3D974)
-   [Mybatis系列教材 （一）- 基础 - 入门教程 - how2j.cn](http://link.zhihu.com/?target=http%3A//how2j.cn/k/mybatis/mybatis-tutorial/1087.html%3Fp%3D974)

## **加分技能**

1.  **前端**，一些岗位要求全栈，即使不是全栈，懂得前端技术的后台能写出更加合理的接口，与前端工程师合作起来会更顺利，理解项目更通透，解决问题准确迅速。
2.  学习一门**动态语言**，动态语言开发起来更灵活迅速。同时比较动态静态语言的特点，可以更好去提炼跳出语言束缚的代码思想。推荐学习JavaScript或者Python等。
3.  **大数据**，大数据开发近几年也是热门方向之一，有兴趣的同学可以学习。
4.  **热门工具及框架**，包括分布式Dubbo、缓存优化redis、nginx、虚拟化技术docker等。一般来说本科应届生不会要求很高，但是要对热门技术有一定的了解。

## **常用网站推荐**

1.  **GitHub： *[Build software better, together](http://link.zhihu.com/?target=https%3A//github.com/)***
2.  **Java学习：*[How2J 的 Java教程](http://link.zhihu.com/?target=http%3A//how2j.cn%3Fp%3D974)***
3.  **Linux命令行：*[TLCL](http://link.zhihu.com/?target=http%3A//billie66.github.io/TLCL/index.html)***
4.  **算法： *[力扣 (LeetCode) 中国官网 - 全球极客挚爱的技术成长平台](http://link.zhihu.com/?target=https%3A//leetcode-cn.com/)***
5.  **正则表达式测试：*[PHP, PCRE, Python, Golang and JavaScript](http://link.zhihu.com/?target=https%3A//regex101.com/)***









如何快速打好Java基础？ - 沈世钧的回答 - 知乎 https://www.zhihu.com/question/50904128/answer/521519858
我学习java的时候，先是通读了《Java编程思想》，然后是《Java核心技术》。当时这两本书还不像现在这么厚，而刚才我把案头的《Java核心技术》第9版翻了翻，上下两册已经1700多页了，可想而知，如果要把它通读一遍，且不说把所有的代码都调通，就是当小说读，估计也需要些时间。

但我现在教学依然首推《Java核心技术》，主要是体系完整，实例多，可操作性强。但对初学者，我一般是只讲前6章，也就是下面的内容：

1.  Java程序设计概述
2.  Java程序设计环境
3.  Java的基础程序设计结构
4.  对象与类
5.  继承
6.  接口与内部类

就《Java核心技术》第9版来说，也就是到250页为止，加把劲，1个月拿下完全没问题。

因为你是自学，所以建议你一定要把其中的代码都调通，课后的作业尽量去做。除此之外，还有两点特别重要：

  
  
作者：沈世钧  
链接：https://www.zhihu.com/question/50904128/answer/521519858  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


目前 Java 后端有哪些不是很有必要去学的？ - 沈世钧的回答 - 知乎 https://www.zhihu.com/question/305924723/answer/557800752
# basestone
“==”常用于用于比较引用和比较基本数据类型时是否具有不同的功能，比较基本数据类型，如果两个值相同，则结果为true而在比较引用时，如果引用指向内存中的同一对象，结果为true。
 直接用==做比较的时候就是比较对象的首地址，肯定是不相等的。
 
equals 方法的特点：

1、自反性：x.equals（x）返回true；

2、对称性：若x.equals（y）为true，则y.equals（x）亦为true；

3、传递性：若x.equals（y）为true且y.equals（z）也为true，则x.equals（z）亦为true；

4、一致性：x.equals（y）的第一次调用为true，那么x.equals（y）的第二次、第三次、第n次调用也均为true，前提条件是没有修改x也没有修改y；

5、对于非空引用x，x.equals（null）永远返回为false。

```
访问修饰符 返回值类型 方法名(参数列表){
    方法体 
}

public  void  functionName(Object arg){ 

}
```
4.**参数列表**：是传递给方法的参数列表，参数可以有多个，多个参数间以逗号隔开，每个参数由参数类型和参数名组成，以空格隔开。当方法被调用时，传递值给参数。这个值被称为实参或变量。参数列表是指方法的参数类型、顺序和参数的个数。参数是可选的，方法可以不包含任何参数。

5.**方法体**：方法体包含具体的语句，定义该方法的功能。



少了训练：

数组成绩






# [方法重写与方法重载的区别](https://www.cnblogs.com/zheting/p/7751787.html)

# 怎样理解JAVA的“构造方法”和“主方法

https://jingyan.baidu.com/article/380abd0a6b94701d90192cca.html

# Java构造方法和析构方法
www.weixueyuan.net/view/5987.html




# Java构造方法
c.biancheng.net/view/976.html



Java中引用变量有两个类型：
1、编译时类型，由声明该变量时使用的类型决定；
2、运行时类型，由实际赋给该变量的对象决定；
在编译时类型与运行时类型不一致时，就可能出现——多态
多态就是“多种形态“；在程序运行过程中才决定用哪个方法，多态性是允许你将父类对象设置成和它的一个或多个子对象相等的技术，赋值后，父对象就可以根据当前赋值给它的子对象的特性运作，即为多态。
多态是面向对象编程领域的核心概念。（面向对象三大特性：封装，继承，多态）
注意：重载方法在编译期间就确定了，是静态的；方法重载与多态无关，真正与多态相关的是重写（覆盖Override）；

多态的存在有3个条件，1)要有继承 2)要有重写3)父类引用指向子类对象

多态的特点：
变量：编译看父类
方法：运行看子类

多态从实现的角度分为：静态多态和动态多态
      静态多态也叫做编译时多态
      动态多态也叫做运行时多态  
多态：同一个符号在不同语义环境下具有不同的解释
一、多态是通过
    1、接口和实现接口并覆盖接口中同一个方法的几种不同的类体现的。
    2、父类和继承父类并覆盖父类中同一方法的几个不同子类实现的。

多态的实现方式：
1、重写
2、接口
3、抽象类和抽象方法
基本上是重载、接口、继承 可通过这三种方式实现 多态
方法的重载，继承或实现接口，父类引用指向子类对象















































































