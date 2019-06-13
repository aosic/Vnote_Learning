# 基石
认识一个企业的，谈到函数式编程，他说：“没什么，就是lambda表达式代码写成一行的一些语法特点，常用，很多语言都有，没什么稀奇的。”

我想问，这，只是表面吧？最底层用lambda演算实现计算机演算，从最基本的原理上就不同于改进图灵机的冯诺依曼体系，church的图灵机本质上就是不一样的东西好吗？

维基：
可图灵指在可计算性理论中，编程语言或任意其他的逻辑系统如具有等用于通用图灵机的计算能力。换言之，此系统可与通用图灵机互相模拟。这个词源于引入图灵机概念的数学家艾伦·图灵（Alan Turing）。

虽然图灵机会受到存储能力的物理限制，图灵完全性通常指具有无限存储能力的通用物理机器或编程语言==可实现死循环，区分物理机不能实现无限内存。



观点：
图灵完备参见：https://www.zhihu.com/question/20115374
量子力学里面的正交完备基，机器A和图灵机都可以归一化为人类在纸上能够进行的计算==一切可解问题==图灵机==等价于lambda演算==无限内存



完备性的解释。包括：[代数闭域](http://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%25E4%25BB%25A3%25E6%2595%25B0%25E9%2597%25AD%25E5%259F%259F)(algebraically closed field）、[紧化](http://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%25E7%25B4%25A7%25E5%258C%2596)(compactification）或[哥德尔](http://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%25E5%2593%25A5%25E5%25BE%25B7%25E5%25B0%2594/152476)不完备定理。主要还是数理逻辑的内容。

根据图灵假说, 任何可计算的都可以用图灵机表达, 也就是说目前没有比Turing Machine更强大的系统, 所以可以粗略地说如果L图灵完备, 则 L = Turing Machine. 因此"两种语言都是图灵完备, 所以这种的程序另一种至少也能写" 是可以这么说的, 因为两者的表达能力都等于图灵机.
Oracle Machine比Turing Machine更强。不过物理上能造出的最强的机器可能就是图灵机了……




```

于改进图灵机的冯诺依曼体系，

运算的基石是组成原理第六章那个变量区计算倒腾01变量（邓俊辉的算法课还有一个形象的TuringMechine），

然后church的底层实现演算是lambda演算，

具体实现过程看小白文和Github项目（haskell），一目了然，

然后在已经建好的大楼上添砖加瓦，造轮子的人才应该被人尊敬，而不是倒卖知识自己还没学明白的那些靠资源信息不对等挣钱的。
```

然后我们需要实现的是添砖加瓦，《张凇的书应用实例多，有思考，启发性强，让我读了很多遍，很有启发》



同样解决希尔伯特的数学可解性问题，证明了逻辑上等价，二律背反，同一系统能够用不同理论描述，跨理论正确不能保证，但是同一体系下理论自洽不是很正常的吗？
完美。
皮亚诺算术，递归。“我们不能定义数字，因为那更加难以理解”


跳出冯诺依曼的魔咒，haskell函数式编程才是更高明的抽象。










## Haskell中的范畴之函子和自然变换

Monad是一种数学结构，haskell中的Monad意义和数学上的意义是一样的。简单的说单子(Monad)就是自函子范畴上的一个幺半群。这个幺半群的态射是作用在自函子上的自然变换，其单位态射是haskell中class Monad 的return函数(这个实际上是个自然变换)。而这个幺半群的态射的组合操作(composition)则是haskell中class Monad的join函数，也是一个自然变换。  
从几何直观的概念来说，Monad是一个自相似的几何结构，通过自函子的作用和两个自然变换的约束得到一层层嵌套的自相似结构。

  
  
作者：parker liu  
链接：https://www.zhihu.com/question/22291305/answer/21333050  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

这个连接还有很多有价值的回答！




















https://zhuanlan.zhihu.com/p/25565309



















## 论文

https://github.com/cohomolo-gy/haskell-resourceshttps://github.com/mitchellwrosen/haskell-papers



知乎用户baozii强烈推荐：《A History of Haskell: Being Lazy With Class》

个人觉得这篇文章是最最重要的，它告诉你为什么要设计Haskell，也即是Haskell的存在意义是什么








作者：祖与占  
链接：https://www.zhihu.com/question/315005729/answer/618034280  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

TBH, Haskell 也快奔三到头, 在上面发表的论文真多如牛毛, 如果没有一个方向或者目的, 列举出来的意义也不是特别大. 下面按方向随便大概列举一下:

### Meta

A History of Haskell: Being Lazy With Class - 到目前为止 Haskell 前半生的故事, 虽然后期 GHC 的实现翻天覆地, 但是还是可以了解到 Haskell 设计的初衷和其中一些概念(例如 Monad)引入的历史, 还有唐凤用实现 Perl6 当 TAPL 练习题干进 Haskell 2010 标准作者之一的故事之类的. 以及对 [为什么 Haskell 始终没法流行呢？](https://www.zhihu.com/question/39115733/answer/79902920) 这种问题心里也有个答案.

Confessions of a Used Programming Language Salesman - Getting the Masses Hooked on Haskell, Haskell 98 标准作者之一 Erik Meijer 把 Haskell 的 idea 到各个语言"发扬光大"过程中的心路历程, 虽然后面搞了 rx, Dart async spec 这种事情没记录进去.

现在拍脑袋就这两篇.

### Haskell 实现

这个真不是我随便就可以列完整的列表, 而且分支也很多, 我来整个 meta-list:

[A Haskell Implementation Reading List](https://link.zhihu.com/?target=http%3A//www.stephendiehl.com/posts/essential_compilers.html)

[ReadingList - GHC](https://link.zhihu.com/?target=https%3A//ghc.haskell.org/trac/ghc/wiki/ReadingList)

[tweag/asterius](https://link.zhihu.com/?target=https%3A//github.com/tweag/asterius/blob/master/docs/readings.md)

[Haskell 实现相关的 reading list](https://link.zhihu.com/?target=https%3A//archive.fo/RglyT)

以及无脑推荐两个 Simon 的所有 paper

### 类型系统

看 Richard A. Eisenberg 的 PhD 论文 [DEPENDENT TYPES IN HASKELL: THEORY AND PRACTICE](https://link.zhihu.com/?target=https%3A//cs.brynmawr.edu/~rae/papers/2016/thesis/eisenberg-thesis.pdf), 找参考文献看应该会比较好

### 语言抽象/模式

Monad 的推荐看 Philip Wadler 的 - [有没有对Haskell中理解monad比较好的代码例子？](https://www.zhihu.com/question/64207539/answer/217887930)

Applicative: [Idioms: applicative programming with effects](https://link.zhihu.com/?target=http%3A//strictlypositive.org/Idiom.pdf)

其他的可以在 [Typeclassopedia - HaskellWiki](https://link.zhihu.com/?target=https%3A//wiki.haskell.org/Typeclassopedia) 找, Profunctor 最近的还没有

Fun with Semirings 这种玩代数结构也挺好玩的

Parser Combinator, 还是推荐 Graham Hutton, Erik Meijer, 复杂的都要自己看实现. 找更原始的可以看 Parsing Techniques 第二版的参考文献.

Recursion Schemes, Paper 都挺不好看的, 看 [Adventures in Uncertainty](https://link.zhihu.com/?target=https%3A//blog.sumtypeofway.com/) 的介绍好多了, 其他可以到 [passy/awesome-recursion-schemes](https://link.zhihu.com/?target=https%3A//github.com/passy/awesome-recursion-schemes) 找

### 数据结构

Okasaki 全家桶 (

succinct data structure 得看 ekmett 的 talk 和库

### 问题解决方案

估计这个[Functional Pearls](https://link.zhihu.com/?target=https%3A//wiki.haskell.org/Research_papers/Functional_pearls) 密集区了

Expression Problem: Data types a la carte

Oleg Kiselyov 问题终结者: Extensible Effects 系列, Implicit Conﬁgurations, Reﬂection without Remorse

ekmett 所以库相关的都推荐

越列越多, 都看得过来吗?

[编辑于 2019-03-09](/question/315005729/answer/618034280)














https://www.zhihu.com/question/315005729/answer/618034280



## z资料
https://github.com/hzlmn/haskell-must-watch
和下一份笔记



## 历史现状


作者：祖与占  
链接：https://www.zhihu.com/question/40231767/answer/85483603  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

谢邀, 我列下我留意过的组(人), 也不知道强不强, 我也想去看看啊哭

我浅薄地用语言来分下类

Haskell的  
[The Yale Haskell Group](https://link.zhihu.com/?target=http%3A//haskell.cs.yale.edu/) 耶鲁, Paul Hudak(已去世), FRP  
[unsw.edu.au 的页面](https://link.zhihu.com/?target=http%3A//www.cse.unsw.edu.au/~pls/pls-website/index.html) UNSW, Haskell LLVM backend, HPC  
[http://fp.cs.nott.ac.uk/](https://link.zhihu.com/?target=http%3A//fp.cs.nott.ac.uk/) Graham Hutton, 这个

[@阅千人而惜知己](//www.zhihu.com/people/6676ea444bda2c703add8474963e800a)

更加清楚一些  
[http://www.cis.upenn.edu/~plclub/](https://link.zhihu.com/?target=http%3A//www.cis.upenn.edu/~plclub/) Dependently-typed Haskell  
[Max Planck Institute for Software Systems (MPI-SWS)](https://link.zhihu.com/?target=http%3A//plv.mpi-sws.org/) 马普, Haskell相关的记得有Backpack, Rust core team里有个小伙子也是这里出来的, PHD那篇关于并发的论文还拿了奖  
[Home page for DA Turner](https://link.zhihu.com/?target=https%3A//www.cs.kent.ac.uk/people/staff/dat/) David Turner, Kent早年还有点工作出来, 近来没怎么看到  
[Philip Wadler's home page](https://link.zhihu.com/?target=http%3A//homepages.inf.ed.ac.uk/wadler/) 爱丁堡, 老早前有个组做类似LINQ的东西叫LINK有点意思  
[TDA342/DIT260](https://link.zhihu.com/?target=http%3A//www.cse.chalmers.se/edu/course/afp/) Chalmers理工也算是老牌的出FP工作的地方...  
[WebHome < Center < UUCS](https://link.zhihu.com/?target=http%3A//foswiki.cs.uu.nl/foswiki/Center) Utrecht university 也算是老牌, 有些工作我挺喜欢的  
其实去MSR Cambridge跟SPJ混应该也行

经过千人提醒忘了牛津...  
说起牛津想起我是通过这个小哥([http://joshkos.blogspot.com/](https://link.zhihu.com/?target=http%3A//joshkos.blogspot.com/))认识牛津那组人的, 后来发现Richard Bird老爷子也是在牛津, 近来出工作比较多的是Jeremy Gibbons, Recursive Scheme一堆堆我看不懂啊看不懂 (

Scala  
[LAMP | EPFL](https://link.zhihu.com/?target=http%3A//lamp.epfl.ch/) ETH, Scala那堆人, 还有Niklaus Wirth 老爷子

Scheme (Racket)  
[Home - Programming Research Laboratory](https://link.zhihu.com/?target=http%3A//nuprl.github.io/) 东北, Scheme大神云集  
[Utah PLT](https://link.zhihu.com/?target=http%3A//www.cs.utah.edu/plt/) 犹他, Matthew Flatt算是Racket的主要贡献者  
[plwonks](https://link.zhihu.com/?target=http%3A//lambda.soic.indiana.edu/) 这个就不用多介绍了

OCaml  
[Inria - Inventeurs du monde numÃ©rique](https://link.zhihu.com/?target=http%3A//www.inria.fr/) 神一般的INria  
[Computer Laboratory: OCaml Labs](https://link.zhihu.com/?target=http%3A//www.cl.cam.ac.uk/projects/ocamllabs/) 剑桥的OCaml Lab

其他PLT劲旅CMU之类的我不说了







## 巨佬



https://www.zhihu.com/question/27355585/answer/36598532






## 应用

## 企业


https://www.zhihu.com/question/54095611/answer/137873645















### Haskell在工业界有哪些实际的应用？

感觉Haskell更多地是作为研究性语言存在的，有哪些公司把Haskell作为开发语言？

https://www.zhihu.com/question/36325022/answer/67674150



https://www.zhihu.com/question/20246934/answer/15262041





### 工业界新星








https://www.zhihu.com/question/41139361/answer/90430564



























作者：祖与占  
链接：https://www.zhihu.com/question/39115733/answer/79902920  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

看下[A History of Haskell](http://link.zhihu.com/?target=http%3A//research.microsoft.com/en-us/um/people/simonpj/papers/history-of-haskell/) , [Every Language Fixes Something](http://link.zhihu.com/?target=http%3A//www.solipsys.co.uk/new/EveryLanguageFixesSomething.html), Haskell的诞生本身就是出于研究目的的, 并没有想去解决工业界的什么痛点或者难点(如果有软件危机也不是单靠换个语言来解决的), 而且Haskell跟流行的语言一点都不像.

老实说到上个世纪或者GHC没有主导Haskell实现之前(严重地说可以到2010年), Haskell的生产力(不是语言表达力, 主要是库), 培训成本跟主流的语言还是有不少差距, Real World Haskell算是个里程碑, 然而现在也已经过时.

主流语言的变化也逐渐变快, C++/Java也吸收了很多函数式编程语言里的元素, Rust也把之前不少PLT研究积累的成果工业化. 虽然Haskell没有进入主流但是也影响了不少其他语言, 像Java, Swift里的Option, Elixir里的with都脱胎于Haskell的Maybe Monad, 还有coffeescript之类的语言

然而Haskell里面各种概念的演变发展是一般的程序员没法想象的, 要让所有程序员理解Monad的怕是要写无数个"深入浅出"的教程, 以及各种以"如何理解", "怎么用简单的语言"开头的知乎问题还有下面无数不同观点的答案, 何况还有free monad, comonad, functor, applicative... 各种东西.

至于一些"政治文化"因素Philip Wadler写过些文章来探讨:  
[Wadler: Functional Programming](http://link.zhihu.com/?target=http%3A//homepages.inf.ed.ac.uk/wadler/topics/functional-programming.html)  
--  
P.S 还是有公司用Haskell的:  
[Haskell in industry](http://link.zhihu.com/?target=https%3A//wiki.haskell.org/Haskell_in_industry)  
[Case Studies](http://link.zhihu.com/?target=https%3A//www.fpcomplete.com/page/case-studies)  
[FP Complete · GitHub](http://link.zhihu.com/?target=https%3A//github.com/fpco)  
[Zalora · GitHub](http://link.zhihu.com/?target=https%3A//github.com/zalora)  
[Galois, Inc. · GitHub](http://link.zhihu.com/?target=https%3A//github.com/GaloisInc)  
[Silk · GitHub](http://link.zhihu.com/?target=https%3A//github.com/silkapp) ;;;  
[Soostone Inc · GitHub](http://link.zhihu.com/?target=https%3A//github.com/Soostone)  
[Helium Systems, Inc. · GitHub](http://link.zhihu.com/?target=https%3A//github.com/helium)  
[facebook/Haxl · GitHub](http://link.zhihu.com/?target=https%3A//github.com/facebook/Haxl) ;;;  
[Well-Typed LLP · GitHub](http://link.zhihu.com/?target=https%3A//github.com/well-typed)  
[Tweag I/O · GitHub](http://link.zhihu.com/?target=https%3A//github.com/tweag)  
[Anchor · GitHub](http://link.zhihu.com/?target=https%3A//github.com/anchor)  
[Tsuru Capital · GitHub](http://link.zhihu.com/?target=https%3A//github.com/tsurucapital)  
[biegunka · GitHub](http://link.zhihu.com/?target=https%3A//github.com/biegunka)  
[capital-match · GitHub](http://link.zhihu.com/?target=https%3A//github.com/capital-match)  
[Ambiata · GitHub](http://link.zhihu.com/?target=https%3A//github.com/ambiata)  
[Scrive · GitHub](http://link.zhihu.com/?target=https%3A//github.com/scrive)  
[Haskell Blockchain Company, BlockApps, Partners With Microsoft](http://link.zhihu.com/?target=https%3A//redd.it/3qmyi2) [BlockApps · GitHub](http://link.zhihu.com/?target=https%3A//github.com/blockapps)  
[Haskell in Production at Wagon](http://link.zhihu.com/?target=https%3A//redd.it/3qmb22)














# 思考Haskell



**JAVA类型的OOP。
数据结构算法，体系结构数值运算，操作系统算法，编译原理语法语义上下文无关，组合数学，离散数学，范畴学，图论，运筹学最优化仿真，统计机器学习，自然演化算法，lamnda表达式相关《知乎小白文》+github编程入门文，数值积分，逻辑数学异或，《数学与泛型编程》小蓝书**是阅读张松不错的前提，其实不必所有都研究明白细节，甚至可以说不止上述信息，只要学懂了，会发现，这一切科学都是在研究一件事[“世界运作的规律”](#世界运作的规律的更加高明的现实建模的抽象)

我做过调度算法，语法语义相关有理解，但是编译原理还是没学明白！！！！难受！！做不出轮子，不能创造就是没学会！！！只会重复已经有的知识只是在耍流氓，根本不是前赴后继前任肩膀上前行的真正的科学应该有的样子！！

[注] 下列标题中文机器翻译英文，不一定就是相关正确的术语关键词。



## 多核并行计算



https://github.com/AccelerateHS/accelerate





Efficient Haskell Arrays featuring Parallel computation

https://github.com/lehins/massiv

















高性能计算中，多核并行编程正统选择：C++/Fortran + OpenMP C++/Fortran + MPIC++/Fortran + MPI + OpenMP 其次：Matlab的Parallel Computing Toolbox Matlab Parallel Computing Toolbox配合C++（Matlab主要负责调度）普通的科学计算（对性能没“极致”要求），Python（用Multiprocessing）、Julia、Haskell等等随便玩玩。 非要用函数式语言的话，Mathematics、Haskell可以试试。而并发编程的概念更广，可选的语言、模型、框架很多，除了上面的，Erlang、Scala Akka、Ocaml Async，Clojure atom/ref/agent。。

作者：rainoftime
链接：https://www.zhihu.com/question/30985257/answer/50200293
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



https://www.zhihu.com/question/22115397/answer/30632716


## 动态输入


https://github.com/chrisdone/dynamic











## 执行速度

https://www.zhihu.com/question/19847363/answer/17355845

## 数值计算领域Haskell或者Idris想要达到C/C++的运行效率，是否存在理论上的障碍？

Haskell非常美妙，Idris更美妙，但是目前看来效率堪忧。那么将来是否有一天，至少在数值计算领域， Haskell或者Idris对大量的通用数值计算问题（例如矩阵运算、求根、优化、微积分等等）实现媲美C/C++的运行效率（比如说同一个问题所需要的CPU小时不超过C/C++的2倍）？

  

如果存在理论上的障碍，那么Haskell或者Idris最终能达到C/C++运行效率的百分之多少？

  

Haskell或者Idris作为高级语言，和C/C++比起来当然有它们的先天不足，但是这两个语言用类型系统提供了某些在C/C++中编译器不可能知道的信息，原则上可以用来提供优化的依据，所以也有它们的优势。我认为这个问题的答案并不那么显而易见。

  

效率是可以进行一般比较的，比如，OJ上刷题的运行时间分布就可以作为一种度量。





作者：祖与占  
链接：https://www.zhihu.com/question/301111822/answer/524107809  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

> 是否存在理论上的障碍？

我觉得是不存在. 数值计算效率的瓶颈在于能否最大化利用硬件, 例如搞 CPU 的 Intel 出的 MKL 就比其他 BLAS, LAPACK 实现要猛. 所以只要搞编译器有足够的投入, Haskell 做数值计算的效率肯定是可以追赶上 C/C++ 的. 但是 Haskell 还有个操作是可以搞 EDSL, 搞 inline-*: 搞个可以编译到 C/C++ 的专门做数值计算的 EDSL, 可以在类型系统做方便生成高效代码的约束, 还可以用 inline-c/cpp/r/java/rust, 想调什么语言就什么语言, 拿 Haskell 做胶水, CPython 实现也很慢, 还不是很火, 还不是调用各种 BLAS, LAPACK 实现?

对内存分配的压力有怀疑的话完全可以让上面说的 EDSL 语义完全是 strict 的嘛, 后面还有 Linear Type, 管理好生命周期应该不会比 C/C++ 差不太远的, 或者完全 fusion 掉?

现状是 Haskell 的 de facto 编译器实现 GHC 的 SIMD 支持[还在路上](https://link.zhihu.com/?target=https%3A//phabricator.haskell.org/D4813) (GSoC 2018 搞的), Accelerate 现在的维护状况还不错, 也有 LLVM 的后端, 具体例子可以看 [Haskell for Numerics?](https://link.zhihu.com/?target=https%3A//idontgetoutmuch.wordpress.com/2017/06/02/1090/)





### 多项式
https://github.com/mokus0/polynomial


https://github.com/mokus0/polynomial



### 数值分析等等


https://github.com/ocramz/sparse-linear-algebra
















































##  hakell科学计算，矩阵计算方法数据结构利用matlab，C，python代码框架接口dll。com，,,,,,

hakell scientific calculation, matrix calculation method data structure using matlab, c, Python code framework interface dll. Com,,,,,,,,









### 大数计算



https://github.com/erikd/haskell-big-integer-experiment


















##  hakell程序设计编译发行exeDocker
 hakell programming exe
https://github.com/dkubb/haskell-builder




















### Andrios APP




https://github.com/wavewave/haskell-android-example




### Andrios APP+IOS




https://github.com/abarbu/haskell-mobile












## I/O标准输入输出



https://github.com/winterland1989/stdio












## Pandoc




https://github.com/jaspervdj/patat











## 状态自动机














https://github.com/owickstrom/motor










## 图像处理




Haskell Image Processing Library

https://github.com/jcollard/unm-hip























##  hakell符号演算定理证明coqProlog


高数线性代数
 proof of hakell symbolic calculus theorem
Linear algebra of higher numbers

https://github.com/jwiegley/coq-haskell




https://zhuanlan.zhihu.com/p/31567423

### Convert Haskell source code to Coq source code
https://github.com/antalsz/hs-to-coq
### Prolog



https://github.com/Erdwolf/prolog











##  hakell分形。自动演算
 hakell fractal. autotune








##  hakell语义语法分析编译原理


Hakell Semantic Grammar Analysis and Compilation Principle
张凇书本P179，P285












https://github.com/ollef/Earley














## Haskell的LEX和YACC
性能比 Parser Combinator 好, 错误信息也可以比 Parser Combinator 精确, GHC 自己也在用, [Purescript 最近也用 Alex+Happy 实现 concrete syntax parser 了](https://link.zhihu.com/?target=https%3A//github.com/purescript/purescript/pull/3608), 从 yacc+bison 过来的也很容易迁移, 例如 [language-c](https://link.zhihu.com/?target=https%3A//github.com/visq/language-c/blob/master/src/Language/C/Parser/Lexer.x) . Parser Combinator 用起来很 fancy, 而且更灵活, 例如 Alex+Happy 就不好描述二进制数据, attoparsec 就可以都处理. 可维护性来说我觉得两个都差不多.

  
  
作者：匿名用户  
链接：https://www.zhihu.com/question/324648976/answer/685468829  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


就是Haskell的LEX和YACC，每个正经语言都有这两个东西，没什么可说的

Parser Combinator 是Haskell独有的，别的语言也在模仿，但是没有惰性求值就是瞎折腾

具体到Parsec，可以参考我这个回答

[Parser Combinator 在语法解析的当中处于怎样的位置?​www.zhihu.com(https://www.zhihu.com/question/35778359/answer/65087586)

  
  
作者：baozii  
链接：https://www.zhihu.com/question/324648976/answer/692025252  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。











## QuickCheck




https://github.com/CIFASIS/QuickFuzz




## 概率编程





https://github.com/adscib/monad-bayes






















##  图论，数据结构预算法，知识生态轮子。证明图灵和church在工程应方面的等价性，
#It proves the equivalence of Turing and church in engineering, graph theory, data structure budget method and knowledge ecological wheel.

### purely functional data structures
https://www.zhihu.com/question/53804334

https://github.com/bos/critbit


https://github.com/tree-sitter/haskell-tree-sitter
###  hakell群论图网络规划树深林数据结构算法，利用C系语言的轮子

Hakell Group Theory Graph Network Planning Tree Deep Forest Data Structure Algorithms, Using Wheels of C-Series Language

### Haskell中如何代价最小的操作（插入、删除）一棵树？

https://www.zhihu.com/question/57629878/answer/153676557

### hash table









https://github.com/gregorycollins/hashtables



























##  lambda演算硬件电路，CPU，傅里叶变换积分变换芯片，单片机芯片电路，函数式高并发操
Lambda Calculus Hardware Circuit, CPU, Fourier Transform Integral Transform Chip, MCU Chip Circuit, Functional High Concurrent Operating System.
## CAD


























A math-inspired CAD program in haskell. CSG, bevels, and shells; 2D & 3D; gcode generation...




https://github.com/colah/ImplicitCAD



www.implicitcad.org














## ADT&GADT，更加泛型抽象接近人的思考更加有用的函数是操作系统！计算机体系结构

 ADT ; GADT, more generic Abstract close to human thinking more useful function is the operating system! Computer Architecture
https://www.zhihu.com/question/38195216/answer/75309462
Haskell可不可以在函数里面定义类型？

类似于c++中在函数里面定义struct/class，然后这个类型的作用域仅限于这个函数  
  
比如类似这样的语法(我瞎编的)：
## 逻辑演算---自然进化Hakell
 Logical Calculus--Natural Evolution Hakell




# 如何评价Haskell的Parser Generator BNFC？

它是不是直接解决了Alex和Happy用户搞不定Layout的痛点？













##  有限状态转移自动机

Finite State Transition Automata






##  ML统计学习Jullia,Python接口调用通用Manod

 ML Statistical Learning Jullia, Python Interface Calls Universal Manod

https://github.com/tensorflow/haskell

### 深度学习



https://github.com/austinvhuang/awesome-haskell-deep-learning






















### 人工神经网络




https://www.zhihu.com/question/38295817/answer/75849804



https://github.com/alpmestan/hnn












## MusicPlayer+GIF


https://github.com/music-suite/music-suite






A terminal music player based on afplay






https://github.com/potomak/haskell-player








https://github.com/lettier/gifcurry


Your open source video to GIF maker built with Haskell.


[https://lettier.github.io/gifcurry/](https://lettier.github.io/gifcurry/)






### FFmeg
Minimal Haskell bindings to the FFmpeg library




https://github.com/acowley/ffmpeg-light


### MIDI






https://github.com/5outh/Bang













## RSA


https://github.com/GaloisInc/RSA















## 数据分析


https://github.com/BinRoot/Haskell-Data-Analysis-Cookbook

### 电子表格





https://github.com/Gabriel439/Haskell-Typed-Spreadsheet-Library

### 画图

https://github.com/timbod7/haskell-chart
















## openCL





https://github.com/bgaster/hopencl









## OpenGL  

https://github.com/hasura/graphql-parser-hs



https://github.com/madjestic/Haskell-OpenGL-Tutorial
https://github.com/bergey/haskell-OpenGL-examples













## 搜索引擎

https://github.com/ndmitchell/hoogle



##  Regex?文本处理?自然语言处理NLP?编码

https://github.com/tibbe/template
https://github.com/jyp/glpk-hs

An efficient packed, immutable Unicode text type for Haskell, with a powerful loop fusion optimization framework.

https://github.com/haskell/text


https://github.com/glguy/utf8-string


https://github.com/haskell/base64-bytestring













## 泛型




https://github.com/Gabriel439/Haskell-Optparse-Generic-Library

































## 编译器
https://github.com/Marwes/haskell-compiler

Haskell to JavaScript compiler, 
https://github.com/ghcjs/ghcjs


https://github.com/ghc-proposals/ghc-proposals

https://github.com/johang88/haskellinjavascript


https://github.com/alephnullplex/cradle



A GHC-based Haskell to JavaScript compiler


https://github.com/valderman/haste-compiler


  

## Haskell LLVM JIT Compiler Tutorial

  https://github.com/sdiehl/kaleidoscope

  https://github.com/llvm-hs/llvm-hs

LLVM是一种静态类型的中间表示和相关的工具链，用于操作，优化和转换此中间形式为本机代码。LLVM代码有两种形式，二进制bitcode格式（`.bc`）和程序集（`.ll`）。命令行工具\`llvm-dis\`和\`llvm-as\`可用于两种形式之间的转换。我们将主要使用人类可读的LLVM程序集，并将其随意引用为\*IR，\*并保留单词*程序集*以表示作为编译结果的本机程序集。一个重要的注意事项是LLVM bitcode 的\[二进制格式\](http://llvm.org/docs/BitCodeFormat.html)以魔术双字节序列（0x42 0x43）或“BC”开头。

  

LLVM *模块*由一系列顶级的相互作用的函数定义，全局变量，类型声明和外部声明组成。

  

LLVM模块中使用的符号是全局的或本地的。全局符号`@`以及本地符号开头`%`。必须定义或转发所有符号。

  

```

declare i32 @putchar(i32)

```

  

  

  

  

  

www.stephendiehl.com/llvm/

## 人工智能
Algorithms from *Artificial Intelligence: A Modern Approach* by Russell and Norvig.
https://github.com/chris-taylor/aima-haskell









## Docker







https://github.com/freebroccolo/docker-haskell



https://github.com/freebroccolo/docker-haskell







## Blockchain



https://github.com/aviaviavi/legion




## 大数据,通用数据接口




https://github.com/facebook/Haxl
A Haskell library that simplifies access to remote data, such as databases or web-based services.






VCache通过ACID事务向Haskell提供扩展的持久内存。目的是支持对数据进行操作的应用程序，这些数据远大于系统内存，或者需要几乎透明的持久性。VCache使用两个主要概念：**VRef**和**PVar**。









https://github.com/dmbarbour/haskell-vcache



https://github.com/dmbarbour/haskell-vcache












## OpenQL






Write type-safe GraphQL services in Haskell







https://github.com/haskell-graphql/graphql-api

https://graphql.org






## kinectgames





A breakout game in Haskell using SDL and FRP, with Wiimote and Kinect support.





https://github.com/ivanperez-keera/haskanoid





## JVM






























#  知识生态很重要,令人敬畏的Haskell链接，框架，库和软件的辅助列表。令人敬畏的项目部分。**https://github.com/krispo/awesome-haskell    ,这个项目齐全了**
包管理
https://github.com/haskell/hackage-server

系统接口

https://github.com/yesodweb/Shelly.hs


## API

**hakell混合编程数据接口dll,良好的文件管理和I/O
**
 Knowledge ecology is very important
** hakell mixed programming data interface dll, good file management and I/O
* *


https://github.com/phadej/github
















### Haskell工具栈
https://docs.haskellstack.org/en/stable/README/


### python
A Haskell kernel for IPython

https://github.com/gibiansky/IHaskell

https://github.com/bjpop/language-python

### R

https://github.com/tweag/HaskellR

### ML


https://github.com/tensorflow/haskell



### C，DLL



https://github.com/mchakravarty/language-c-inline















https://github.com/jarrett/cpphs




**什么是fficxx？
**
fficxx（“eff fix”）是C ++的自动haskell外部函数接口（FFI）生成器。




https://github.com/wavewave/fficxx





Tools for making it easier to integrate Haskell and Objective-C

https://github.com/jspahrsummers/ObjectiveHaskell




















https://www.zhihu.com/question/39207822/answer/80352685
Haskell 与 C++的交互性如何？

[llvm-general: General purpose LLVM bindings](https://link.zhihu.com/?target=http%3A//hackage.haskell.org/package/llvm-general)  
今日发现一 llvm 相关的 package，其介绍：  
llvm-general is a set of Haskell bindings for LLVM [The LLVM Compiler Infrastructure Project](https://link.zhihu.com/?target=http%3A//llvm.org/). Unlike other current Haskell bindings, it uses an ADT to represent LLVM IR ([LLVM Language Reference Manual](https://link.zhihu.com/?target=http%3A//llvm.org/docs/LangRef.html)), and so offers two advantages: it handles almost all of the stateful complexities of using the LLVM API to build IR; and it supports moving IR not only from Haskell into LLVM C++ objects, but the other direction - from LLVM C++ into Haskell.

看题主的描述，这个package是可以把Haskell编译成的IR与C++编译好的IR相互移动，大概可以实现Haskell调用C++模块或相反，但IR本身是属于汇编level的语言，很难恢复成高级语言的，所以互译不现实


Haskell 与 C++的交互性如何？ - 王喆的回答 - 知乎 https://www.zhihu.com/question/39207822/answer/80352685











## BigWeb大前端



适合吗？网络编程优缺点
https://www.zhihu.com/question/37748492/answer/73360072


### Haskell适合做网站开发吗？有什么优缺点？

本人Haskell基本算是入门了 最近接了个网站开发的活 我先试试用Haskell来写（为了攒Haskell经验以方便找工作）看了几个Haskell做的网站感觉不错的样子。有没有哪位大神用过Haskell做网站的？听说那个Yesod很好用的样子？都有哪些优缺点，会不会有很多坑呢？网上搜了一些文章都是很多年前的了。哪位大神来简单回答一下？

https://www.zhihu.com/question/37748492/answer/73360072


作者：祖与占  
链接：https://www.zhihu.com/question/37748492/answer/73360072  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

先吐槽一下

> 最近接了个网站开发的活 我先试试用Haskell来写（为了攒Haskell经验以方便找工作）看了几个Haskell做的网站感觉不错的样子。  

如果是那种写完能拍拍屁股走人的项目用Haskell还好, 不是并且需求变动多或者略奇葩的话还是乖乖用PHP/Python/Ruby挑个实用的框架就算. Web开发的知识经验是基本上是语言无关的, 还有什么工作需要Haskell经验的请联系我, 好像并没有多少不是玩票性质用Haskell写的网站公开代码, 不要看着前端写得好看就感觉不错 (  
--  
用Haskell做Web开发最大的优点大概只有"类型安全"这点(连HTTP都搞了个[http-types: Generic HTTP types for Haskell](https://link.zhihu.com/?target=https%3A//hackage.haskell.org/package/http-types)), Rapid Prototyping这个别的语言框架都可以做到; 性能? Go, Rust这些新生代编译语言性能已经不差, 并且Haskell的内存管理性能调优监控会的人凤毛麟角, 谈不上优势.

具体到框架上, 比如说差不多跟Rails同一个量级的Yesod, 相对于别的比较全的框架比如Snap, Happstack, 更新比较快, 文档健全, 周边配套比较完善. 但是Yesod里面有很多高级的类型魔法Type Family, Template Haskell 虽然可以不需要太了解这些特性就能写出代码, 但是出了问题或者偏离框架适合的应用场景(也就是你Google或者SO找不到代码来复制粘贴)的时候就会没辄. 最近发现Thoughtbot写了个挺靠谱的例子[thoughtbot/carnival · GitHub](https://link.zhihu.com/?target=https%3A//github.com/thoughtbot/carnival). 至于更加轻量的Scotty, Spock跟Sinatra差不多个路子 (

在两三年前SPA开始慢慢出现时, 我感觉到Haskell, Scala这种语言挺适合开发API服务器. 因为服务端跟客户端通讯需要Contract, 强大的类型系统正好可以作为这个Contract(然而当时我并不知道Grape跟Swagger这种存在, 并且Haskell的类型系统不足以表达JSON Schema里面的所有约束, 或许LiquidHaskell的Reﬁnement Types能够满足, 别跟我提SOAP, WSDL), 另外一点是这些语言做JSON(反)序列化会稍稍快些, 用上Aeson会飞 (

在那段时间到Servant出来之前大概有两个东西比较出名, 一个是Silk出的[Rest](https://link.zhihu.com/?target=http%3A//silkapp.github.io/rest/), 另一个是 [postgrest](https://link.zhihu.com/?target=https%3A//github.com/begriffs/postgrest), 前者通过一套DSL来定义数据模型(资源)生成服务端客户端代码,文档, 后者直接在Postgre上套一层API, 这两个的限制在于都限制在RESTful API上可定制性不是很高. 然后轮到Servant, 简单来说Servant就是用Type-Level DSL来定义HTTP接口(不受限于REST), Type-Level DSL优势在于能够expose 类型信息, 比仅仅是结构的DSL好生成代码得多, 打这么多字好累, 看这里好了 [ChicagoHaskell/servant-presentation · GitHub](https://link.zhihu.com/?target=https%3A//github.com/ChicagoHaskell/servant-presentation/) 有代码有slides

前端部分, Yesod那些莎士比亚模板语言还算能用. 主流的[BlazeHtml](https://link.zhihu.com/?target=http%3A//jaspervdj.be/blaze/) , [Lucid](https://link.zhihu.com/?target=http%3A//chrisdone.com/posts/lucid) 都挺好看, CSS只有个 [Clay](https://link.zhihu.com/?target=http%3A//fvisser.nl/clay/). Compile2JS早点就有Fay, Haste都是实现GHC的子集, GHCJS渐渐能用, 但是为了实现Haskell的语言都拖着个Runtime, 生成的文件庞大, 也已经有FRP系统在上面实现([reflex](https://link.zhihu.com/?target=https%3A//hackage.haskell.org/package/reflex)). 语法特性类似Haskell的Purescript亲和性更加好一点, 各种binding都比较齐全, 也有自己的生态.

至于坑, 用小众语言做实际项目坑是不可避免的, 大众语言大众库即便有坑多人踩了就有PR, Workaround, Haskell不但小众而且语言问题也不好解决, 碰到个不懂的概念就好多时候就瞎眼. 开发网站用传统的服务器渲染, 在关系数据库上CRUD能很好解决. 如果网站规模变大, 组件一多(Message/Job Queue, NoSQL DB, 各种Service), Haskell有些Binding或者DB Driver质量或者维护不是很好要么就自己动手, 要么就换别的语言的库, 再跟各个组件通讯. 这种结构会给运维和系统稳定性带来不少麻烦和风险.

即便如此, 不是不推荐用Haskell, 毕竟需要更多人填坑修路






### A demo web browser engine

https://github.com/elginer/shpider


https://github.com/chrisdone/vado



### The intent is to develop a high quality, high level driver similar to pycassa.



https://github.com/Soostone/cassy













































Haskell Web Application Interface
https://github.com/yesodweb/wai


haskell-distributed.github.io

https://github.com/haskell-distributed/distributed-process
https://github.com/agrafix/Spock

https://github.com/msgpack/msgpack-haskell




https://github.com/jtdaugherty/HaskellNet










https://github.com/GaloisInc/haskell-tor
#### WSAM



https://github.com/haskell-wasm/wasm







https://github.com/mattgodbolt/compiler-explorer











Haskell WebAssembly Toolkit
https://github.com/SPY/haskell-wasm

























##### NetASM







https://github.com/NetASM/NetASM-haskell






https://github.com/HaskellCNOrg/snap-web

#### canvas




https://github.com/ku-fpg/blank-canvas








#### port




https://github.com/laserpants/hashids-haskell













#### GRPC










https://github.com/awakesecurity/gRPC-haskell/blob/master/examples/tutorial/TUTORIAL.md





https://github.com/jaspervdj/hakyll



#### CSS





https://github.com/sebastiaanvisser/clay

#### DNS




https://github.com/kazu-yamamoto/dns




#### Fast Haskell XML parser


https://github.com/ocramz/xeno


#### OpenSSL binding for Haskell







https://github.com/depressed-pho/HsOpenSSL

#### SSL


https://github.com/dpwright/HaskellNet-SSL









#### http


https://github.com/haskell/HTTP

#### Amazon Web Services for Haskell





https://github.com/aristidb/aws








#### YAML
https://github.com/dhall-lang/dhall-haskell


#### JSON文本处理







https://github.com/bos/aeson

#### Apache
https://github.com/tweag/sparkle

### SQL






https://github.com/fpco/odbc




https://github.com/paul-rouse/mysql












Opaleye是一个Haskell库，提供用于定位Postgres的SQL生成嵌入式域特定语言。如果要使用Haskell编写类型安全和可组合的代码来查询Postgres数据库，则需要Opaleye。

> “Opaleye真的很棒。你已经设法带来关于关系数据库的精彩内容并给它类型安全和组合（即Haskell的精彩内容）” - Daniel Patterson，[职位发展](http://positiondev.com/)

> “我们将它用于大多数数据库代码。它非常灵活，几乎总是像手动编写的查询一样[高效](http://ircbrowse.net/browse/haskell?id=22634197&timestamp=1460980502#t1460980502) ” - [Adam Bergmark](http://ircbrowse.net/browse/haskell?id=22634197&timestamp=1460980502#t1460980502)， [Silk.co](http://www.silk.co/)

Opaleye允许您在Haskell代码中定义数据库表并针对它们编写查询，并且旨在成为类型安全，因为如果您的代码编译，则生成的SQL查询在运行时不会失败。支持广泛的SQL功能，包括内部和外部联接，限制，聚合，不同，排序和限制，联合和差异。还提供了插入，更新和删除表的工具。使用Opaleye编写的代码可以在非常精细的粒度级别上进行组合，从而促进代码重用和高级抽象。

https://github.com/tomjaguarpaw/haskell-opaleye

https://github.com/mongodb-haskell/mongodb

https://github.com/hdbc/hdbc
### 调用其他软件的接口api
Telegram Bot API for Haskell


https://github.com/klappvisor/haskell-telegram-api


### Haskell bindings to Microsoft's Z3 API (unofficial).


https://github.com/IagoAbal/haskell-z3







### latex文本处理

https://github.com/Daniel-Diaz/HaTeX



https://github.com/batterseapower/charsetdetect

### 可视化


https://github.com/viskell/viskell

Viskell是一种用于类型（类似Haskell）的函数式编程语言的实验性可视化编程环境。该项目正在探索交互式可视化编程的可能性和挑战，并结合功能语言的优点和缺点。


### OpenCV





https://github.com/LumiGuide/haskell-opencv
















### 搜索猎犬框架






https://github.com/bitemyapp/bloodhound



Haskell有一些问题类型可以擅长，但是，如果你编写一个需要不断改变状态的程序，那么Haskell是一个糟糕的选择。 如果在对问题进行建模时，它不适合函数编程，例如编写CAD(计算机辅助设计)程序，那么OOP将是更好的选择，因为编程范例更适合模型。 但是，如果您不受这些问题的影响，那么Haskell可以成为一种很好的语言。


解决办法：利用“计算机系统接口混合编程”




























# 我认为hakell是C系语言的超集

## 合适的语法糖Package------完全可以兼容合并吞吃吸纳现有的知识轮子，算法dll






**递归是循环的超集**，有很多递归，树的递归，扩展递归，尾递归，互调递归



用“列表”构造广义表，下标层级指针模拟链表和树基石语法糖建立高楼


用超集多叉树，森林，降维实现C语言二叉树的树结构，图形学四叉树八叉树图形学多叉树

图：
广度优先------深度遍历----树的某序遍历----快不全局部最优解启发式
深度优先------广度遍历------树的层级便利------全局最优解，慢，爆炸指数增长时间复杂度算不完


用列表广义表三元组实现序号====》逻辑上的类似指针（3）在上利用已经有的C语言现成知识轮子

用尾递归实现for循环结构


用take，drop,take n构造for循环结束条件确定循环次数的语法糖

用until构造while未知循环次数结束条件的语法糖

条件表达式  ||  守卫表达式          实现if...then ...else,更加严禁定义，不能省略。

情况分析表达式 || 模式匹配       实现switch...of...选择，

？？？？？？局部变量？堆栈？链表？指针？？？全局变量？





### ADT更加抽象更加泛型，更加数学，近世代的定理很多几乎放诸四海皆可用！！抽象的魅力！！！更接近大脑思考！



## 同样是a higher level of abstraction轮子封装，模块化程序设计，软件工程，项目管理，不断降低复杂度，把已经写好的难题麻烦包装起来，


学习学的是造轮子的思路想法启发，知识创造的来龙去脉从零建立来自己心中的知识高楼，而不是背默下来琐碎的知识点，舍本逐末。

Haskell没有JAVA那么蹩脚，C语言基石，C++拿来主义什么都往上加丰富过分单调的C，各种子函数兼容成面向对象，然后C++++--简化成JAVA，JVM跨平台和网络的顺风车让他大火，接着发现同样是实现继承，多态，重载，重写和递归方法调用，单继承还行，多继承接口实现。JAVA蹩脚同时各种戴着镣铐跳舞的奇淫怪技，限制太多，现在行业JAVA的正确风气应该是提供接口这种正确的抽象而不是闭嘴硬是要继承带来各种限制。

但是，最适合跨平台网络编程那年JAVA火了，最适合GUI的面向对象火了。

如何看待Erlang之父Joe Armstrong觉得OO编程很烂？ - 大宽宽的回答 - 知乎 https://www.zhihu.com/question/29888990/answer/703226836


1. 子函数模块化封装成OOP
现在应该倡导的是“接口”种种类似manoid
2. 函数嵌套调用封装Haskell的单子函子，curry传参数，更加高明，泛函，抽象，底层


强类型，类型类，kind，type ，typeclass------更像泛型，接口，类型类，近世代数，范畴，

张松书本：

JAVAC++和haskell的17重载，多态17，
167类型类typeclass~~接口interface
197泛型实现javaVShaskell
148
199用类型系统实现完整的lamdba演算系统，一如在冯诺依曼体系上建立一个冯诺依曼体系结构的VM，bosh，实验楼，英真实验，一个操作系统虚拟机。。。异曲同工，诺兰红辣椒停机问题鸡生蛋庄生晓梦迷蝴蝶的梦中梦，无穷嵌套悖论。












# 更加高效有用的OOP抽象---面向函数对象hakell

老爷子后来认为Erlang是OOP，但是这个OOP和其他人理解的不一样：

-   常规认为OOP=封装+继承+多态
-   老爷子认为OOP=消息传递 + 隔离 + 多态，其中**消息传递最重要，隔离和多态都源自于消息传递。**

> Smalltalk的作者Alan Kay更是认为Messaging是唯一重要的事情。

从这个角度，Erlang非常OOP。**所以老爷子其实是支持OOP的，但是他支持的不是题主要问的Java那种OOP。**

  
  
作者：大宽宽  
链接：https://www.zhihu.com/question/29888990/answer/703226836  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。








```
（数字，网络，路图，树木，lambda表达式，匿名函数，函子，通用文件manod）函数是第一公民

```



## 放大招：Haskell_GUI

https://github.com/tomsmalley/semantic-reflex


https://tomsmalley.github.io/semantic-reflex/














## 用Haskell实现面向对象编程。既然现在JAVAC++之类的面向对象都是C语言模块化封装，加上各种因此专心设计的语法泛型编程技巧，

不考虑实现OO的意义，仅考虑实现OO的思路和效果（  
比如existential type class用于模拟inheritance。。



https://www.zhihu.com/question/52412654/answer/130426928

https://github.com/fumieval/objective










# haskell操作系统




https://github.com/dls/house



















##   我想到的优点


1. 更短更泛型，传入模块更加函数方便封装，传入参数可变，泛型更接近约莫近似的人脑思维方式，信息量传递的OOP更加抽象，更加高效！参数格式可变，参数类型可变，参数数量可选，更加泛型，更加模糊，更加抽象。
2. 高阶函数封装处理更加数学，证明方便高效，递归证明，可递归定义，更范畴，更加近世代数，更加像数学公式的代码。
3. 轻量化线程，纯函数，高并发，事件处理STM
4. 混合编程，逻辑演算，并行计算，数学演算用haskell计算，结果传入给其他软件混合编程（WASM）。-分形画图计算机图学直接传参调用相关开放性包画图，或者大前端画图浏览器系列编程。调用面向对象的A higher level of abstrac!   各种文件的（主要文本文件）I/O处理，文件网络Socket用Manod外界其他文件其他语言的Dll，比如面向对象传入的数据，C语言画图的框架DLL，Python机器学习包 ,Matlab科学计算M文件，R数据SPSS分析统计处理,mathematica有趣的各种骚操作......调用其他软件，比如ABBY文本识别，TXT处理，ODBCMySQL数据库，Mathpix snipping 公式识别，bat文件之类的“跨软件全操作系统混合编程”。（操作系统API调用方法）
5.  容易理解逻辑，数学怎么写，代码怎么写，方便编译正确性能保证，好看，短，脏活儿扔给计算机。
6.  不存在内存StackFlow等等因为变量意外，指针意外带来的难以发现的计算机硬件时序电路体系带来的“困惑”，纯函数，高并发，安全稳定可靠，安全性正确性能够证明
7.  从更高的角度看问题，从一个超集的更加功能强大的系统看以往简陋的系统，更加高瞻远瞩。递归是循环的超集，而Haskell是更加抽象的现实模型，比C更少“程序员需要操心的部分”，比JAVA更加高级的传入信息量的OOP。语法更加模糊接近人的思维方式，描述现实更加抽象，代码更加难懂。
8. 函数（curry高阶函数匿名函数图论网络树森林类型king类型类typeclass值type常量数值字符串数据结构+算法=程序）是第一公民！
9. 子系统是我们研究的一个小的模块化编程（OOP的对象）部分，a new level of abstract又接着封装，成为新的系统要研究的对象。系统工程https://www.jianshu.com/p/75e8d71f7d99。C语言传入参数靠的是（（（（......）））,而Haskell直接Curry，分级传参，高阶函数传入函数的函数实现函数的嵌套，已经研究好的子系统直接封装把信号传递给超系统，更利于研究实际系统的模块化编程，更利于理解“世界运作的规律”

## **别人认为的优点:**

优点

学习haskell将改变您对编程的看法。 (人们经常发现，一旦他们学会了哈斯克尔，他们就会发现自己在其他语言中编写类似于哈克尔的代码)
类型安全是否高于主流语言(空指针例外？)
类型推断意味着除非绝对必要，否则您不必担心类型。
它可以生成高性能的可执行文件。
par和pseq组合器的并行性几乎微不足道
交互式环境(hugs/ghci)可让您快速构建想法
有一个很好的支持社区(irc，邮件列表等)
非常富有表现力和简洁的语法
GHC正在积极开发和改进，包括支持GPU上的代码执行以实现高性能计算的额外优势
QuickCheck>单元测试
缺点
学习haskell会破坏所有其他语言。
进入
非常复杂
非常容易编写无人理解的神秘程序，几天后甚至不是你自己



还有人说
优点：点击 

1)Haskell是最先进的编程语言。 我做了一些研究，haskell似乎是唯一真正的最先进的编程语言。还有其他像agda和coq，但这些都是实验性的，缺乏现实世界编程的功能(例如图书馆支持)。最好投资一种最先进的编程语言。 (注意：我没有争论为什么haskell是最先进的，几乎任何其他编程语言都没有。这需要花费太多时间。所以这只是我的主观意见。同样适用于其他陈述。) (注意：我后面提到的一些功能可能是GHC特定的，但我仍然只写haskell)

2)Haskell程序员通常非常聪明。库的代码质量非常高。此外，stackoverflow的提示写得非常好，并且也处于高水平(感谢Don Stewart这样的人，仅举一例)。我认为改进编程的最佳方法之一是学习其他人的代码。 Haskell在这方面非常出色。 

3)moste OOP语言中的命令式编程已经过时。通常的副作用编程方式也是如此。但是很少有编程语言用于没有副作用的声明性编程。例如Scala，F#，Ocaml和Erlang不是副作用。 (但是，在OOP语言的学术领域也有工作，显然没有过时。考虑Alan Kay过去的工作，或者例如Smalltalk领域当前最先进的学术工作。) 

4)Haskell支持使用抽象数学概念进行编程(例如monad，functor，combinators，GADT等)。我认为这可以提高编程效率。 


5)Haskell类型系统非常灵活，支持类型推断。这大大减少了可能的错误。在编译时检查类型系统。类型系统有助于作为文档。

6)首先在haskell中实现一些最先进的概念(如QuickCheck库)。有很多有趣的扩展。

7)haskell语法设计得很好。没有不必要的括号。代码紧凑，模式匹配和列表理解的synatax非常好。像Knuth这样的人提倡有文化的编程，而haskell/GHC则支持它。

8)haskell支持懒惰评估 缺点：结果
1)这很难学，掌握haskell需要数小时，数月。没有适当的计算机科学背景就更难了。像Monads和Functors这样的东西很难理解，特别是没有数学背景。所以大多数程序员可能没有能力或愿意学习haskell。 Haskell并不“简单”。如何使用支持所有高级功能的简单语言是不可能的。
2)IDE选项不如其他编程语言好。我使用leksah作为我的IDE，它非常好，但它与Eclipse的java开发无法比较。 
3)Haskell不能用于Android或Iphone开发。相比之下，Scala可以用于Android开发，它也兼容java，这是一个巨大的优势。 
4)我认为一些图书馆缺乏支持维护和改进它们的人。我在haskell中进行语义Web编程，并且库支持可能更好。

Haskell不适合所有项目。如果你需要每毫秒的性能，C/C++仍然可能是最好的选择。因此，haskell适用于许多项目，但不是全部。 Haskell与其他编程语言相比具有许多技术优势。但是，可能存在反对使用haskell的政治原因。例如，Scala可以更好地与现有的Java基础架构集成。



 知乎作者：随心所往说：链接：https://www.zhihu.com/question/26510008/answer/33050372  ：



haskell的wiki上有汇总总结，基本上是一年两期，今年还只有上半年的第一期。

\[https://www.haskell.org/haskellwiki/Haskell\\\_Communities\\\_and\\\_Activities\\\_Report\](https://link.zhihu.com/?target=https%3A//www.haskell.org/haskellwiki/Haskell\_Communities\_and\_Activities\_Report)

  

你感兴趣可以去看看那些实践者们都是用在什么场合就大概可以体会一点haskell在工程中的优势了。

  

其实我看这个报告的时候有些失望，因为工程项目确实是少，当然这是符合haskell的热度排名情况的(常年40左右)。

  

haskell最能体现工程层面优势的项目应该是，io少，内存不紧张，业务逻辑特别复杂且多变的项目。

  











# Haskell似乎在现有语言之间进行安全性，抽象性和实用性之间的最佳权衡。OLE,DLL，LIB，混合编程，Haskell可能是最好的胶水语言。现在学术界喜欢Haskell低调研究，不想成功火起来，从而方便一些实验性的代码能够经过调试而不是错误代码就被广为流传到处使用（比如那个C操作系统注释了临时代码希望以后有人修改的，后来没改不但还把注释删除了的事情）。官网其实希望Haskell用来研究，而其他他衍生出来的商用语言用来“工业使用”。




















想要商用，想要Haskell火起来，重点就是我说的前文的生态问题的解决，让Haskell成为能够调用整个“计算机所有软硬件资源的完美接口灵活”的通用性语言，用“操作系统接口调用方法”打通所有语言之间的“壁垒”。






![业界良心](_v_images/业界良心_1560385691_8073.png)













业界良心，必须买！
![](_v_images/1560385618_13213.png)


































# 世界运作的规律的更加高明的现实建模的抽象万花筒，就是编程语言百态的根本原因


世界运作的规律是：数学家演算纸上符号，物理学家的公式模型，计算机上仿真模拟的编程实物演算（机械时代用机械结构，电气时代用电子晶体管，没差了，知乎下“纯机械时代巅峰”），所有学科所有人都在做一件事“洞悉世界运作的规律”，它是
1.  Ctrl+CV的lambda演算复读机本性
2.  兔子细胞繁殖半衰期Fibonacci，数列穷举法的指数增长，阶乘增长函数，整数之间除法必然遇到的素数相关“数学皇后数论”的问题
3.  是高维俯瞰的复数，4元数，时间维相对论
4.  是不断重复自己的分形，
5.  是精美绝伦的对称，杨振宁口中的21世纪的对称，物理对称和不动点的关系------那位女科学家
6.  是泛函找最小作用量的最优化，是量子光学，量子电动学等最优化的计算
7.是统计机器学习找规律的近似，近似是很有效的物理研究思想  
8.  是各种群，范畴，矩阵，函数，算子等等变换下不变量，守恒量，特征根函数不动点
9.  是离散和连续，量子化和数学极限，集合论和无穷维线性代数（量子力学用到），
10.  是场论，是图论，是复分析可视化，
11. 是状态时序电路的有限状态直接不断跳转的“自动机”
12. 是逻辑电路，Haskell给定输入有确定输出的输出的纯函数
13. 是机械仿真，电子仿真，系统工程仿真模拟
14. 是Taylor展开机械控制的线性化处理近似，是傅里叶拉普拉斯的信号处理
15. 是编码理论通信鼻祖的，信号论，信息熵编码理论香农大大，信号处理奥本海默牛人
16. 是对称调用自己，递归（子集循环）的无脑重复，代码复用下的自然。
17. 是曲率纤维丛研究下的空间
18. 是拓扑研究中的不变量
19. 是声振动模态，光电量子电磁场动力学，热振动热能，力牛顿时代形象生动的描述。
20. 是不同研究模式下的不同范式。。。。。。。

{--
尽管牛顿自己也没有说过力这种抽象，《原理》定义的是动量，导数关系导出的元素只是研究对象，不是最本质的定义实际意义的量，或者根本没有所谓最本质的东西，场论如果物质分布电磁场变成物质那么梯度，旋度，导数就是想要的东西了。这一切都只是符合现实的规律二律背反的 建模方式，并不知道那个是对的，或者都对，都是“冥冥中的世界运作的规律的抽象近似模型”，谁的描述方法更加精准形象就用谁的。
科学就是要自洽，严谨，满足客观实验规律，能用来指导生产生活才能被成为科学，而不是谬论。
--}

对于编程语言，我的观点觉得：没人关心你到底用的什么语言写的程序代码，用户只关心稳定，安全好用。老板只关心开发周期，开发成本，项目管理计划于安排。甚至连写代码的人都不关心这个语言还是那个语言，只要有好的知识轮子可以用，就是好语言。为了做出好的轮子，我们都不得不认真比较，毕竟每种编程语言就像每个学科不同的研究建模数学表达方式，都是为了一个目的“世界运作的数学原理”。
我感觉Haskell有着很多优点是其他语言赶不上的，而且，我觉得更重要的不是各种语言，而是定义一种所有语言通用的DLL,LIB，OLE之类的跨平台的所有编程语言都能进行交互，互相调用的“操作系统接口--协议--调用方法---或者说是约定”，具体说来就是一种通用的数据格式，代码模块化格式，方便各种语言互相调用（就像是数学方言之间的相互翻译和等价证明），Haskell最美的地方大概就是和数学接近吧！

如果所有编程语言都能通过“Haskell”作为桥梁接口连接沟通，而Haskell又能与数学语言翻译的话，那么，描述世界运作的“自然哲学里面的数学原理”就能通过Haskell完美诠释，以后数学书上那些公式就能很方便地编程计算机上的代码，用光速仿真模拟世界运作的规律！


# 很多时候，决定脑袋里面思考内容的是人们看到什么。














































































































































































































































































































































































