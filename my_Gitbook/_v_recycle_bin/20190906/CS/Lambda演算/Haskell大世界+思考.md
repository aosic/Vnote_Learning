[TOC]







缘起，其实很多时候科学研究世界运作的规律，殊途同归。

陆陆续续接触λ演算，Haskell这类Fp也有一年多了，此文算是给自己填坑小结吧，也是为了让更多人看到λ演算大世界的美妙。

fp话题有点大，定题为 Haskell大世界 好了。


[不动点](https://www.zhihu.com/question/263431508/answer/574084280),这个问题我当时刚看Haskell免费电子书，发现实际上自己认识不到位呀。看书很多时候要有一定的基础去看才能触类旁通，举一反三，很多名字不一样的东西其实就是一个东西，一个思路。一个比较具体的例子就是，学完C看张淞的书，发现就像囫囵吞枣，学完JAVA再看，深入理解了很多，在期间接触很多相关的东西之后再看，笔记已经在书页挤得满满的了。很多书都是，在新认知层面再看，发现很多以前自己没有发现的认识。张淞的书第一版我最珍重的是他章末和扉页最后一段那些参考文章的推荐和介绍，感觉这才是他遗留在沙滩上的脚印，适合当初我的水平接触，现在很官方正式的引文倒是让我有点不知道这么多引文不知道点那个的迷糊。

[haskell大型项目](https://www.zhihu.com/question/340251796/answer/808338345).其实近期内我相关思考，精炼的主要观点就在这个回答里面，太长不看的人士，可以看这个回答。

水平有限，不喜请喷，欢迎交流.

# 基石般灵活表现自由的抽象范式

认识一个企业后端工作的的程序员，问到函数式编程

他说：“没什么，就是lambda表达式代码写成一行的一些语法特点，常见，很多语言都有，没什么稀奇的。”

我犹豫了下没问，心想，这，只是表面吧？最底层用lambda演算实现计算机演算，从最基本的原理上就不同于改进图灵机的冯诺依曼体系，church的图灵机本质上就是不一样的东西吧？

>维基：
可图灵指在可计算性理论中，编程语言或任意其他的逻辑系统如具有等用于通用图灵机的计算能力。换言之，此系统可与通用图灵机互相模拟。这个词源于引入图灵机概念的数学家艾伦·图灵（Alan Turing）。虽然图灵机会受到存储能力的物理限制，图灵完全性通常指具有无限存储能力的通用物理机器或编程语言==可实现死循环，区分物理机不能实现无限内存。

同样解决希尔伯特的数学可解性问题，证明了逻辑上等价，二律背反。如果在同一系统能够被不同理论描述，不同理论结论的自洽和相互转换等价性不是显然的吗？

皮亚诺算术，递归。“我们不能定义数字，因为那更加难以理解”。一个大佬回答我的关于形式化量词如何用代码实现的问题的时候，问我，“你如何不用递归来定义无穷集？”我愣住了，对哟。

观点：
>图灵完备参见这个[相关链接](https://www.zhihu.com/question/20115374)
量子力学里面的正交完备基，机器A和图灵机都可以归一化为人类在纸上能够进行的计算==一切可解问题==图灵机==等价于lambda演算==无限内存.
完备性的解释。包括：[代数闭域](http://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%25E4%25BB%25A3%25E6%2595%25B0%25E9%2597%25AD%25E5%259F%259F)(algebraically closed field）、[紧化](http://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%25E7%25B4%25A7%25E5%258C%2596)(compactification）或[哥德尔](http://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%25E5%2593%25A5%25E5%25BE%25B7%25E5%25B0%2594/152476)不完备定理。主要还是数理逻辑的内容。
根据图灵假说, 任何可计算的都可以用图灵机表达, 也就是说目前没有比Turing Machine更强大的系统, 所以可以粗略地说如果L图灵完备, 则 L = Turing Machine. 因此"两种语言都是图灵完备, 所以这种的程序另一种至少也能写" 是可以这么说的, 因为两者的表达能力都等于图灵机.
Oracle Machine比Turing Machine更强。不过物理上能造出的最强的机器可能就是图灵机了……


我理解中的Lambda是改进图灵机的冯诺依曼体系等价理论体系，更加基础的抽象。

感觉现在计算机实现运算的基石是组成原理第六章，那个变量里面计算倒腾01变量（邓俊辉的数据结构课前几节还有一个形象的TuringMechine），然后church的底层实现演算是lambda演算，具体实现过程看[面向小白的lambda演算](https://zhuanlan.zhihu.com/p/30510749)（这文章跟着用白纸手算一遍很受启发），然后我推荐看这个[Github项目中文lambda演算的介绍，包括Haskell的翻译。](https://github.com/txyyss/Lambda-Calculus)，看完，跟着演算一边PDF很有感觉。

然后在已经建好的大楼上添砖加瓦，（造轮子的人才应该被人尊敬，而不是倒卖知识自己还没学明白的那些靠资源信息不对等挣钱的），我们需要实现的是添砖加瓦，《函数式编程入门》张凇的书应用实例多，有思考，启发性强，让我读了很多遍，很有启发，最开眼的是他把haskell数学公式形式和代码完美结合，展示出来一种很自然的感觉。《魔力haskell》这本书我看的比较晚，但是看到后期果然发现不同书籍之间有互补的作用，函子->应用函子->单子，我感觉韩冬老师的书讲的太好了，虽然有些时候半页看半天才看懂（那题用flodl实现flodr的）。

跳出冯诺依曼的魔咒，haskell函数式编程也是很高明的抽象。

简单来说，我感觉λ演算就是另一种更基础的抽象，生活中数学里各种“操作”的抽象就是lambda演算代入，模式匹配就像是“选择判断”的抽象，不动点是“重复操作”的抽象，而递归仅仅是“重复+判断出递归基”罢了，循环不过是尾递归系统栈改成用户栈调用优化罢了。

这些同构的系统就能证明相互性，就能互相转换，不同理论体系描述世界的方式不同，也就殊途同归了。就像 定理之间的组合也会存在“最基本的那么几条公理”能张成整个“理论空间”，比如欧几里几何。或者说命题逻辑里面的“联结词完备集”，{非，或/与}和{与非联结词}是可以转换的，再如量子力学九种形式.......


无穷集如果是递归定义的，这说明能用归纳法去证明其正确性，而和自然数同构的很多系统也能用N的方法来研究就显而易见了，这大概就是 数学之美 吧。

## 编程语言是什么？


借用Mooc教授讲编译原理的时候说的话，大概意思是：
>新语言最贵的是培训，几个人弄明白内核就够了，新语言是因为旧社区不能推倒重来，干脆换个名字叫新语言。

每种语言只是自己适用场合不一样，知识轮子生态不一样而已。

C系语言都差不多，很多语言我称之为打包C，重点是生态，知识轮子和针对性，便捷性。

Api程序员的调侃其实也说明了，我们就是不断打包已有知识的基础上，减轻脑力复杂度，进而研究更加深入问题的，但是黑箱子可以不代表可以永远“不求甚解”，必须懂构造思路逻辑方法或者基础自学操作常识性认识，需要“求甚解”的时候要有能快速学会的能力。

函数式系语言也一样，haskell纯函数式，对我来说比较有特殊意义。

复制粘贴程序员的笑话说明一点，人力优势穷，计算机知识帮助我们拓展思路能力辅助器官，好处是：光速大内存精准记忆和可重复性强。

编程语言说到底只是人机交互的桥梁，文学编程mma/jupyter就很有感觉，但我感觉lambda演算上层建筑fp能给你更加好的体验。

这些fp代码长着就像算法流程说明书，只不过是他恰好能运行罢了。




函数是第一公民（数字，网络，路图，树木，lambda表达式，匿名函数，函子，通用文件manod......万物皆函数的角度）



# 推荐论文

[类型系统λ学习笔记参考知乎专栏（黑洞）](https://zhuanlan.zhihu.com/p/32182423?utm_source=wechat_session&utm_medium=social&utm_oi=749297898931384320)

千里冰封欧林猫他们在干的，建议围观。

[文章](https://github.com/mitchellwrosen/haskell-papers)

[论文](https://github.com/cohomolo-gy/haskell-resources)

[相关问题搜索引流](https://www.zhihu.com/question/315005729/answer/618034280  )

wiki上很多相关专题都值得看。

论文检索，还是去专业的地方吧。

个人觉得，张淞的书看着就像是论文学习笔记，特别是第二版。

##  大佬建议
>TBH, Haskell 也快奔三到头, 在上面发表的论文真多如牛毛, 如果没有一个方向或者目的, 列举出来的意义也不是特别大. 下面按方向随便大概列举一下:
>### Meta
>A History of Haskell: Being Lazy With Class - 到目前为止 Haskell 前半生的故事, 虽然后期 GHC 的实现翻天覆地, 但是还是可以了解到 Haskell 设计的初衷和其中一些概念(例如 Monad)引入的历史, 还有唐凤用实现 Perl6 当 TAPL 练习题干进 Haskell 2010 标准作者之一的故事之类的. 以及对 [为什么 Haskell 始终没法流行呢？](https://www.zhihu.com/question/39115733/answer/79902920) 
>Confessions of a Used Programming Language Salesman - Getting the Masses Hooked on Haskell, Haskell 98 标准作者之一 Erik Meijer 把 Haskell 的 idea 到各个语言"发扬光大"过程中的心路历程, 虽然后面搞了 rx, Dart async spec 这种事情没记录进去.
>### Haskell 实现 
>这个真不是我随便就可以列完整的列表, 而且分支也很多, 我来整个 meta-list:
>[A Haskell Implementation Reading List](https://link.zhihu.com/?target=http%3A//www.stephendiehl.com/posts/essential_compilers.html)
>[ReadingList - GHC](https://link.zhihu.com/?target=https%3A//ghc.haskell.org/trac/ghc/wiki/ReadingList)
>[tweag/asterius](https://link.zhihu.com/?target=https%3A//github.com/tweag/asterius/blob/master/docs/readings.md)
>[Haskell 实现相关的 reading list](https://link.zhihu.com/?target=https%3A//archive.fo/RglyT)
>以及无脑推荐两个 Simon 的所有 paper
>### 类型系统
>看 Richard A. Eisenberg 的 PhD 论文 [DEPENDENT TYPES IN HASKELL: THEORY AND PRACTICE](https://link.zhihu.com/?target=https%3A//cs.brynmawr.edu/~rae/papers/2016/thesis/eisenberg-thesis.pdf), 找参考文献看应该会比较好。
>
>### 语言抽象/模式
>
>Monad 的推荐看 Philip Wadler 的 - [有没有对Haskell中理解monad比较好的代码例子？](https://www.zhihu.com/question/64207539/answer/217887930)
>Applicative: [Idioms: applicative programming with effects](https://link.zhihu.com/?target=http%3A//strictlypositive.org/Idiom.pdf)
>其他的可以在 [Typeclassopedia - HaskellWiki](https://link.zhihu.com/?target=https%3A//wiki.haskell.org/Typeclassopedia) 找, Profunctor 最近的还没有。
>Fun with Semirings 这种玩代数结构也挺好玩的。
>Parser Combinator, 还是推荐 Graham Hutton, Erik Meijer, 复杂的都要自己看实现. 找更原始的可以看 Parsing Techniques 第二版的参考文献.
>Recursion Schemes, Paper 都挺不好看的, 看 [Adventures in Uncertainty](https://link.zhihu.com/?target=https%3A//blog.sumtypeofway.com/) 的介绍好多了, 其他可以到 [passy/awesome-recursion-schemes](https://link.zhihu.com/?target=https%3A//github.com/passy/awesome-recursion-schemes) 
>### 问题解决方案
>估计这个[Functional Pearls](https://link.zhihu.com/?target=https%3A//wiki.haskell.org/Research_papers/Functional_pearls) 密集区了
>Expression Problem: Data types a la carte
>Oleg Kiselyov 问题终结者: Extensible Effects 系列, Implicit Conﬁgurations, Reﬂection without Remorse
>
>succinct data structure 得看 ekmett 的 talk 和库，ekmett 所以库相关的都推荐
>越列越多, 都看得过来吗?
>
>[编辑于 2019-03-09](/question/315005729/answer/618034280)


# Haskell在工业界有哪些实际的应用？

感觉Haskell更多地是作为研究性语言存在的，有哪些公司把Haskell作为开发语言？

https://www.zhihu.com/question/36325022/answer/67674150

https://www.zhihu.com/question/20246934/answer/15262041

https://www.zhihu.com/question/54095611/answer/137873645



>https://www.zhihu.com/question/41139361/answer/90430564
>著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
>看下[A History of Haskell](http://link.zhihu.com/?target=http%3A//research.microsoft.com/en-us/um/people/simonpj/papers/history-of-haskell/) , [Every Language Fixes Something](http://link.zhihu.com/?target=http%3A//www.solipsys.co.uk/new/EveryLanguageFixesSomething.html), Haskell的诞生本身就是出于研究目的的, 并没有想去解决工业界的什么痛点或者难点(如果有软件危机也不是单靠换个语言来解决的), 而且Haskell跟流行的语言一点都不像.\
>老实说到上个世纪或者GHC没有主导Haskell实现之前(严重地说可以到2010年), Haskell的生产力(不是语言表达力, 主要是库), 培训成本跟主流的语言还是有不少差距, Real World Haskell算是个里程碑, 然而现在也已经过时.
>主流语言的变化也逐渐变快, C++/Java也吸收了很多函数式编程语言里的元素, Rust也把之前不少PLT研究积累的成果工业化. 虽然Haskell没有进入主流但是也影响了不少其他语言, 像Java, Swift里的Option, Elixir里的with都脱胎于Haskell的Maybe Monad, 还有coffeescript之类的语言.
>然而Haskell里面各种概念的演变发展是一般的程序员没法想象的, 要让所有程序员理解Monad的怕是要写无数个"深入浅出"的教程, 以及各种以"如何理解", "怎么用简单的语言"开头的知乎问题还有下面无数不同观点的答案, 何况还有free monad, comonad, functor, applicative... 各种东西.
>至于一些"政治文化"因素Philip Wadler写过些文章来探讨:  
>[Wadler: Functional Programming](http://link.zhihu.com/?target=http%3A//homepages.inf.ed.ac.uk/wadler/topics/functional-programming.html)  
>P.S 还是有公司用Haskell的:  
>[Case Studies](http://link.zhihu.com/?target=https%3A//www.fpcomplete.com/page/case-studies)  
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
>[Haskell in industry](http://link.zhihu.com/?target=https%3A//wiki.haskell.org/Haskell_in_industry)  



# 关于fp的一些思考

我甚至曾经冲动地认为Fp是C系语言的超集，是上游的更原始普适有效的抽象，才能更方便直接利用做好的代码知识轮子。

C用内存作为装数据的没标签透明杯子抽象方式，haskell用monad装数据，但是有对应的管道类似的操作传来传去很费劲。
处理副作用问题的时候不太方便，但（存数+类型标签）的盒子抽象，精美的类型系统能自由安全处理，推导数据类型的正确性和安全性。

C系语言类型解析形式是int foo=1;告诉编译器记住foo地址的二进制串解释方式是int的字符编码约定。类型转换，改数据就直接弄foo位置存储的bite位，这会带来"价值百万的NULL错误"问题或者内存泄漏之类的。haskell则是要新绑定一个（值+值的类型标签)盒子，安全的类型转换。这样也有缺点，打印出中间结果比较费劲，函数调用深度debug比较麻烦（不过写的时候能调通的代码基本没什么bug）。

惰性求值有它的好处，从《Why Functional Programming Matters》中知晓惰性计算可以带来哪些好处。但是不但给复杂度分析，算法分析带来困惑，内存处理空间分析也很难想清楚，《魔力haskell》提到“任务盒堆积问题”。

thunk任务盒子堆积要seq,如果只想一些中间变量有用保存结果，没必要保存中间变量，飞速发展的haskell，好像已经有办法了，记得好像大概可能也许看过？Dynamic动态类型？unsafeCoerce强制类型转换？具体忘了。

参数度多种类型的多态也能做，实现函数重载，java可以接口，haskell可以“类型类”，kind*。

lambda表达式是《C++Primer》说的是一种可调用对象callable object的抽象，很适合函数调用函数，curry柯里化把多元函数看成一元函数串起来，实现任意参数（lift2A升格也行，但是任意函数升格还是不如串起来运行时决定）。

模式匹配处处都是，其实模式匹配是生活中“各种抽象的情况下对应分类处理方式”的抽象，haskell处处可见，可以看成C系语言的选择抽象，如果看成循环判断出口的话，可以定义出循环结束，当然也可以定义出不动点函数重复计算的出口，递归调用的结束递归基。

元编程，泛型等haskell都很优雅地完成任务，值得一提的是纯函数在并行处理的时候的优越性，学过操作系统的时候一定曾经被处理流水的各种算法弄蒙逼了吧，这里有更加安全的STM，更好的事务管理，更好的并行并发。

haskell和数学主流描述世界的抽象描述方式极其逼近，我想类比
“Mathematic is more in need of good notations than of new therems.------A.Turing ”，
一种更高明的编程方式比新的源码库包装起来的代码知识轮子更重要，
“CS is more in need of good Abstract description pattern  than of new  code library”。

描述世界运作的规律（一可以用各种数学方言来描述，各种数学理论公式定理），既可以用这种编程语言实现，也可以用那种编程语言实现，但是不变的是写在抽象符号表示的那些“数学语言”。

就像计算机可以像差分机一样用机械结构实现，用电子电路实现，甚至用量子物理等，各有优点，尽管长得很不一样。

但是，图灵机自动机上下文无关那些《计算机理论》类似的符号化的抽象规律描述的本质规律，才是真正的科学指导纲领。





## 递归是循环的超集。

任何的递归都可以用栈来替换实现。递归可以用不动点定义，不动点是重复的抽象，递归已经包括了重复结束条件的抽象。

栈能把递归实现非递归模式，或者说，递归是系统栈调用，效率不高因为《操作系统》保存环境恢复现场多余信息，用户自己设计一个栈只存储用得上的值，所以用户栈定义的非递归效率高。

一些编译器会把尾递归优化为循环。

而越抽象，越放之四海皆可用，越抽象也越难直接写出来且没有bug，要有很强的造轮子能力。

 ADT更加抽象更加泛型，更加数学，可用范围更广！

抽象的魅力！

更接近大脑思考！



## 同样是a higher level of abstraction轮子封装。

**模块化程序设计，软件工程，项目管理，不断降低复杂度，把已经写好的难题麻烦包装起来。
**

>学习学的是造轮子的思路想法启发，知识创造的来龙去脉从零建立来自己心中的知识高楼，而不是背默下来琐碎的知识点，舍本逐末。
Haskell没有JAVA那么蹩脚，C语言基石，C++拿来主义什么都往上加丰富过分单调的C，各种子函数兼容成面向对象，然后C++++--简化成JAVA，JVM跨平台和网络的顺风车让他大火，接着发现同样是实现继承，多态，重载，重写和递归方法调用，单继承还行，多继承接口实现。JAVA蹩脚同时各种戴着镣铐跳舞的奇淫怪技，限制太多，现在行业JAVA的正确风气应该是提供接口这种正确的抽象而不是闭嘴硬是要继承带来各种限制。
但是，最适合跨平台网络编程那年JAVA火了，最适合GUI的面向对象火了。
如何看待Erlang之父Joe Armstrong觉得OO编程很烂？ - 大宽宽的回答 - 知乎 https://www.zhihu.com/question/29888990/answer/703226836




# 世界运作的规律的更加高明的现实建模的抽象万花筒，就是编程语言百态的根本原因

1. 子函数模块化封装成OOP
现在应该倡导的是“接口”种种类似manoid
2. 函数嵌套调用封装Haskell的单子函子，curry传参数，更加高明，泛函，抽象，底层


强类型，类型类，kind，type ，typeclass------更泛型，类型类，近世代数，范畴------>研究世界的数学抽象方式。



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
20. 是不同研究模式下的不同范式
21. ......


{--
尽管牛顿自己也没有说过力这种抽象，《原理》定义的是动量，导数关系导出的元素只是研究对象，不是最本质的定义实际意义的量，或者根本没有所谓最本质的东西，场论如果物质分布电磁场变成物质那么梯度，旋度，导数就是想要的东西了。这一切都只是符合现实的规律二律背反的 建模方式，并不知道那个是对的，或者都对，都是“冥冥中的世界运作的规律的抽象近似模型”，谁的描述方法更加精准形象就用谁的。
科学就是要自洽，严谨，满足客观实验规律，能用来指导生产生活才能被成为科学，而不是谬论。
--}

对于编程语言，我的观点觉得：没人关心你到底用的什么语言写的程序代码，用户只关心稳定，安全好用。老板只关心开发周期，开发成本，项目管理计划于安排。甚至连写代码的人都不关心这个语言还是那个语言，只要有好的知识轮子可以用，就是好语言。为了做出好的轮子，我们都不得不认真比较，毕竟每种编程语言就像每个学科不同的研究建模数学表达方式，都是为了一个目的“世界运作的数学原理”。
我感觉Haskell有着很多优点是其他语言赶不上的，而且，我觉得更重要的不是各种语言，而是定义一种所有语言通用的DLL,LIB，OLE之类的跨平台的所有编程语言都能进行交互，互相调用的“操作系统接口--协议--调用方法---或者说是约定”，具体说来就是一种通用的数据格式，代码模块化格式，方便各种语言互相调用（就像是数学方言之间的相互翻译和等价证明），Haskell最美的地方大概就是和数学接近吧！

如果所有编程语言都能通过“Haskell”作为桥梁接口连接沟通，而Haskell又能与数学语言翻译的话，那么，描述世界运作的“自然哲学里面的数学原理”就能通过Haskell完美诠释，以后数学书上那些公式就能很方便地编程计算机上的代码，用光速仿真模拟世界运作的规律！




# Haskell，你就是话题之王？ 


数据结构算法，体系结构数值运算，操作系统算法，编译原理语法语义上下文无关，组合数学，离散数学，范畴学，图论，运筹学最优化仿真，统计机器学习，自然演化算法，lamnda演算相关+github编程论文项目，数值积分，逻辑数学异或，《数学与泛型编程》小蓝书......

很久我才明白一个道理：其实不必什么事情都一个人研究明白细节，因为Haskell研究科学，甚至可以说包括的不止上述信息。

只要学懂了，会发现，这一切科学发展思路基石都统一于研究一件事“世界运作的规律”

我做过调度算法，语法语义相关理解一些，但是编译原理还是没学明白！

难受！！做不出知识轮子，不能创造举一反三就是没学会！只会重复已经有的知识只是在耍流氓复读机，根本不是前赴后继前任肩膀上前行的真正的科学应该有的样子！！

注意，下列文章例子项目只是恰巧看到的距离或者常见的引导链接，实际上我觉得信息爆炸的互联网比起来，下面的范围连个粗浅的简要目录都算不上，

但是**Haskell就是这么宽广的一个大世界!**

[注] 下列标题中文，翻译成英文，不一定就是相关正确的术语搜索关键词，找准方向，深入了解，记得找准英文关键词。

[注] 下列链接只是为了说明Haskell的波澜壮阔，实际上互联网是很宽广的大海！

曾经，我有过一个想法，如果全世界的人共同维护一颗知识笔记书，让索引变得方便，共同编译一份项目，分好类，做好索引分享的话，很多前任走过的坑后人就不会再无效信息或者过期信息间不断跳转了，我本来还想做个项目，后来发现everything之类的项目，类似的我觉得不需要新建，跟着完善也不错，比如共同编辑的维基索引，领域相关的博客论坛社区，[https://wiki.haskell.org/Haskell](https://wiki.haskell.org/Applications_and_libraries/Mathematics)

喜欢Haskell的小伙伴一定能畅游到自己喜欢的地方！看烦了可以直接滚动屏幕到文末总结部门






# 令人敬畏的Haskell链接，框架，库和软件的辅助列表

https://github.com/krispo/awesome-haskell ，这里叫介绍了很多很不错的Haskell,我翻译在专栏就有。


包管理
https://github.com/haskell/hackage-server

系统接口

https://github.com/yesodweb/Shelly.hs

#  知识生态！

Hackage,Stackage,Hoogle,Github,wiki相关，stack flow相关，社区论坛 Etc.



## DSL领域编程

##用haskell单子优势处理JSON，XML,字符串，websocket，HTTP,序列化,Protobuf,MessagePack，网页模板编程，或者生成SQL，parser解析器......



Haskell处理XML
https://blog.csdn.net/kowity/article/details/8134477

## DSL编译原理翻译其他语言，语法解析器+模板编程+泛型编程

应用例子  http://www.aqee.net/post/why-haskell-is-worth-learning.html


##  模板template编程

```haskell
import Control.Lens.TH
data position = position {posX:: Double,posY::Double}
makeLensess ''Position--AST抽象语法树abstract syntax tree
```
Q单子

拼接

reify


```haskell
 

```

## 模板编程
其实这个我是在魔力haskell第一次看到的haskell相关库的使用介绍的，韩冬不愧是使用haskell做工程的背景。





## 泛型




https://github.com/Gabriel439/Haskell-Optparse-Generic-Library




www.voidcn.com/article/p-kaljxhgr-qd.html






代数类型是指和sum类型，积product定义出来的数据类型，递归类型









## 编译器
https://github.com/Marwes/haskell-compiler

Haskell to JavaScript compiler, 
https://github.com/ghcjs/ghcjs


https://github.com/ghc-proposals/ghc-proposals

https://github.com/johang88/haskellinjavascript


https://github.com/alephnullplex/cradle



A GHC-based Haskell to JavaScript compiler


https://github.com/valderman/haste-compiler


## 解析器paser

optparse-applicative命令行参数解析器函数库

https://hackage.haskell.org/package/optparse-applicative



  

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






## 并行并发
并行parallel函数库



并发forkIO


STM


aysnc



## 语言扩展和程序标记ghc表一编译相关技巧


{-#...#-}


{-#UNPACK#-}





编译选项


-Wall打开所有警告
运行分析-prof
-threaded多线程
-stat链接器linker用静态库打包exe会很大，但是环境要求不太高。放哪儿都能用。

```haskell
module Main where
main = print (fib 30)
fib n= if n<2 then 1 else fib(n-1)+fib(n-2)
{-
ghc - prof -fprof-auto -rtsopts Main.hs
Main.exe +RTS -p在Windows下
./Main +RTS -p

-}
```

```haskell

module Main where
main = print (fib 30)
fib n=let fibs = 0:1:zipWith (+) fibs (tail fibs) in fibs !! n


```

RTS -p时间消耗

RTS -h内存消耗

```haskell
Main.exe +RTS -h
hp2ps Main.hp
open Main.ps

```

```haskell


```



##  Regex/文本处理/自然语言处理NLP

https://github.com/tibbe/template
https://github.com/jyp/glpk-hs

An efficient packed, immutable Unicode text type for Haskell, with a powerful loop fusion optimization framework.

https://github.com/haskell/text


https://github.com/glguy/utf8-string


https://github.com/haskell/base64-bytestring






### latex文本处理

https://github.com/Daniel-Diaz/HaTeX



https://github.com/batterseapower/charsetdetect





## 快熬出头的Haskell大前端



### 适合吗？网络编程优缺点
https://www.zhihu.com/question/37748492/answer/73360072


 Haskell适合做网站开发吗？有什么优缺点？

本人Haskell基本算是入门了 最近接了个网站开发的活 我先试试用Haskell来写（为了攒Haskell经验以方便找工作）看了几个Haskell做的网站感觉不错的样子。有没有哪位大神用过Haskell做网站的？听说那个Yesod很好用的样子？都有哪些优缺点，会不会有很多坑呢？网上搜了一些文章都是很多年前的了。哪位大神来简单回答一下？

https://www.zhihu.com/question/37748492/answer/73360072


作者：祖与占  
链接：https://www.zhihu.com/question/37748492/answer/73360072  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

先吐槽一下

> 最近接了个网站开发的活 我先试试用Haskell来写（为了攒Haskell经验以方便找工作）看了几个Haskell做的网站感觉不错的样子。  
如果是那种写完能拍拍屁股走人的项目用Haskell还好, 不是并且需求变动多或者略奇葩的话还是乖乖用PHP/Python/Ruby挑个实用的框架就算. Web开发的知识经验是基本上是语言无关的, 还有什么工作需要Haskell经验的请联系我, 好像并没有多少不是玩票性质用Haskell写的网站公开代码, 不要看着前端写得好看就感觉不错
用Haskell做Web开发最大的优点大概只有"类型安全"这点(连HTTP都搞了个[http-types: Generic HTTP types for Haskell](https://link.zhihu.com/?target=https%3A//hackage.haskell.org/package/http-types)), Rapid Prototyping这个别的语言框架都可以做到; 性能? Go, Rust这些新生代编译语言性能已经不差, 并且Haskell的内存管理性能调优监控会的人凤毛麟角, 谈不上优势.
具体到框架上, 比如说差不多跟Rails同一个量级的Yesod, 相对于别的比较全的框架比如Snap, Happstack, 更新比较快, 文档健全, 周边配套比较完善. 但是Yesod里面有很多高级的类型魔法Type Family, Template Haskell 虽然可以不需要太了解这些特性就能写出代码, 但是出了问题或者偏离框架适合的应用场景(也就是你Google或者SO找不到代码来复制粘贴)的时候就会没辄. 最近发现Thoughtbot写了个挺靠谱的例子[thoughtbot/carnival · GitHub](https://link.zhihu.com/?target=https%3A//github.com/thoughtbot/carnival). 至于更加轻量的Scotty, Spock跟Sinatra差不多个路子 (
在两三年前SPA开始慢慢出现时, 我感觉到Haskell, Scala这种语言挺适合开发API服务器. 因为服务端跟客户端通讯需要Contract, 强大的类型系统正好可以作为这个Contract(然而当时我并不知道Grape跟Swagger这种存在, 并且Haskell的类型系统不足以表达JSON Schema里面的所有约束, 或许LiquidHaskell的Reﬁnement Types能够满足, 别跟我提SOAP, WSDL), 另外一点是这些语言做JSON(反)序列化会稍稍快些, 用上Aeson会飞 (
在那段时间到Servant出来之前大概有两个东西比较出名, 一个是Silk出的[Rest](https://link.zhihu.com/?target=http%3A//silkapp.github.io/rest/), 另一个是 [postgrest](https://link.zhihu.com/?target=https%3A//github.com/begriffs/postgrest), 前者通过一套DSL来定义数据模型(资源)生成服务端客户端代码,文档, 后者直接在Postgre上套一层API, 这两个的限制在于都限制在RESTful API上可定制性不是很高. 然后轮到Servant, 简单来说Servant就是用Type-Level DSL来定义HTTP接口(不受限于REST), Type-Level DSL优势在于能够expose 类型信息, 比仅仅是结构的DSL好生成代码得多, 打这么多字好累, 看这里好了 [ChicagoHaskell/servant-presentation · GitHub](https://link.zhihu.com/?target=https%3A//github.com/ChicagoHaskell/servant-presentation/) 有代码有slides
前端部分, Yesod那些莎士比亚模板语言还算能用. 主流的[BlazeHtml](https://link.zhihu.com/?target=http%3A//jaspervdj.be/blaze/) , [Lucid](https://link.zhihu.com/?target=http%3A//chrisdone.com/posts/lucid) 都挺好看, CSS只有个 [Clay](https://link.zhihu.com/?target=http%3A//fvisser.nl/clay/). Compile2JS早点就有Fay, Haste都是实现GHC的子集, GHCJS渐渐能用, 但是为了实现Haskell的语言都拖着个Runtime, 生成的文件庞大, 也已经有FRP系统在上面实现([reflex](https://link.zhihu.com/?target=https%3A//hackage.haskell.org/package/reflex)). 语法特性类似Haskell的Purescript亲和性更加好一点, 各种binding都比较齐全, 也有自己的生态.
至于坑, 用小众语言做实际项目坑是不可避免的, 大众语言大众库即便有坑多人踩了就有PR, Workaround, Haskell不但小众而且语言问题也不好解决, 碰到个不懂的概念就好多时候就瞎眼. 开发网站用传统的服务器渲染, 在关系数据库上CRUD能很好解决. 如果网站规模变大, 组件一多(Message/Job Queue, NoSQL DB, 各种Service), Haskell有些Binding或者DB Driver质量或者维护不是很好要么就自己动手, >要么就换别的语言的库, 再跟各个组件通讯. 这种结构会给运维和系统稳定性带来不少麻烦和风险.


>即便如此, 不是不推荐用Haskell, 毕竟需要更多人填坑修路




## 字符串


bytestring 函数库，Lazy Bytestring|ByteStrung Builder


text 和utf8-string函数库

mono-traversable 函数库



## 网络编程
haskell发力点，webassembly第一个用的都是haskell小坦克游戏

wai/warp




wai-extra

编程框架思路：这些网络编程框架大多提供一个HTTP的单子抽象，单子提供Reader环境，可以读取要求信息，同时提供一些Writer操作，用来HTTP响应，eq:apiary函数库提供的ActionT单子变换




WebSockets函数库


Socket编程








## serialize序列化/反序列化与泛型编程

序列化/反序列化，把内存中“活”数据<->传输/存储序列化格式JSON,MessagePack,Protobuf...






重复代码很多解决办法：
1. 模板编程
2. 泛型编程






aeson函数库





模板自动生成ToJSON/FromeJSON


泛型自动生成ToJSON/FromeJSON

泛型编程

attoparsec函数库




protobuf函数库




###  React App etc.Big Web Products


reanimate





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


## 数据库



HDBC


postgresql-simple,mysql-simple,sqlite-simple


persistent

groundhog



esqueleto:比如DSL书写SQL的好处





opaleye


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






##  hakell计算效率



>数值计算领域Haskell或者Idris想要达到C/C++的运行效率，是否存在理论上的障碍？
Haskell或者Idris作为高级语言，和C/C++比起来当然有它们的先天不足，但是这两个语言用类型系统提供了某些在C/C++中编译器不可能知道的信息，原则上可以用来提供优化的依据，所以也有它们的优势。我认为这个问题的答案并不那么显而易见。
效率是可以进行一般比较的，比如，OJ上刷题的运行时间分布就可以作为一种度量。
作者：祖与占  
链接：https://www.zhihu.com/question/301111822/answer/524107809  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  

> 是否存在理论上的障碍？
我觉得是不存在. 数值计算效率的瓶颈在于能否最大化利用硬件, 例如搞 CPU 的 Intel 出的 MKL 就比其他 BLAS, LAPACK 实现要猛. 所以只要搞编译器有足够的投入, Haskell 做数值计算的效率肯定是可以追赶上 C/C++ 的. 但是 Haskell 还有个操作是可以搞 EDSL, 搞 inline-*: 搞个可以编译到 C/C++ 的专门做数值计算的 EDSL, 可以在类型系统做方便生成高效代码的约束, 还可以用 inline-c/cpp/r/java/rust, 想调什么语言就什么语言, 拿 Haskell 做胶水, CPython 实现也很慢, 还不是很火, 还不是调用各种 BLAS, LAPACK 实现?
对内存分配的压力有怀疑的话完全可以让上面说的 EDSL 语义完全是 strict 的嘛, 后面还有 Linear Type, 管理好生命周期应该不会比 C/C++ 差不太远的, 或者完全 fusion 掉?

>现状是 Haskell 的 de facto 编译器实现 GHC 的 SIMD 支持[还在路上](https://link.zhihu.com/?target=https%3A//phabricator.haskell.org/D4813) (GSoC 2018 搞的), Accelerate 现在的维护状况还不错, 也有 LLVM 的后端, 具体例子可以看 [Haskell for Numerics?](https://link.zhihu.com/?target=https%3A//idontgetoutmuch.wordpress.com/2017/06/02/1090/)



##  量子力学


https://wiki.haskell.org/Numeric_Quest


http://www.philipzucker.com/a-touch-of-topological-quantum-computation-in-haskell-pt-i/


Haskell Pt中的拓扑量子计算。







### 多项式
https://github.com/mokus0/polynomial


https://github.com/mokus0/polynomial



### 矩阵计算，数值分析等等


https://github.com/ocramz/sparse-linear-algebra




### haskell-optimization
https://github.com/frizensami/haskell-optimization



















































### 大数计算



https://github.com/erikd/haskell-big-integer-experiment














## 命题逻辑，一阶逻辑，形式验证，定理证明，数学猜想

其实我觉得λ演算很适合做这个的。

### Haskell bindings to Microsoft's Z3 API (unofficial).


https://github.com/IagoAbal/haskell-z3




###  hakell符号演算定理证明coq


高数线性代数
 proof of hakell symbolic calculus theorem
Linear algebra of higher numbers

https://github.com/jwiegley/coq-haskell




https://zhuanlan.zhihu.com/p/31567423



Haskell保存公理公式和运算，实现证明高数书本的过程！！

！！翻译，一个高校计算机演算数学公式的过程！


机器数学证明，把求导积分微分等等放进去操作的约定，人不推导公式，人用它来发现新的公式！
机器几何证明！



### Haskell程序证明

https://zhiwei.li/text/2010/06/10/haskell程序推理/





### Convert Haskell source code to Coq source code
https://github.com/antalsz/hs-to-coq

### Prolog


用Haskell编写的prolog解释器。
https://github.com/Erdwolf/prolog









##  hakell Paser语义语法分析---编译原理


Hakell Semantic Grammar Analysis and Compilation Principle
张凇书本P179，P285


https://github.com/ollef/Earley


https://blog.csdn.net/libinbin_1014/article/details/78833172

https://www.cnblogs.com/ghjbk/p/6953619.html


https://www.haskell.org/happy/





### Haskell的LEX和YACC
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




### 如何评价Haskell的Parser Generator BNFC？

它是不是直接解决了Alex和Happy用户搞不定Layout的痛点？








## 数据分析


https://github.com/BinRoot/Haskell-Data-Analysis-Cookbook

### 电子表格





https://github.com/Gabriel439/Haskell-Typed-Spreadsheet-Library

### 画图

https://github.com/timbod7/haskell-chart
















##  ML统计学习Jullia,Python接口调用通用Manod

 ML Statistical Learning Jullia, Python Interface Calls Universal Manod

https://github.com/tensorflow/haskell

### 深度学习



https://github.com/austinvhuang/awesome-haskell-deep-learning




### 人工神经网络




https://www.zhihu.com/question/38295817/answer/75849804



https://github.com/alpmestan/hnn



### 何时Haskell比数据科学中的R或Python更有用？

https://www.forbes.com/sites/quora/2018/01/24/when-is-haskell-more-useful-than-r-or-python-in-data-science/#d6707a069e47











https://blog.csdn.net/lyndacn/article/details/80882257






https://www.zhihu.com/question/40703653/answer/88245442








## 好玩的CAD/CAE


github项目processing

processing-for-haskell


haskell-playground/graphics


Topic:Graphics.Github很多haskell 计算机图学项目汇总，直接搜索Computer graphics .  haskell .github

### 图像处理




Haskell Image Processing Library

https://github.com/jcollard/unm-hip


### Hackage上视频框架，图像处理框架

gloss就不错，还有很多，一搜就有。

reanimate- Animation library based on SVGs-



### 建模，计算机辅助设计CAD

opengl+haskell

computer aided design CAD+haskell



haskell建模框架也有很多在hackage，stackage能找到的，类似plantsimulation等领域语言编程框架




























A math-inspired CAD program in haskell. CSG, bevels, and shells; 2D & 3D; gcode generation...




https://github.com/colah/ImplicitCAD



www.implicitcad.org















### MusicPlayer+GIF


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










### 可视化


https://github.com/viskell/viskell

Viskell是一种用于类型（类似Haskell）的函数式编程语言的实验性可视化编程环境。该项目正在探索交互式可视化编程的可能性和挑战，并结合功能语言的优点和缺点。


### OpenCV





https://github.com/LumiGuide/haskell-opencv







### openCL





https://github.com/bgaster/hopencl









### OpenGL  

https://github.com/hasura/graphql-parser-hs



https://github.com/madjestic/Haskell-OpenGL-Tutorial
https://github.com/bergey/haskell-OpenGL-examples









## OpenQL






Write type-safe GraphQL services in Haskell







https://github.com/haskell-graphql/graphql-api

https://graphql.org





## 搜索猎犬框架






https://github.com/bitemyapp/bloodhound

### 搜索引擎

https://github.com/ndmitchell/hoogle


















## QuickCheck


https://github.com/CIFASIS/QuickFuzz


## 概率编程


https://github.com/adscib/monad-bayes



## RSA加密


https://github.com/GaloisInc/RSA



## haskell音乐框架
www.euterpea.com




https://github.com/spell-music/csound-expression




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









## 异常处理

垃圾回收

异常处理


运行时异常



Either/Maybe

异步异常处理



try catch





resource函数库



单子用作异常处理
exceptions函数库

monad-control单子栈操作库































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














## 人工智能
Algorithms from *Artificial Intelligence: A Modern Approach* by Russell and Norvig.
https://github.com/chris-taylor/aima-haskell



##  数字孪生硬件相关



### kinectgames



A breakout game in Haskell using SDL and FRP, with Wiimote and Kinect support.



https://github.com/ivanperez-keera/haskanoid







##  hakell分形。自动演算
 hakell fractal. autotune

https://gregheartsfield.com/fractal-hs/

https://github.com/cies/haskell-fractal


## 计算机演化，演算计算---自然进化Hakell
 Logical Calculus--Natural Evolution Hakell






##  状态自动机


https://github.com/owickstrom/motor



# haskell游戏编程框架

https://wiki.haskell.org/Game_Development




Yampa /游戏引擎

A lightweight, cross-platform, OpenGL/GLUT-based 2D game engine in Haskell 



https://haskell.libhunt.com/categories/2947-game-engine

Haskell game engine library for roguelike dungeon crawlers; please offer feedback, e.g., after trying out the sample game with the web frontend at https://lambdahack.github.io


一个Haskell的游戏框架：ActionKid。


helm: A functionally reactive game engine.








# Andriod

## Andrios APP

https://github.com/wavewave/haskell-android-example

## Andrios APP+IOS
https://github.com/abarbu/haskell-mobile




# java V.S Haskell更加高效有用的OOP抽象---面向函数对象hakell

>老爷子后来认为Erlang是OOP，但是这个OOP和其他人理解的不一样：
>
>-   常规认为OOP=封装+继承+多态
>-   老爷子认为OOP=消息传递 + 隔离 + 多态，其中**消息传递最重要，隔离和多态都源自于消息传递。**
> Smalltalk的作者Alan Kay更是认为Messaging是唯一重要的事情。从这个角度，Erlang非常OOP。**所以老爷子其实是支持OOP的，但是他支持的不是题主要问的Java那种OOP。**
>作者：大宽宽  
>链接：https://www.zhihu.com/question/29888990/answer/703226836  
>来源：知乎  
>著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


## JAVA VS Haskell

(亲身经验，学完java接口再看Haskell类型类，异常处理并发线程等等，绝对有启发有帮助！)


https://www.zhihu.com/question/67678268/answer/255774559
作者：非构造性雨轩菌  
链接：https://www.zhihu.com/question/67678268/answer/255774559  
来源：知乎  
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
  没有，java和haskell都是作为图灵完备的语言而设计的。（逃
嘛，更容易做到的和更难做到的倒是一个很大的话题。这里以我自己的理解和经历取多个方面不完全的列举一些简单的例子吧
和语言的社区、学习相关的：
-   Java更容易利用现有的API、工具链及相关文档实现一些常见的功能性程序。Haskell相对来说存在相关文档可能较少、没有类似的可参考的实现等劣势。这跟语言本身的定位、社区有一定关系。
-   Java在web方面有较多现有的解决方案，技术栈、文档相对来说齐全。相关技术、API都被反复使用过，如果不是在玩各种黑魔法，对已有的坑之类的即使踩中也有能很轻松的找到解决方案。嘛，毕竟Java（www
-   一般来说Haskell的学习曲线较Java陡峭，社区的各类教程不如Java丰富，社区的规模摆在那里。很多基础概念涉及被抽象后的数学概念，前置知识要求较多，毕竟抽象很大程度要站在直观理解的位置才行，没有直观理解的话较难理解抽象背后的意义。自学的话Haskell更需要自身有多尝试、找文档、规划学习过程等能力。
-   有一定数学基础（特别是离散数学、类型论等）学习Haskell相对Java来说更加有用，较容易找到对应的概念，这方面的文档要比Java丰富。容易写一些十几行简单的程序来辅助理解，能写的东西较多。而Java需要在另一种方面去学习，比如通过研究现有的开源程序、学习设计模式、写一些简单的小项目等。这可能会导致“Haskell学语言，Java学姿势”的情况（www
-   Haskell社区的资源更加集中，在学习过程中如果善于去找的话，更容易找到真正需要的资源。比如有[Hoogle](https://link.zhihu.com/?target=https%3A//www.haskell.org/hoogle/)这种好东西，对学习很有帮助。
-   etc.
语言特性方面：
-   说到Haskell那语言特性方面第一个想到的果然还是类型系统相关的吧www，Java的话OOP范式、inheritance、behavioral subtyping、generic（bounded parametric polymorphism）、wildcard（existential bounded polymorphism）、overloading（ad hoc polymorphism）、etc. 。Haskell的话能说的就多了，FP范式、ML系、type inference（Hindley-Milner type system）、parametric polymorphism、typeclass（ad hoc polymorphism）、type constructor（higher kinded type）、lazy evaluation strategy（call-by-need）、经常被提到的monad（www）、etc.。各种扩展更是不计其数，常见的：RankNTypes、ExistentialQuantification、GADTs、DataKinds、TypeFamilies、TypeOperators、MultiParamTypeClasses、FunctionalDependencies、etc.
-   Meta programming的话Java不支持、Haskell有template。
-   Haskell主要后端是编译到native code，也有bytecode。Java主要编译到bytecode然后jvm解释、JIT。内存管理都是GC策略。
-   因为Haskell类型系统相对Java更丰富，可以用类型系统玩各种有趣的东西www，Java的话泛型并不支持higher kinded type，type inference也只是局部的，能玩的东西有限。
-   Java的话并行程序主要还是靠加锁、wait notify、java.util.concurrent、现有的thread safe的数据结构，线程安全靠Java内存模型。Haskell的话有Control.Parallel、Control.Concurrent、Control.Concurrent.STM，用得不多不太好发表评论。
-   etc.
如果假设这里的更容易和更难指的是具体实现一个程序主观上是否更容易的话那么大概Java的长处就是OOP范式本身和丰富的API了。Haskell的长处就是其类型系统了，能够抽象出更多的概念，在高层次处理复杂问题，由类型系统保证程序的正确性，甚至可以玩定理证明www
总之分别有各自的应用领域，Haskell和Java各有各的好。





## 用Haskell实现面向对象编程OOP

现在JAVAC++之类的面向对象都是C语言模块化封装，加上各种因此精心设计的语法泛型编程技巧，

不考虑实现OO的意义，仅考虑实现OO的思路和效果（  
比如existential type class用于模拟inheritance。。


https://www.zhihu.com/question/52412654/answer/130426928

https://github.com/fumieval/objective



### JVM

https://github.com/typelead/eta


https://github.com/Frege/frege










#  lambda演算硬件电路编程语言
Lambda Calculus Hardware Circuit, CPU, Fourier Transform Integral Transform Chip, MCU Chip Circuit, 

## “λ演算芯片”？
既然能用机械差分机演算积分微分，那么电路也能物理手段演算一些数学定律，比如傅里叶变换积分变换芯片，群论相关结论芯片电路，或者专门为了计算的GPU改良版，那么有没有“λ演算芯片”？

卡脖子技术不是别人知识轮子上的说明书，而是他们没告诉你的，怎么造出来轮子的基础原理技术。


### 《From Haskell to Hardware via CCCs》
Wiki相关介绍
### ForSyDe
Haskell的DSL用来写VHDL,可和第三方EDA链接（Modelisim,Quartus）
### Atom
嵌入在haskell的硬件描述

### Circuit Simulator电路模拟器Hawk项目
David J.King & Jhon O'Donnell's digital circuit simulator.
指定和原型制造微处理器

Hawk语言=haskell+hawk库


### chortl

haskell EDSL 用于硬件描述





###  CλaSH（clash）功能性硬件描述语言

借用haskell函数式语法高级描述转换为低级VHDL，Verilog,SystemVerilog，说到底还是Haskell适合用haskell单子优势处理DSL领域相关问题，正如前面的例子，用haskell单子优势处理JSON，XML,字符串，websocket，HTTP,序列化,Protobuf,MessagePack，网页模板编程，或者生成SQL，parser解析器。。。。。。


github:HaSKI





# 函数式高并发操作系统
Functional High Concurrent Operating System.

Haskell Users's Operation System and Environment.


https://github.com/dls/house


## Haskell_GUI

https://github.com/tomsmalley/semantic-reflex


https://tomsmalley.github.io/semantic-reflex/




##  hakell程序设计编译发行exe等

其实直接ghc Main.hs就可以。

 hakell programming exe
https://github.com/dkubb/haskell-builder




## I/O标准输入输出



https://github.com/winterland1989/stdio















# 大一统的出路---Haskell胶水实现



## 编程语言通过胶水链接OS接口实现大一统。

不想引战，但是我觉得python胶水粘不牢，类库包管理混乱，开源社区虽然都有这种缺点，而且python也在改正，但是我感觉它做不到太高效率干净整洁地完全独立出来。Anaconda,JupyterNotebook各种语言内核玩转的确让我甚是喜爱，但是我的确觉得python的C打包味道不够干净。

但是Fp还没足够强大，这也是需要越来越多人加入改变他的理由！

理论上我感觉，Haskell似乎在现有语言之间进行安全性，抽象性和实用性之间的绝佳权衡。

OLE,DLL，LIB，混合编程，Haskell可能是最好的胶水语言。计算机优势是重复光速大内存，haskell也能提供一种很好的利用计算机资源的方法。

现在学术界喜欢Haskell低调研究，不想成功火起来，从而方便一些实验性的代码能够经过调试而不是错误代码就被广为流传到处使用（比如那个C操作系统那行被作者注释了临时代码表明不合适，希望以后有人修改的，后来没改不但还把注释删除了的事情）。官网其实希望Haskell用来研究，而其他他衍生出来的商用语言用来“工业使用”。

想要商用，想要Haskell火起来，重点就是我说的前文的生态问题的解决，让Haskell成为能够调用整个“计算机所有软硬件资源的完美接口灵活”的通用性语言，用“操作系统接口调用方法”打通所有语言之间的“壁垒”。




## 调用其他软件的接口api
Telegram Bot API for Haskell


https://github.com/klappvisor/haskell-telegram-api

https://docs.haskellstack.org/en/stable/README/

hakell混合编程数据接口dll,良好的文件管理和I/O

https://github.com/phadej/github

## Haskell-API
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















#   文末总结+我想到的优点：

**越是抽象高屋建瓴得到的理论结论越是内涵，这种规律越是容易映射到其他事物上，高处不胜寒，就像数学，越学越发现回头看的以前的结论是降维特例而已，代码也一样，很Trivial，这些二元运算在自函子范畴上很有效，幺半群的结论都满足。适用性广意味着我不用费脑筋考虑它失效的条件是什么。最妙不可言的是，语言内核居然惊人的简单，人类的本质是复读机，难道计算机世界运作的本质规律是复制M-w粘贴C-y?通过模式匹配有选择地M-w/C-y，通过递归重复执行M-w/C-y？**


1. 更短更泛型，传入模块更加函数方便封装，传入参数可变，泛型更接近约莫近似的人脑思维方式，信息量传递的OOP更加抽象，更加高效！参数格式可变，参数类型可变，参数数量可选，更加泛型，更加模糊，更加抽象。
2. 高阶函数封装处理更加数学，证明方便高效，递归证明，可递归定义，更范畴，更加近世代数，更加像数学公式的代码。
3. 轻量化线程，纯函数，高并发，事件处理STM
4. 混合编程，逻辑演算，并行计算，数学演算用haskell计算，结果传入给其他软件混合编程（WASM）。-分形画图计算机图学直接传参调用相关开放性包画图，或者大前端画图浏览器系列编程。调用面向对象的A higher level of abstrac!   各种文件的（主要文本文件）I/O处理，文件网络Socket用Manod外界其他文件其他语言的Dll，比如面向对象传入的数据，C语言画图的框架DLL，Python机器学习包 ,Matlab科学计算M文件，R数据SPSS分析统计处理,mathematica有趣的各种骚操作......调用其他软件，比如ABBY文本识别，TXT处理，ODBCMySQL数据库，Mathpix snipping 公式识别，bat文件之类的“跨软件全操作系统混合编程”。（操作系统API调用方法）
5.  容易理解逻辑，数学怎么写，代码怎么写，方便编译正确性能保证，好看，短，脏活儿扔给计算机。
6.  不存在内存StackFlow,等等因为变量意外，人为瞎操作指针意外带来的难以发现的计算机硬件时序电路体系带来的“困惑”，纯函数，高并发，安全稳定可靠，安全性正确性能够证明。
7.  从更高的角度看问题，从一个超集的更加功能强大的系统看以往简陋的系统，更加高瞻远瞩。递归是循环的超集，而Haskell是更加抽象的现实模型，比C更少“程序员需要操心的部分”，比JAVA更加高级的传入信息量的OOP。语法更加模糊接近人的思维方式，描述现实更加抽象，代码更加难懂。
8. 函数（curry高阶函数匿名函数图论网络树森林类型king类型类typeclass值type常量数值字符串数据结构+算法=程序）是第一公民！
9. 子系统是我们研究的一个小的模块化编程（OOP的对象）部分，a new level of abstract又接着封装，成为新的系统要研究的对象。系统工程https://www.jianshu.com/p/75e8d71f7d99。C语言传入参数靠的是（（（（......）））,而Haskell直接Curry，分级传参，高阶函数传入函数的函数实现函数的嵌套，已经研究好的子系统直接封装把信号传递给超系统，更利于研究实际系统的模块化编程，更利于理解“世界运作的规律”

# **别人认为的优点:**

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
优点：
https://www.oschina.net/translate/state-of-the-haskell-ecosystem-august-2015  翻译不太好，建议看原文https://github.com/Gabriel439/post-rfc/blob/master/sotu.md  这里里谈到很多领域方面**haskell应用领域+编程需求**

1)Haskell是最先进的编程语言。 我做了一些研究，haskell似乎是唯一真正的最先进的编程语言。还有其他像agda和coq，但这些都是实验性的，缺乏现实世界编程的功能(例如图书馆支持)。最好投资一种最先进的编程语言。 (注意：我没有争论为什么haskell是最先进的，几乎任何其他编程语言都没有。这需要花费太多时间。所以这只是我的主观意见。同样适用于其他陈述。) (注意：我后面提到的一些功能可能是GHC特定的，但我仍然只写haskell)

2)Haskell程序员通常非常聪明。库的代码质量非常高。此外，stackoverflow的提示写得非常好，并且也处于高水平(感谢Don Stewart这样的人，仅举一例)。我认为改进编程的最佳方法之一是学习其他人的代码。 Haskell在这方面非常出色。 

3)moste OOP语言中的命令式编程已经过时。通常的副作用编程方式也是如此。但是很少有编程语言用于没有副作用的声明性编程。例如Scala，F#，Ocaml和Erlang不是副作用。 (但是，在OOP语言的学术领域也有工作，显然没有过时。考虑Alan Kay过去的工作，或者例如Smalltalk领域当前最先进的学术工作。) 

4)Haskell支持使用抽象数学概念进行编程(例如monad，functor，combinators，GADT等)。我认为这可以提高编程效率。 


5)Haskell类型系统非常灵活，支持类型推断。这大大减少了可能的错误。在编译时检查类型系统。类型系统有助于作为文档。

6)首先在haskell中实现一些最先进的概念(如QuickCheck库)。有很多有趣的扩展。

7)haskell语法设计得很好。没有不必要的括号。代码紧凑，模式匹配和列表理解的synatax非常好。像Knuth这样的人提倡有文化的编程，而haskell/GHC则支持它。

8)haskell支持懒惰评估 








## Haskell有一些问题类型可以擅长，但是，

如果你编写一个需要不断改变状态的程序，那么Haskell是一个糟糕的选择。 如果在对问题进行建模时，它不适合函数编程，例如编写CAD(计算机辅助设计)程序，那么OOP将是更好的选择，因为编程范例更适合模型。 但是，如果您不受这些问题的影响，那么Haskell可以成为一种很好的语言。解决办法：利用“计算机系统接口混合编程”




>haskell的wiki上有汇总总结，基本上是一年两期，今年还只有上半年的第一期。
[https://www.haskell.org/haskellwiki/Haskell_Communities_and_Activities_Report](https://wiki.haskell.org/Haskell_Communities_and_Activities_Report)
你感兴趣可以去看看那些实践者们都是用在什么场合就大概可以体会一点haskell在工程中的优势了。
其实我看这个报告的时候有些失望，因为工程项目确实是少，当然这是符合haskell的热度排名情况的(常年40左右)。
haskell最能体现工程层面优势的项目应该是，io少，内存不紧张，业务逻辑特别复杂且多变的项目。
Haskell用在工程項目中有什麼優勢？ - 随心所往的回答 - 知乎
>https://www.zhihu.com/question/26510008/answer/33050372
 
 好产品例子Pandoc

https://github.com/jaspervdj/patat


## haskell缺点


1)这很难学，掌握haskell需要数小时，数月。没有适当的计算机科学背景就更难了。像Monads和Functors这样的东西很难理解，特别是没有数学背景。所以大多数程序员可能没有能力或愿意学习haskell。 Haskell并不“简单”。如何使用支持所有高级功能的简单语言是不可能的。
2)IDE选项不如其他编程语言好。我使用leksah作为我的IDE，它非常好，但它与Eclipse的java开发无法比较。 
3)Haskell不能用于Android或Iphone开发。相比之下，Scala可以用于Android开发，它也兼容java，这是一个巨大的优势。 
4)我认为一些图书馆缺乏支持维护和改进它们的人。我在haskell中进行语义Web编程，并且库支持可能更好。

Haskell不适合所有项目。如果你需要每毫秒的性能，C/C++仍然可能是最好的选择。因此，haskell适用于许多项目，但不是全部。 Haskell与其他编程语言相比具有许多技术优势。但是，可能存在反对使用haskell的政治原因。例如，Scala可以更好地与现有的Java基础架构集成。

 知乎作者：随心所往说：链接：https://www.zhihu.com/question/26510008/answer/33050372  ：




>还要一个值得一提的是Zipper，learn you a haskell for good 的例子已经够好了。参考链接 zippers。当然，Haskell这一类fp的语言面前，递归结构书写出来都是很漂亮的。只是遇到状态变更一类的场景时，显得有些别扭，不如直接通过指针修改来得高效。
>作者：夜色残阳
>链接：https://www.zhihu.com/question/32163076/answer/254083860



https://blog.csdn.net/quicmous/article/details/82222038
王垠也写过一篇吐槽Haskell的.

 Safe or Convenient？
 
 的确，谁家通信总拿根管子传来传去？你说安全,可惜我觉得不方便，这真是个问题。

但是，真正值得传递的到底是什么？想起来，《Mathematica演示项目笔记》吴飞说过，编程到后面，变量都不是全局变量。

再引用一遍。

>老爷子后来认为Erlang是OOP，但是这个OOP和其他人理解的不一样：
>
>-   常规认为OOP=封装+继承+多态
>-   老爷子认为OOP=消息传递 + 隔离 + 多态，其中**消息传递最重要，隔离和多态都源自于消息传递。**
> Smalltalk的作者Alan Kay更是认为Messaging是唯一重要的事情。从这个角度，Erlang非常OOP。**所以老爷子其实是支持OOP的，但是他支持的不是题主要问的Java那种OOP。**
>作者：大宽宽  
>链接：https://www.zhihu.com/question/29888990/answer/703226836  
>来源：知乎  
>著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

oo分流派的，现在通常说的oo是指java/c++这一派，搞类、搞继承、搞多态。古典oo是erlang这一派的，每个对象object是个actor，对象间通过消息通讯，没有继承这一说，对象间不共享状态。Joe看不起现代派oo。erlang自己是古典派的，如何看的起现代派。至于c++标志性的template，不属于oop的概念。Alan Kay，oop概念发明者，也是图灵奖获得者，说了：OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme late-binding of all things. It can be done in Smalltalk and in LISP. OOP对我来说，就是指消息、本地记忆与保护、隐藏状态与进程、所有事物的极端延迟绑定。可以在Smalltalk也可以在LISP实现。据我所知，殿堂级大师，都看不上以Java/c++为代表的现代派oop。

作者：码师兄
链接：https://www.zhihu.com/question/29888990/answer/704512665
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

# 很多时候，决定脑袋能想到什么的是人们看到了什么。

虽然最终决定脑袋决策的是屁股。


发明haskell的大佬说了，希望Haskell成为学术类可以不断发展的低调的语言，要“商业成功”，换个名字加别的属性改成别的语言吧，只有不流行，不广为传播，GHC发生的错误才能被及时纠正。而不是像那行明知道不合适的OS代码，作者都标注明白这样写不好，希望后来人改好，却广为流传以至连那行注释都被删除了。


[注]引用没有标明出处请告知




