# haskell-Notes



# Haskell环境搭建模块生态stackage/hackage

看官网，haskell platfrom，winGHC，各种插件，Ghci。

## cabal/stack

[cabal](https://package.haskell.org/package/cabal/users-guide)


管理工具+自动化编译工具



```shell



cabal update
cabal install containers安装函数库 containers



ghc-pkg list#查看全局安装函数库
ghc-pkg unregister foo# 卸载foo函数库
ghc-pkg unregister foo --force# 强制卸载foo函数库，以来foo的函数库可能因此不能用


ghc-pkg check #检查全局函数库是否完整

ghc-pkg hide foo  # 隐藏Foo函数库


```

全局污染不好，一般不建议全局安装cabal   install 


```shell
cabal sandbox init

cabal repl
cabal sandbox hc-pkg list  #list函数库
cabal sandbox hc-pkg unregister foo  # 卸载foo函数库
cabal sandbox hc-pkg --force unregister foo # 强制卸载，foo以来函数库可能不可用
cabal sandbox delete


```



```shell
cabal sandbox init

cabal init

vim Main.hs
main :: IO()
main = print "Bye World"
#推出保存
cabal run
>Bye World


cabal build#编译整个项目

cabal clean # 清理之前的编译结果，干干净净再打包上传
cabal sdist#生成可以上传发布的包

cabal upload Foo.tar.gz  #上传sdist打包好的包


```



大佬告诉我，stack好。



## Haddock


```shell
haddock Main.hs -o ./doc


```

新建cabal haddock项目 文档














强大的表现力，无拘束地表达抽象。

# 张淞书笔记




循环本质就是递归优化    邓俊辉

https://softwareengineering.stackexchange.com/questions/325601/is-a-while-loop-intrinsically-a-recursion
递归循环的原因，自然界找到一个成立的规律，用数学物理语言描述，然后就能递归调用这个来计算想要的结果了！比如计算代数几何的那个群论多边形结论，比如求导积分变换等等，从最基本的“公理性自然哲学”出发，演算世界运作的规律！

长得像公式的Haskell才是符合逻辑思考方式抽象形式的最好选择！

循环的本质是不是和递归等价的？邓俊辉老师说的就是动态优化------递推直观看本质到迭代省时省力算法的进步!

循环判断条件就是递归判断条件，只是他们一个调用的是系统栈，一个调用的是用户自己设置的记录递归求到的结果循环变量(看作用户栈)
https://www.zhihu.com/question/26457760?q=任何递归程序都能转换为一个等价的非递归程序吗？
系统栈，用户栈   王道

https://stackoverflow.com/questions/931762/can-every-recursion-be-converted-into-iteration3

从递归到迭代转换极其困难的一个例子是Ackermann函数。


千里冰封说递归是循环的超集，比如树的递归就有循环做不来的地方。

阶乘不动点  Haskell的类型系统，让代码一样能够推导，自动计算演算！


汉诺塔递归和非递归形式。用不动点实现haskell和C系（其他大多是约定符号语法糖不一样，OOP还是很很像C的子函数“a new level of abstract!”）语言的“编译”！让haskell利用现有丰富的C代码生态成果而不用新造轮子！虽然不一定最优省空间，但是正如Haskell写dll被C调用，人啊不关心过程，要的是好的产品，当然，成熟严谨的的过程类型推到对作者来说很重要，用户不关心！


**递归是循环的超集**，有很多递归，树的递归，扩展递归，尾递归，互调递归



用“列表”构造广义表，下标层级指针模拟链表和树基石语法糖建立高楼


用超集多叉树，森林，降维实现C语言二叉树的树结构，图形学四叉树八叉树图形学多叉树

图：
广度优先------深度遍历----树的某序遍历----快不全局部最优解启发式
深度优先------广度遍历------树的层级便利------全局最优解，慢，爆炸指数增长时间复杂度算不完


用列表广义表三元组实现序号====》逻辑上的类似指针（3）在上利用已经有的C语言现成知识轮子

用尾递归实现for循环结构


```
{-
可见惰性求值尾递归tail recursion比循环loops更加消耗内存。
-}
Prelude Data.List> foldl' (+) 0 [1 ..10000000]
50000005000000
it :: (Num b, Enum b) => b
(0.28 secs, 880,073,856 bytes)
Prelude Data.List> foldl (+) 0 [1 ..10000000]
50000005000000
it :: (Num b, Enum b) => b
(8.56 secs, 1,612,374,144 bytes)
```



用take，drop,take n构造for循环结束条件确定循环次数的语法糖

用until构造while未知循环次数结束条件的语法糖

条件表达式  ||  守卫表达式          实现if...then ...else,更加严禁定义，不能省略。

情况分析表达式 || 模式匹配       实现switch...of...选择，

？局部变量？堆栈？链表？指针？？？全局变量？



张松书第一版：

JAVA/C++和haskell的17重载，多态17，
167类型类typeclass~~接口interface
197泛型实现javaVShaskell
148
199用类型系统实现完整的lamdba演算系统，一如在冯诺依曼体系上建立一个冯诺依曼体系结构的VM，bosh，实验楼，英真实验，一个操作系统虚拟机。。。异曲同工，诺兰红辣椒停机问题鸡生蛋庄生晓梦迷蝴蝶的梦中梦，无穷嵌套悖论。



# Haskell最权威参考就是文档




https://downloads.haskell.org/~ghc/8.6.3/docs/html/users_guide/ghci.html





>知乎有人推荐Haskell的常规路径大概是：
文法 --\> lambda运算 --> 简单类型和函数类型 --> 代数数据类型 --> 类型类，高阶类型和范畴 --> 面向组合子编程 --> 编译器魔>法，DSL和协议建模等等 --> 程序正确性证明（雾


## 看Stackage/Hackage/Hoogle文档学习才是真正的学习方法

cabal run/build/clean/sdist/upload *.gz

``` haddock Main.hs -o -o ./doc```把注释生成Doc文档，cabal haddock自动生成文档

**Hackage大部分文档函数库附带详细的模块文档，其中模块功能，包含的数据类型，绑定等信息简单介绍，附带重要的类型类。**通过阅读类型说明，可以快速理解这套函数库的全部原理与功能。





#  Notes-数据结构+算法

**It proves the equivalence of Turing and church in engineering, graph theory, data structure budget method and knowledge ecological wheel.**

## 算法

okmij.org/ftp/Haskell/AlgorithmsH1.html

举一反三很难的，purely是本好书。

中文的话，算法新解很有味道。

算法还是要做题才能学会呀，理解原有的思路，举一反三很难的，兔法也好，龟法也罢，不过兔法防秃发。

## Haskell 常用数据结构
>在haskell中，控制结构是建立在数据结构之上的，数据结构本身就是控制结构《魔力haskell》
www.voidcn.com/article/p-wvxzhfbz-be.html

www.voidcn.com/article/p-ymptfdsh-be.html

www.voidcn.com/article/p-enyaokzx-buy.html

www.voidcn.com/article/p-amgeivnt-be.html

www.voidcn.com/article/p-yxazuhkc-be.html

www.voidcn.com/article/p-akhkexxv-bsm.html

### purely functional data structures《一本很好的英文书》
图书馆看到过，作者还有一本函数式程序设计，习题都有答案在章末，很好。


https://www.zhihu.com/question/53804334

https://github.com/bos/critbit


https://github.com/tree-sitter/haskell-tree-sitter

###  图网络规划树森算法？




### 树
github项目：BinaryTreeHouse

Haskell中如何代价最小的操作（插入、删除）一棵树？

https://www.zhihu.com/question/57629878/answer/153676557

### 列表





### hash table







https://github.com/gregorycollins/hashtables



### 栈

https://hackage.haskell.org/package/priority-queue-0.2.2







### 队列
https://stackoverflow.com/questions/11471230/haskell-fifo-queue-algorithm-complexity


## "小白文"和不动点递归替代循环技巧

```javascript
function givemefive (xs){
    var Result = [];
    for(var l= xs.length,i=0;i<1;i++){
    if(i%5==0){
        Result.push(xs[i]);
    }
   }
   return Result;
   
}

```

尾递归
现算被子装水过程，盒子装数字过程，独立出来的变量使平台无关(代码实现越基础代表硬件无关，大数计算实现更加抽象可靠1234567890987654321*1234567890098765432333333333333345678999999999999999876543211111111111111112345666666都能算出来不会出现溢出之类的程序员想不到的意外！包括it*it还可以算！这也太神奇了吧。但是sin(pi/6)还是0.49999999994没办法变成0.5？如何精准数学运算？符号解？)+防止“千年问题”+没有NULL安全，基石稳固因为学习本质就应该从搭积木最原始的bingdings和递归等放诸四海皆用的道理开始，越抽象普世性越强越难学，越具体越容易出bug的时候不知道到底问题出在哪儿。比如没人管理的python packages，环境安装都头痛，linux系统会好很多，windows不开源唯一解决办法就是打包MingGW有上百份gcc！
站在巨人肩膀上的可能是 懒人，是废人，淹没在一堆复杂度超乎常理的 troubles from" a lower level of abstraction".只会调包的废人比不过会做积木的工匠！做tensorflow远比会用tensorflow牛逼太多了。

这，才是知识！所以需要学习！C++用OJ的gcc有原因的，Visual Studio 什么鬼“printf_s,scanf_s”什么鬼预编译头，

会用C+++emacs+gcc写算法题就够了！！！！！

数据结构和算法，闭着眼睛写出来不是背诵，是理解之后才能记住！是举一反三！只有懒人才会不努力就认为别人死记硬背下来很简单。其实很难的，理解举一反三，德配其位才是最重要的！




```haskell
giveMeFive :: [a]->[a]
giveMeFive xs= giveMeFiveHelper 0 xs

giveMeFiveHelper :: Int->[a]->[a]
giveMeFiveHelper _ []->[]
giveMeFiveHelper i (x:xs)=
    if `rem`5==0 then x:giveMeFiveHelper (i+1) xs
                else giveMeFiveHelper (i+1 ) xs



```

改进


```haskell
giveMeFive::[(Int,a)]->[a]
giveMeFive []=[]
giveMeFive ((i,x):xs)=
    if i `rem`5 ==0 then x:giveMeFive xs
                    else giveMeFive xs
                    

```
giveMeFive(Zip[0..][0..100])









## 如何用flodr实现flodl



https://www.cnblogs.com/flytrace/archive/2012/02/19/haskell.html

```haskell
foldl :: (a->b->a)->a->[b]->a
foldl f a bs = foldr(\b g x ->(f x b))id bs a


{-
comments
foldl f a bs = (foldr(\b g x ->(f x b))id bs) a




-}

```
## 树的编程技巧












## 伊塔转换
$$/eta$$  -conversion

韩冬魔力haskell书本P49说这里蕴含道理是：证明两个函数相等的唯一办法，就是证明所有输入的情况下，两个函数输出相等。

想起来张淞书上说，排序算法呢？算法复杂度不一样呀，输入输出一样呀，殊途同归，但是怎么走这条路很重要的。


```haskell

data Position = Cartesian Double Double |Polar Double Double
--Cartesian 3 4 == Polar 0.9272952180016123 5

instance Eq Position where
  Cartesian x1 y1 == Cartesian x2 y2 =(x1==x2)&&(y1==y2)
  Polar x1 y1 == Polar x2 y2 = (x1==x2)&&(y1 == y2)
  Cartesian x y == Polar a r = (x==r*cos a)&& (y==r*sin a)
  Polar a r == Cartesian x y = (x==r*cos a)&& (y==r*sin a)
  

  

```



```haskell

import Control.Concurrent

main = do
  tid1 <- forkIO $ forever $ do
    threadDelay 1000000
    putStrLn "hello"
  threadDelay 500000
  tid2 <- forkIO $forever $ do
    threadDelay 1000000
    putStrLn "world"
  putStrLn $ "Two Thread are runing at"++
      show tid1 ++ "and" ++ show tid2 ++"."
      threadDelay 1000000
```



## 词汇表









saturated饱和      
fully applied完全应用





arity参数数量






nullary/unary/binary/ternary零一二三元



closure 闭包，函数体内引用了外围作用域中的自由变量free variable的函数


combinator 自由函数，闭包反义词，不包含自由变量的函数。

















## 高级数据结构

## 高级类型编程

Typeable And Dynamic


type families

Data families

GADT




datakinds数据类别


