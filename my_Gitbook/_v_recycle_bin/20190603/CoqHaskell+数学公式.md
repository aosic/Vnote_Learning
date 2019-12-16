Coq+Haskell+数学公式


参考文档

Coq开发团队维护以下参考文档：

-   的[参考手册](https://coq.inria.fr/distrib/current/refman/)，这对于Coq的文件的完整，权威来源;
-   与系统一起分发的[标准库](https://coq.inria.fr/distrib/current/stdlib)的文档。

可以从[GitHub上的发布页面](https://github.com/coq/coq/releases/tag/V8.9.1)下载参考手册的PDF版本 。

请注意，此参考文档不是开始使用Coq的好地方。有关初学者的更多适用文档，请参见下文。

-   [参考手册](https://coq.inria.fr/distrib/current/refman/)
 -   [标准图书馆](https://coq.inria.fr/distrib/current/stdlib)

书籍和长篇教程

以下书籍和长篇教程由经验丰富的Coq用户和教师编写：

-   [Coq'Art](http://www.labri.fr/perso/casteran/CoqArt/)，第一本专门用于Coq证明助手的书（Yves Bertot，PierreCastéran，2004年，2009年中文版），只有法语版和练习版可以免费下载，英文版可以在[Springer的网站](https://link.springer.com/book/10.1007/978-3-662-07964-5)上[找到](https://link.springer.com/book/10.1007/978-3-662-07964-5) ;
-   [软件基础](http://www.cis.upenn.edu/~bcpierce/sf/)，一系列基于Coq的逻辑，功能编程和编程语言基础教科书（Benjamin Pierce *等*，2007，定期更新），备受好评的初学者，但更倾向于计算机科学家;
-   [使用相关类型认证编程](http://adam.chlipala.net/cpdt/)，一本关于Coq实用工程的教科书（Adam Chlipala，2008），教授高级实用技巧和非常具体的证明方式;
-   [认证编译器的程序逻辑](https://www.cambridge.org/us/academic/subjects/computer-science/programming-languages-and-applied-logic/program-logics-certified-compilers)（Andrew W. Appel *et al。*，2014），这本书解释了如何使用分离逻辑理论构建强大而富有表现力的程序逻辑，并附带Coq（[验证软件工具链）中](https://vst.cs.princeton.edu/)的正式模型，这适用于C光编程语言和其他例子。
-   [关于程序的正式推理](http://adam.chlipala.net/frap/)（Adam Chlipala，2017），这本书同时提供了关于程序正确性的正式逻辑推理以及为此目的使用Coq的一般介绍。
-   [程序和证明](https://ilyasergey.net/pnp/)，（Ilya Sergey，2017），这本书简要而实用地介绍了使用Coq进行交互式定理证明的基本概念; 通过来自SSreflect证明语言的一小组原语，强调关于可判定命题的归纳推理的计算性质。
-   [计算机算术和形式证明](http://iste.co.uk/book.php?id=1238)，（S. Boldo和G. Melquiond，2017），这本书提供了如何使用[Flocq库](https://gitlab.inria.fr/flocq/flocq)使用Coq正式指定和验证棘手的浮点算法的全面视图 。
-   在[数学组件书](https://math-comp.github.io/mcb/)（A. Mahboubi和E. TASSI，2018），即更多地转向数学的用户导向的一本书，潜入勒柯克与SSReflect证明语言，数学组件库。

-   [Coq'Art](http://www.labri.fr/perso/casteran/CoqArt/)
 -   [SF](http://www.cis.upenn.edu/~bcpierce/sf/)
 -   [CPDT](http://adam.chlipala.net/cpdt/)
 -   [MCB](https://math-comp.github.io/mcb/)

更短的教程和视频

以下简要介绍了Coq或特定主题，可能针对初学者或更高级用户：

-   一个旧的[教程](https://coq.inria.fr/tutorial)，这是一个注释的交互式会话，介绍术语，证据和战术的基础知识（GérardHuet，Gilles Kahn和Christine Paulin-Mohring）。
-   [Coq in a Hurry](https://cel.archives-ouvertes.fr/inria-00001173)（Yves Bertot，2006）;
-   一个[教程上递归类型在Coq的](http://www.labri.fr/perso/casteran/RecTutorial.pdf)（爱德华希门尼斯，皮尔Castéran，2006）和相关联的[实施例](http://www.labri.fr/perso/casteran/RecTutorial.v) ;
-   [视频教程](http://math.andrej.com/2011/02/22/video-tutorials-for-the-coq-proof-assistant/)（Andrej Bauer，2011）;
-   [Coq中的类型类和重写的](http://www.labri.fr/perso/casteran/CoqArt/TypeClassesTut/typeclassestut.pdf)简要[介绍](http://www.labri.fr/perso/casteran/CoqArt/TypeClassesTut/typeclassestut.pdf)（PierreCastéran，Matthieu Sozeau，2012）以及Coq 8.3-8.5 的[相关示例](http://www.labri.fr/perso/casteran/CoqArt/TypeClassesTut/) ;
-   [Preuves de programs en coq](http://www-sop.inria.fr/members/Yves.Bertot/videos-coq/)（法语视频讲座）（Yves Bertot，2013）;
-   一个可以作为[Coq文件](https://coq.inria.fr/files/nahas_tutorial.v)交互式浏览的[教程](https://coq.inria.fr/tutorial-nahas)（Mike Nahas，2014）;[](https://coq.inria.fr/files/nahas_tutorial.v)
-   [](https://www.youtube.com/channel/UC5yB0ZRgc4A99ttkwer-dDw/feed)2017年DeepSpec暑期学校的[视频](https://www.youtube.com/channel/UC5yB0ZRgc4A99ttkwer-dDw/feed)，介绍了Coq和许多高级用途;

-   [Mike Nahas的教程](https://coq.inria.fr/tutorial-nahas)
 -   [Coq匆忙](https://cel.archives-ouvertes.fr/inria-00001173)

其他文件

一些额外的资源：

-   一堆[常见问题](https://github.com/coq/coq/wiki/The-Coq-FAQ) ;
-   [Cocorico！](https://github.com/coq/coq/wiki/)，Coq维基;
-   [Coq源代码](https://github.com/coq/coq/tree/master/dev#miscellaneous-information-about-the-code-devdoc)的内部开发人员[文档](https://github.com/coq/coq/tree/master/dev#miscellaneous-information-about-the-code-devdoc)索引;
-   odoc [为Coq的](https://coq.github.io/doc/master/api/)开发版本生成[了Coq API的文档](https://coq.github.io/doc/master/api/) ;
-   [](https://coq.github.io/doc/master/refman/)Coq开发版[参考手册](https://coq.github.io/doc/master/refman/) ;
-   [](https://coq.github.io/doc/master/stdlib/)Coq开发版[标准库的文档](https://coq.github.io/doc/master/stdlib/)。





















































































































































































































































