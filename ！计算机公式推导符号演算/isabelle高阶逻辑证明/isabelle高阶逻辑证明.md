# isabelle高阶逻辑证明
托比亚斯·尼普科夫、(英)劳伦斯·鲍尔森、玛尔库斯·温泽尔编著的《高阶逻辑辅助证明系统(精)》是在高阶逻辑中使用Isabelle辅助证明系统进行交互式证明的导论，适用于Isabelle系统的潜在使用者，自成体系，分为三部分：第一部分是基本技巧：介绍在高阶逻辑中如何进行函数式程序建模，提供了表(1ist)和自然数的简单证明实例。大多数证明只要两步完成：对所选变量进行归纳以及使用自动策略(auto)。当然，这些粗浅的例子仍然涵盖了嵌套递归和交叉递归等技术。第二部分是逻辑与集合：介绍大量可供选择使用的低级证明策略。本部分描述了Isabelle／HOL如何处理集合、函数、关系以及如何实现递归定义集合，包括模型检验理论和经典教科书中关于形式语言的案例。第三部分是话题：包括实数、记录、重载技术等主题。本部分也讨论了归纳法和递归方法的技巧，还专门给出一章来介绍安全协议的形式化验证。






官网教程文档






isabelle.in.tum.de/documentation.html


各种文档，都是PDF版本，HTML,或者latex版本就要编辑转化一下。













理论文件展示
[http://isabelle.in.tum.de/library/HOL/](http://isabelle.in.tum.de/library/HOL/)





形式证明档案


[https://www.isa-afp.org/](https://www.isa-afp.org/)

正式证明档案是证据库，示例和更大的科学发展的集合，在定理证明者[Isabelle中进行](http://isabelle.in.tum.de/)机械检查。它以科学期刊的方式组织，由[dblp](http://dblp.uni-trier.de/db/journals/afp/)索引并具有ISSN：2150-914x。提交的内容均经过审核。首选引用风格[\[此处\]](https://www.isa-afp.org/citing.html)。我们鼓励AFP提交会议和期刊出版物。











HOL=函数编程+逻辑


第一部分 基本技巧  

第一章 基础  

1．1 引言  

1．2 theory(理论)  

1．3 类型，项和公式  

1．4 变元  

1．5 交互与界面  

1．6 启动  

第二章 HOL中的函数编程  

第三章 函数式编程  

第四章 theory的表示  

第二部分 逻辑与集合  

第五章 游戏规则  

第六章 集合、函数和关系  

第七章 集合递归定义  

第八章 高级types  


nat cos,tan，log.无穷大omega和无穷小epsilon,无限接近也能定义，非标准实数，极限微分积分很容易实现（Mechanizing non-standrad real anaysis [J]文中写道）

有理数完备实数RComplete理论文件中有完备性定义

HOL_completx理论文件中有rat,real,complex类型

可使用HOL-NSA逻辑的理论文件是Hyperreal理论文件，有超越函数sin......几十个类型类，半环有序半环，环有序环，域有序域，除零等几百条引理。















Ring_and_Field理论文件中有很多数值理论文件，通过公理类型类来组织，a/0=0



第九章 化简与归纳  

第十章 案例学习：验证安全协议  

附录  

参考文献  

译后记一













# 周边

www.voidcn.com/article/p-rkuqqdrh-byn.html



我正在阅读 [“Concrete semantics with Isabelle/HOL”](javascript:void()),我对高阶逻辑非常感兴趣.我知道普通的一阶逻辑和一些模态逻辑,但如果之前没有接触到高阶逻辑及其元理论,我几乎没有,所以我想填补空白.我读到HOL本质上是Church的简单类型理论而Pure是前者的直觉变体.问题是“基本上”这个词：Isabelle / HOL和Isabelle / Pure理论与例如 [Andrews’ textbook](javascript:void())有何不同？是否有关于Isabelle / HOL和Isabelle / Pure中使用的高阶逻辑的教科书介绍,并讨论了它们的元理论特性？

关于HOL及其众多变体和方言,可以说很多.这是 [Isabelle](javascript:void())和其他 [HOL](javascript:void())系统邮件列表上的一个经常性主题.例如,以下是2013年1月/ 2月关于isabelle用户的相关帖子： [Where to learn about HOL vs FOL?](javascript:void())以及对相关文献的更多参考.

在[Isabelle/Isar Implementation](javascript:void())手册第2节“原始逻辑”中,还有一些关于Isabelle / Pure(最小HOL)逻辑的内容.




































































































































































#


























