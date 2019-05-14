不太明白在Coq中对C代码的抽象功能证明了后如何将证明的属性传递到真正的C代码上呢？
https://www.zhihu.com/question/51065669
Coq用的是C还是haskell系编写？



https://zhuanlan.zhihu.com/p/54164515    Coq 入门级技巧

入门笔记
https://blog.csdn.net/Cbcwestwolf/article/details/84754714

www.calvinneo.com/2017/03/12/coq学习笔记/

https://coq.inria.fr/refman/coq-tacindex.html   Coq 官方的文档

https://www.zhihu.com/question/66184910  为什么没被广泛接受的Coq数学教学？


 p, li { white-space: pre-wrap; } 

https://zhuanlan.zhihu.com/p/35937895

  

《\[软件基础\](http://link.zhihu.com/?target=https%3A//coq-zh.github.io/SF-zh/)》系列（英文版 \[Software Foundations\](http://link.zhihu.com/?target=https%3A//softwarefoundations.cis.upenn.edu/)，主要作者 \[Benjamin C. Pierce\](http://link.zhihu.com/?target=http%3A//www.cis.upenn.edu/%7Ebcpierce/)）主要介绍了可靠软件的数学基础。

  

**书籍目前分为《逻辑基础》、《编程语言基础》和《函数式算法验证》三卷本。内容涵盖了函数式编程、逻辑基础、计算机辅助定理证明、Coq 证明助理、编程语言理论、操作语义、霍尔逻辑、静态类型系统、基础数据结构和算法的形式化验证等非常丰富的内容。**






https://eb.host.cs.st-andrews.ac.uk/writings/plpv11.pdf
https://www.cs.cmu.edu/~rwh/papers/dtal/icfp01.pdf





结构证明论（structural proof theory）和解释证明论（interpretational proof theory）。前者着眼于对形式证明的结构进行分析；后者着眼于考察形式理论间的语法翻译。

https://www.zhihu.com/question/58317566/answer/158539605
ATP(自动定理证明)领域研究现状如何有哪些大学在研究?
只听说过荷兰有搞htt的, 曼大有搞机器学习类atp的

求教现今研究主要集中在什么方面?有那些大学在研究?若申博有什么推荐吗?

个人推荐一个会议 CADE (International Conference on Automated Deduction)

\-\-\-\-\-\-\-\-\-\-\-\-\-\-

列几个人觉得有些关系的会议（不分先后）：

-   CADE
-   IJCAR
-   TABLEAUX
-   CP
-   TLCA-RTA
-   TYPES
-   SAT-SMT
-   AAAI
-   IJCAI
-   CAV
-   LICS
-   ISSAC
-   ....

  
  
作者：rainoftime  
链接：https://www.zhihu.com/question/58317566/answer/158117015  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。










# coq
如何实现一个简单的定理证明器？
https://www.zhihu.com/question/52383857/answer/131204615
补充：不限支持的定理种类，以及证明自动化程度（反正有____定理拦路

在用过的theorem prover里面，Coq是最好用的并没有之一。后期维护做的也很好。中文社区主要是Coq群…（逃Coq对于做安全来说，一个很吸引人的地方在于其可以保证百分百的满足property，只要你能恰当的formalize。然而要指出的是，作为一个有着很高工程价值的工具，Coq的门槛还是太高了，验证所需周期还是太长。不过这是整个formal verification领域的问题。针对硬件上Coq的应用，略尴尬。硬件一旦设计确定流片出厂后几乎没办法再修改，所以对于verification的需求对比软件只多不少。然而在硬件的知识体系里，Coq技能的get好比一颗天外飞过来的树杈需要硬生生的怼在技能树上…希望有天能像用C或Java那样去用Coq。

作者：捉木马的蓝胖纸
链接：https://www.zhihu.com/question/56063711/answer/147616100
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



第一：用Coq完成证明的本质还是要自己进行推导。因此学习效果不会打折扣。相反，在Coq中很多可以推广的结论可以直接证明其推广形式，而不是在其各个特例使用“类似可证”。这恰恰更有利于对于数学概念的理解。

  

第二：目前来说不现实。相对现实的是比较基础的抽象代数课程、集合论、数理逻辑等。原因是哪怕最基础的数学分析课程中，也要用到大量的人的直观，或者说数学常识。例如，如果x<y，那么x<(x+y)/2<y。这对于人来说是显然的，但是对于形式化证明来说并不是。在Coq中尚未提供有关的优秀的库的情况下，强制要求学生形式化分析的证明，会导致学生的精力大量浪费在这些不重要的细枝末节上。

  
  
作者：Qinxiang Cao  
链接：https://www.zhihu.com/question/58953828/answer/330434086  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。




# Coq 入门级技巧!!!
https://zhuanlan.zhihu.com/p/54164515


# 圆角骑士魔理沙  
链接：https://www.zhihu.com/question/36578462/answer/137226520  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

最近形式化验证Odd Order Theorem的团队新出了一本Coq书，[Mathematical Components](https://link.zhihu.com/?target=https%3A//math-comp.github.io/mcb/)，就是面向不怎么会编程的（但是要会点数学，看了下，至少需要naive set theory，用到点抽代/线代，不过这两可以现用现学），跟会coq的（但是不会他们的库的）读者。

如果会haskell的话，建议看CPDT。

会编程但是不会函数式编程的话，建议看Software Foundation。

数学库的话，基本的底层打齐了（Set, Real, Function, Peano Nat, Category, Abstract Algebra）。。。上一点的有些也有，比如说线代，微积分，都有库，坑点在文档基本上就是源代码的类型/定义pretty print一下。。。导致要什么功能都只能自己爬整个Coq std lib（甚至contrib），比如说我最近在搞Automatic Differentiation，爬了一小时才搞明白大部分的功能在那，然后又爬了一/两个小时才找出div rule。。。如果有人写一个Coq Differential Calculus Tutorial就会好很多。当然，也许问题是不应该直接看Coqdoc而是该load进Coq里面用Coq自带的Search找出来。。。不过一开始的坑过来，读/写Coq pooof的interactiveness，detail不是PDF能比的-这里引的lemma5.6是啥，我直接Check之，甚至不需要一次context jump（而如果paper引的是另外一个paper的lemma，这就不是一个PDF context jump的问题了），没看懂这里的推理步骤怎么办，直接Check proof/debug eauto，现在我该用什么，SearchAbout Rplus derivable就能给出所有跟+，求导相关的定理，paper能做到吗

语言的话，Coq的自动化**用好了**很爽，有很多现成的decision procedure（Presburger Arithmetic solver，Fourier method for solving inequality，SAT solver，SMT solver，Nelson and Oppen congruence closure algorithm，暴力深搜），你自己也可以任意定制，pattern matching，prolog式backtracking branching，自定义爆搜，自己在OCaml里面写，有不少的时候我自己脑袋里还没证出来，但是Coq已经搞出来了。同时，你做任何的逻辑推导（正向推导，反向推导），coq都会自动的展示出【你还需要证明什么，才能证明整个theorem】，很爽，不需要自己写/放脑袋里。Coq也符合LCF approach-换句话说，只要你在Coq proving mode里面一步步走，到最后把所有东西证明了，就一定对。你也不需要proof read你的证明了，bravo daze!

但是Coq很复杂，甚至有的时候到达了玄学的境界（eauto为什么卡死了，typeclass 推不出来gibberish type error糊多长都可能（因为dependent type，你value有多长type error也能有多长），intuition为什么突然这么慢，说好的LCF approach呢？为啥guarded condition, non structural induction, universe inconsistency（这又是啥？为啥这货跟module相性不好）都不符合LCF approach？par 为啥不solve掉所有goal不能用，simpl刷屏怎么破，exists \[\].为啥推不出type，自己的tactic不work/太慢怎么debug，type checker termination checker universe checker怎么哄，在线等，为什么tactic变强了反而会break proof，为什么Coq自己有这么多bug（不过别担心，Coq有de brujin criteria，换句话说Coq的proof checker很短，就一百行代码左右，只要这100行没bug就不影响证出来的东西的正确性））。。。诚然，这些问题大部分都能解，但是重点是，不是你今天想用coq check自己的proof，明天就能全速做事，要花很多精力进Coq才能学得好。

另外一点就是自动化太慢，这点完全是Coq自找的。。。因为你每次用Coq check proof，搜索过程都会重新启动，重新搜，不会保存下来。。。设计太美不敢想。不算很严重的问题，比如现在我用了1K行formalize了STLC，然后在证明各种property，process一次大体5分钟，比起人肉验证还是快很多。另：传闻adam的proof要12小时才能check，不过adam是adam，自动化程度高到大部分人都到不了他一半，另外就算如此人肉验证也要12小时以上吧。。。

而，不用自动化的话，的确能去掉绝大部分的玄学，速度也会快很多，但是实在太繁琐。。。当然，可以半自动化半手动化，自己找平衡点，不过这自己也是另外的学问了。

另外还有数学证明中常常跳步，但是Coq中不能跳的问题-正是因为这些跳步导致coq老司机写证明也比纸上写慢。

TLDR：慢，难学，但是能自己写自动化程序，有个助手帮你保存下所有的定理（以供Search），写完了不用担心有问题。同时，也可以只用Coq做一部分工作，剩下的用传统方法做，have the best of both world（自动化程度自己定，跳步直接admit，没库用公理代替，甚至根本不用Coq做证明，字面上证，证完一个定理Coq中admit一个（然后comment中写），只用Coq的Search/Check功能，把Coq当定理library用）。如果你问我得畅不偿失，何尝不花几天自己试下呢？（我是认为肯定够的，不然也不会现在还在用了）

最后打个广告，有个Coq QQ群，300多人左右，活跃度还可以，想学Coq的可以自己搜，人最多的就是了。





我没拿 Coq 做过数学科研，只能说业余时候搞了点数学方面的证明。之前学习各种证明技术的时候，用它证明了一下素数有无穷多。然后开了个大坑，打算证一个稍微复杂一点的定理，证明 wallpaper group 只有17种。第一步就是搞个群论的形式化，当然有很多现成的库如 math-classes，不过形式化证明要的就是自己亲手做，看当年教科书上的定理变成实实在在的代码那种爽感，所以我就作大死的自己搞。我参考了现有实现和一些论文，我的 Coq 水平是比较挫的，看那些实现本身也有学习的意思在里面。不过现实中的科研任务也不轻，我业余又比较懒，所以进度很慢。这里面有很多坑，就说最开始遇到的一个吧：集合的定义，直接用 Coq 的 Set 类型是不行的。那样定义出来的群没法轻易定义“商群”，因为没有给你定义等价关系的余地，一种解决办法是加上可判定性相等的 Setoid，然后就可以慢慢定义群、子群、同态、同构……然后我就一直停在那里了，就等某天午夜梦回再起来搞吧

作者：王盛颐
链接：https://www.zhihu.com/question/36578462/answer/86744828
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



# 教材
https://math-comp.github.io/mcb/

https://github.com/math-comp/math-comp

https://github.com/search?utf8=✓&q=coq&type=








# 现况
形式证明与普通数学证明的区别是什么，为什么说费马定理是没有形式证明的？
作者：匿名用户  
链接：https://www.zhihu.com/question/29686410/answer/66676380  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

形式证明与普通数学证明的区别是什么? (前者机器可逐步验证; 后者目前只有人能读, 而且读的普通人头痛; 等自然语言处理达到一定水平, 机器也可以读LaTeX, 吴恩达有学生做过.)  
为什么说费马定理是没有形式证明的？(现有的各种数学证明都可以翻译成形式证明吧, 就是有些人工证明太长太繁琐太难懂了, 还没有人去做吧. 法国一大批学者开发Coq在做, 挺有前途的.)

最近看到一篇把实变函数, 概率论, 信息论, 测度论形式化的论文.  
Ref \[1\]: On the Formalization of the Lebesgue Integration Theory in HOL. [http://hvg.ece.concordia.ca/Publications/TECH\_REP/MLP\_TR10/MLP_TR10.pdf](https://link.zhihu.com/?target=http%3A//hvg.ece.concordia.ca/Publications/TECH_REP/MLP_TR10/MLP_TR10.pdf)  
形式证明在数值分析方面的应用.  
Ref \[2\]: Formal Proof of a Wave Equation Resolution Scheme: the Method Error.  
[http://arxiv.org/pdf/1005.0824.pdf](https://link.zhihu.com/?target=http%3A//arxiv.org/pdf/1005.0824.pdf)  
形式证明在工业界: 检查涉及浮点运算的软件.  
Ref \[3\]: Wave Equation Numerical Resolution: a Comprehensive Mechanized Proof of a C Program  
[http://arxiv.org/pdf/1112.1795.pdf](https://link.zhihu.com/?target=http%3A//arxiv.org/pdf/1112.1795.pdf)  
形式证明在微分方程ODE的应用  
Ref \[4\]: The Picard Algorithm for Ordinary Di erential Equations in Coq  
[http://www.cs.ru.nl/~spitters/Picard.pdf](https://link.zhihu.com/?target=http%3A//www.cs.ru.nl/~spitters/Picard.pdf)

第一篇一个加拿大EE方面的博士形式化了测度论(他博士论文), 你还能让其他学科的人形式化解析数论吗? 说明这方面工作刚开始, 说明在数学界还没有充分重视这方面工作. 话说, 这倒是灌水的好机会: 把所有重要数学论文都形式验证下. 如果稍稍机智点, 或许可以让机器证明一些公开问题.

目前形式证明/定理自动证明/机器证明的困难:  
(1) 计算复杂度. 各种定义, 引理的潜在组合太多, 如何启发式搜索, 或者借用量子计算机?  
Ref \[5\]: Machine learning and automated theorem proving. James P. Bridge. 2010  
[https://www.cl.cam.ac.uk/techreports/UCAM-CL-TR-792.pdf](https://link.zhihu.com/?target=https%3A//www.cl.cam.ac.uk/techreports/UCAM-CL-TR-792.pdf)  
\[6\]: Machine Learning for Automated Theorem Proving. Bernhard Kragl  
[http://pub.ist.ac.at/~chl/ML2015/kragl-sma2015.pdf](https://link.zhihu.com/?target=http%3A//pub.ist.ac.at/~chl/ML2015/kragl-sma2015.pdf)  
(2) 知识图谱. 现有的数学技巧, 物理直觉, 数学成果如何高效的转化为一个数据库?  
Ref \[7\]: Matuszewski, R., Rudnicki, P.: Mizar: The first 30 years. Mechanized Mathematics and Its Applications 4, 3–24 (2005)  
(3) 其余. 计算两个定理之间的距离? 简单解释上同调? 构造反例? 根据哥德尔定理, 添加少许公理假设?  
Ref \[8\]: [https://www21.in.tum.de/~blanchet/axiom_sel.pdf](https://link.zhihu.com/?target=https%3A//www21.in.tum.de/~blanchet/axiom_sel.pdf)  
提出新的猜想, 鉴别组合得到的定理重要性, 提出新的数学工具, 和物理化学等学科的联系. 完全实现这些, 等价于实现了强人工智能, 大约需要十年以上?

就上面参考文献来说, 对目前职业数学工作者而言, 还在比较初级的辅助证明阶段(proof assistants). 对于逻辑电路验证, 高可靠软件而言, 已经有明确的工业应用.  
Ref \[9\]: 交互式定理证明与程序开发 Coq归纳构造演算的艺术(清华软件翻译)

PS. 数学证明会提交到杂志, 有审稿人初审. 重要的论文会被PhD们翻破, 出错的可能性越来越小. 计算机和数学是良好的互相促进, 而且学科融合的很快, 分不清了.

显著感觉国外CS界更关心这些, 理论计算机方面的学者在主导这个领域(他们要做很多应用, 密码学, 软件可靠性验证), 因此费马定理就暂时搁置.



## 大佬云集的资料分享回答
https://www.zhihu.com/question/66184910
# 为什么机器验证的形式化证明没有被数学界广泛采用？

一方面，是不是这样的系统，它还太过复杂，写出来的东西太过罗嗦，不具有使用价值？比如：[仅用Coq等定理证明器，学习诸如实分析之类的数学课程是否现实？](https://www.zhihu.com/question/58953828)。它又为什么会太过复杂呢（相比人类结果的「简洁」）？换句话说，人类的「简洁」中到底隐藏了什么细节？这些细节都可靠吗？一个结果，只要它通过了同行的审核，就可以被认为是正确的吗？

另一方面，这样的形式化证明，它的表达力够不够呢？它能不能表达人类所能理解的所有数学内容？

还有就是，数学界能否接受这种东西呢？将来应不应该投稿必须要是经过形式化验证的？还是说天马行空的「想法」「创意」更重要，即使实际上是有 gap 的？但是将来能不能借助机器学习，就像化解（如）围棋（等人类认为有灵性的东西）中的直觉、找到优良的策略一样，来有效地做数学呢？比如[如何评价DeepMath?](https://www.zhihu.com/question/57317255)

[据说](https://link.zhihu.com/?target=https%3A//news.ycombinator.com/item%3Fid%3D15378012) Voevodsky 就是因为自己犯了巨大的错误才转向研究形式化的？（同时参考[【推荐】一份 Voevodsky 的幻灯片](https://zhuanlan.zhihu.com/p/24741328)）

相关问题：

[如何评价Vladimir Voevodsky？](https://www.zhihu.com/question/64048187)

[形式证明与普通数学证明的区别是什么，为什么说费马定理是没有形式证明的？](https://www.zhihu.com/question/29686410)

https://www.zhihu.com/question/29876277/answer/45891236
我刚入门这玩意，用的Agda，但是给出一个通俗易懂的解释是可以有的。  
在假定你知道在这个语境下啥是“证明”的情况下，交互式证明就是你先给出命题，然后通过IDE给出的提示进行证明(有时还可以让IDE自己猜测证明过程，也就是机器写代码)，最终将它变为一个公理(比如a = a)的过程。IDE会跟踪你的证明过程，告诉你证到哪一步了。和手写的那种证明不同的是，手写证明一般是要写每一步的结论，然后偶尔写用到的定理；而这种证明是必须写每一步用到的定理，然后用了这个定理得到的结论由IDE推断，然后告诉你。

我写完后删了不少名词，为了让它更容易看懂。。。

实际应用：证明算法(编译器等)的正确性/数学定理(四色定理等)的正确性

录了两个视频，一个是给同学看的s3群上的小性质 [http://www.bilibili.com/video/av16337753](https://link.zhihu.com/?target=http%3A//www.bilibili.com/video/av16337753) ，一个是给新手看的自然数加法交换率 [http://www.bilibili.com/video/av16365625](https://link.zhihu.com/?target=http%3A//www.bilibili.com/video/av16365625) ，你们可以去看  
两个都只有十分钟

  
  
作者：兴趣使然千里冰封  
链接：https://www.zhihu.com/question/29876277/answer/261527761  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

# coq官网
https://coq.inria.fr











































































































