javap math.class >math.txt
反汇编


https://www.bilibili.com/video/av45497157?from=search&seid=10098719170838094425




JVM

https://zhuanlan.zhihu.com/p/25713880
![](_v_images/1559284539_21578.png)

# JVM原理最全、清晰、通俗讲解，五天40小时吐血整理

https://blog.csdn.net/csdnliuxin123524/article/details/81303711





https://blog.csdn.net/witsmakemen/article/details/28600127





# 反射调用



































# [java深浅克隆https://www.cnblogs.com/wuyudong/p/4399180.html](https://www.cnblogs.com/wuyudong/p/4399180.html)

https://www.zhihu.com/question/23031215

浅克隆不会克隆原对象中的引用类型，仅仅拷贝了引用类型的指向。深克隆则拷贝了所有。也就是说深克隆能够做到原对象和新对象之间完全没有影响。
https://blog.csdn.net/jeffleo/article/details/76737560
而深克隆的实现就是在引用类型所在的类实现*Cloneable*接口，并使用*public*访问修饰符重写*clone*方法。


## 总结：

1.浅克隆：只复制基本类型的数据，引用类型的数据只复制了引用的地址，引用的对象并没有复制，在新的对象中修改引用类型的数据会影响原对象中的引用。  
2.深克隆：是在引用类型的类中也实现了clone，是clone的嵌套，复制后的对象与原对象之间完全不会影响。  
3.使用序列化也能完成深复制的功能：对象序列化后写入流中，此时也就不存在引用什么的概念了，再从流中读取，生成新的对象，新对象和原对象之间也是完全互不影响的。  
4.使用clone实现的深克隆其实是浅克隆中嵌套了浅克隆，与toString方法类似


















 p, li { white-space: pre-wrap; } 

  

  

\# https://github.com/silenceyear/zzax/blob/master/java112/doc/memory.md

  

https://www.bilibili.com/video/av49987505?from=search&seid=10098719170838094425

  

  

  

  

  

  

  

  

  

https://www.youtube.com/watch?v=cxh4avYqBFU

  

http://zzax.io/java112/

  

http://zzax.io/java112/doc/transition/

  

  

https://www.zhihu.com/question/29833675

!\[\](\_v\_images/1559228732_20953.png)

  

  

  

  

  

  

  

  

  

  

  

  

  

  

正好开了专栏，写了几篇Java虚拟机相关的文章,关于Java虚拟机的堆、栈、局部变量表等，可以参考下专栏里的这篇—\[Java虚拟机—堆、栈、运行时数据区\](https://zhuanlan.zhihu.com/p/44694290)

**专栏里的文章主要内容总结自-《深入理解Java虚拟机》-周志明第二版和《Java虚拟机规范JavaSE8》,以下是Java虚拟机相关的部分文章:**

  

\[Java虚拟机——字节码、机器码和JVM\](https://zhuanlan.zhihu.com/p/44657693)

  

\[Java虚拟机——类加载机制和类加载器\](https://zhuanlan.zhihu.com/p/44670213)

\[Java虚拟机—堆、栈、运行时数据区\](https://zhuanlan.zhihu.com/p/44694290)

  

\[Java虚拟机—Class文件结构\](https://zhuanlan.zhihu.com/p/45003974)

  

\[Java虚拟机—字节码指令初探\](https://zhuanlan.zhihu.com/p/45050364)

  

\[Java虚拟机—栈帧、操作数栈和局部变量表\](https://zhuanlan.zhihu.com/p/45354152)

  

\[Java虚拟机—对象的内存布局和访问定位\](https://zhuanlan.zhihu.com/p/44948944)

  

\[Java虚拟机—堆内存分代和GC垃圾收集算法\](https://zhuanlan.zhihu.com/p/45558897)

  

作者：Lyon

链接：https://www.zhihu.com/question/29833675/answer/506600010

来源：知乎

著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

  

https://github.com/silenceyear/zzax/














# JAVA堆栈内存JVM本质
https://github.com/silenceyear/zzax/blob/master/java112/doc/memory.md

https://www.bilibili.com/video/av49987505?from=search&seid=10098719170838094425









https://www.youtube.com/watch?v=cxh4avYqBFU

http://zzax.io/java112/

http://zzax.io/java112/doc/transition/


https://www.zhihu.com/question/29833675
![](_v_images/1559228732_20953.png)














正好开了专栏，写了几篇Java虚拟机相关的文章,关于Java虚拟机的堆、栈、局部变量表等，可以参考下专栏里的这篇—[Java虚拟机—堆、栈、运行时数据区](https://zhuanlan.zhihu.com/p/44694290)  
**专栏里的文章主要内容总结自-《深入理解Java虚拟机》-周志明第二版和《Java虚拟机规范JavaSE8》,以下是Java虚拟机相关的部分文章:**

[Java虚拟机——字节码、机器码和JVM](https://zhuanlan.zhihu.com/p/44657693)

[Java虚拟机——类加载机制和类加载器](https://zhuanlan.zhihu.com/p/44670213)  
[Java虚拟机—堆、栈、运行时数据区](https://zhuanlan.zhihu.com/p/44694290)

[Java虚拟机—Class文件结构](https://zhuanlan.zhihu.com/p/45003974)

[Java虚拟机—字节码指令初探](https://zhuanlan.zhihu.com/p/45050364)

[Java虚拟机—栈帧、操作数栈和局部变量表](https://zhuanlan.zhihu.com/p/45354152)

[Java虚拟机—对象的内存布局和访问定位](https://zhuanlan.zhihu.com/p/44948944)

[Java虚拟机—堆内存分代和GC垃圾收集算法](https://zhuanlan.zhihu.com/p/45558897)

  
  
作者：Lyon  
链接：https://www.zhihu.com/question/29833675/answer/506600010  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



























https://github.com/silenceyear/zzax/










