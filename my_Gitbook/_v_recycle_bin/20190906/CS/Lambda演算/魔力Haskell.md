# 《魔力haskell》_Some-Notes，学会看Doc学Haskell


## DS,在haskell中，控制结构是建立在数据结构之上的，数据结构本身就是控制结构

### 列表Data.List


**不要在需要大量随机访问和需求大量拼接的场合用列表，以避免列表遍历O（m为被更新数据下标）带来的时间消耗**

```haskell

*Main> listA=[1,2,3,4]
*Main> listA
[1,2,3,4]
*Main> tail listA
[2,3,4]
*Main> listA
[1,2,3,4]
*Main> foo[a,b,c,d]=a
*Main> foo listA
1
*Main> foo (a:b:c:d)=d
*Main> foo listA
[4]
*Main> foo (a:b:c)=c
*Main> foo listA
[3,4]
*Main> foo (a:b:c:d:e)=e
*Main> foo listA
[]

*Main> foo (a:b:[c,d])=d
*Main> foo listA
4

--取出指定下标的数字
Prelude> :i !!
(!!) :: [a] -> Int -> a 	-- Defined in ‘GHC.List’

Prelude> [1,2,3]!!2
3
Prelude> [1,2,3]!!10
*** Exception: Prelude.!!: index too large
--!! _=error"Exception: Prelude.!!: index too large"


无穷列表一定要学会取出前特定几个，套进去任何无穷列表看出来。take 10 [1..]
{-
看Doc自学haskell函数举例子
Prelude> :i take
take :: Int -> [a] -> [a] 	-- Defined in ‘GHC.List’
Prelude> :t take
take :: Int -> [a] -> [a]
然后浏览器打开官方htmlDoc教程，或者说直接打开winGHC的？按钮帮助页面自动跳转，找到map对应教程
--C:/Program%20Files/Haskell%20Platform/8.6.3/doc/html/libraries/base-4.12.0.0/GHC-List.html安装目录下Doc
--C:/Program%20Files/Haskell%20Platform/8.6.3/doc/html/libraries/base-4.12.0.0/src/GHC.Base.html#take

take :: [Int](Data-Int.html#t:Int "Data.Int") -\> [a] -> [a][Source](src/GHC.List.html#take)[#](#v:take)

`[take](GHC-List.html#v:take "GHC.List")` `n`, applied to a list `xs`, returns the prefix of `xs` of length `n`, or `xs` itself if ``n > `[length](GHC-List.html#v:length "GHC.List")` xs``:

take 5 "Hello World!" == "Hello"
take 3[1,2,3,4,5] == [1,2,3]
take 3 [1,2] == [1,2]
take 3 [] == []
take (-1) [1,2] == []
take 0 [1,2] == []

It is an instance of the more general `[genericTake](Data-List.html#v:genericTake "Data.List")`, in which `n` may be of any integral type.


Prelude> take 10 (iterate (+1) 1)
[1,2,3,4,5,6,7,8,9,10]

--
Prelude> let xs= iterate (+1) 1
Prelude> take 10 xs
[1,2,3,4,5,6,7,8,9,10]

--诸如此类，都可以类推得到


:i length 
:t length
Prelude> length [[1,2,3,4],[4,3],[1]]
3
Prelude> length [[1,2,3,4],[4,3],[1]]
3
Prelude> init [1,2,3]
[1,2]
Prelude> last [1,2,3]
3
Prelude> take 2 [1,2,3]
[1,2]
Prelude> drop 2 [1,2,3]
[3]
Prelude> replicate 3 1
[1,1,1]

--边界条件+迭代递归规则



```


#### 常用的列表操作：映射，过滤，折叠和扫描
Prelude> :i filter
filter :: (a -> Bool) -> [a] -> [a] 	-- Defined in ‘GHC.List’
查看位置
C:/Program%20Files/Haskell%20Platform/8.6.3/doc/html/libraries/base-4.12.0.0/GHC-List.html
映射，


```haskell
看到下列说明
map :: (a -> b) -> [a] -> [b] Source#点击这里源码的定义甚至都告诉了你

map f xs is the list obtained by applying f to each element of xs, i.e.,
有应用例子，直接看懂map映射的写法。
map f [x1, x2, ..., xn] == [f x1, f x2, ..., f xn]
map f [x1, x2, ...] == [f x1, f x2, ...]
-}

```
大数据处理领域map-reduce，一般map对数据进行相同的处理，然后就是reduce，把第一部得到的数据聚合flodl成想要的结果。

过滤是对顺序操作的抽象

```haskell
filter :: (a -> Bool) -> [a] -> [a] Source#

filter, applied to a predicate and a list, returns the list of those elements that satisfy the predicate; i.e.,

filter p xs = [ x | x <- xs, p x]

filter even [1..10]
Prelude Data.List> filter even [1..10]
[2,4,6,8,10]
Prelude Data.List> even 4
True





```


折叠，几乎所有迭代处理的函数都可以用折叠foldl来实现

```haskell
Prelude Data.List> foldl (+) 0 [1..100]
5050

Prelude Data.List> foldl (+) 0 [1..3]
{-
foldl (+) 0 [1..3]
foldl (+)((+) 0 1)[2,3]
foldl (+)((+) ((+)0 1)2)[3]
foldl (+)((x)((+) ((+)0 1)2)3)[]
((x)((+) ((+)0 1)2)3)
((+) ((+)0 1)2)+3
((+)0 1)+2+3
((0+1)+2)+3

-}
6

Prelude Data.List> foldr (+) 0 [1..3]
{-
foldl (+) 0 [1,2,3]
(+) (foldr (+) 0 [2,3])1
(+) ((+)(foldr (+) 0 [3])2)1
(+) ((+)((+)(foldr (+) 0 [])3)2)1
(+) ((+)((+) 0 3)2)1
(+)((+) 0 3)2+1
((+) 0 3)+2+1
((0+3)+2)+1
-}


6


```





扫描,折叠时累计每一步迭代递归



```haskell
Prelude Data.List> scanr (+) 0 [1..3]
[6,5,3,0]
Prelude Data.List> scanl (+) 0 [1..3]
[0,1,3,6]

```



有点有意思的是


```haskell

Prelude> xs = iterate (+1) 1
Prelude> take 5 xs
[1,2,3,4,5]


Prelude> xs = iterate' (+1) 1

<interactive>:143:6: error:
    ? Variable not in scope:
        iterate' :: (Integer -> Integer) -> Integer -> t
    ? Perhaps you meant ‘iterate’ (imported from Prelude)

像是不存在，可能是弱常态严格版本要开启扩展之类的才能用

新建一个tmp.hs然后写如下列Doc查到的源码：
-- | 'iterate\'' is the strict version of 'iterate'.
--
-- It ensures that the result of each application of force to weak head normal
-- form before proceeding.
{-# NOINLINE [1] iterate' #-}
iterate' :: (a -> a) -> a -> [a]
iterate' f x =
    let x' = f x
    in x' `seq` (x : iterate' f x')

然后
Prelude> :load "tmp.hs"
[1 of 1] Compiling Main             ( tmp.hs, interpreted )
Ok, one module loaded.
*Main> xs = iterate' (+1) 1
*Main> take 5 xs
[1,2,3,4,5]
成功

```



### 元组

C:/Program%20Files/Haskell%20Platform/8.6.3/doc/html/libraries/ghc-prim-0.5.3/GHC-Tuple.html


同理Data.Tuple，一看就懂，超级贴心的教程。

```haskell
Documentation
fst :: (a, b) -> a Source#

Extract the first component of a pair.

snd :: (a, b) -> b Source#

Extract the second component of a pair.

curry :: ((a, b) -> c) -> a -> b -> c Source#

curry converts an uncurried function to a curried function.

Examples
uncurry :: (a -> b -> c) -> (a, b) -> c Source#

uncurry converts a curried function to a function on pairs.

Examples
>>> uncurry (+) (1,2)
3
>>> uncurry ($) (show, 1)
"1"
>>> map (uncurry max) [(1,2), (3,4), (6,8)]
[2,4,8]
swap :: (a, b) -> (b, a) Source#

Swap the components of a pair.

```



### 数组

```haskell


```





array函数库


vector函数库

repa函数库建立在vector上，能多维度数组处理，图像处理等，对应repa-algorithm函数库有很多数据处理模块，包括FFT,卷积等，试验中


accelerate函数库，基于array编写的面向GPU并行处理的数组函数库，后端accelerate-cuda,accelerate-opengl要硬件支持


还有很多特殊需求的的carray,bit-array。。。。。。







### hash
HashTable函数库提供ST单子中传统可变散列表的实现，
，包括，Basic，Cuckoo（http://en.wikipedia.org/wiki.Cuckoo_hashing）,Linear(http://en.wikipedia.org/wiki.Linear_hashing)  三种不同算法的散列表来实现

想用可以在Dataa.HashTable.IO模块中提供的封装函数实现，


```haskell


```



```haskell


```



```haskell


```



```haskell


```


```haskell


```








### 栈

https://hackage.haskell.org/package/priority-queue-0.2.2


### 队列
https://stackoverflow.com/questions/11471230/haskell-fifo-queue-algorithm-complexity

### hash等等略



## 八皇后---列表单子结构控制函数

### l列表单子数组归纳八皇后



```haskell

Prelude> :{
Prelude| do
Prelude|   x<-[1,2,3]
Prelude|   y<-[4,5,6]
Prelude|   return $ x * y
Prelude| :}
[4,5,6,8,10,12,12,15,18]




```





```haskell
--list comprehension列表归纳

Prelude> [x*y|x<-[1,2,3],y<-[4,5,6]]
[4,5,6,8,10,12,12,15,18]
Prelude> [x*y|x<-[1..3],y<-[x..6]]
[1,2,3,4,5,6,4,6,8,10,12,9,12,15,18]
Prelude> [x*y|x<-[y..3],y<-[x..6]]

<interactive>:16:10: error: Variable not in scope: y

Prelude> [x*y|x<-[1..10],y<-[x..10]]
[1,2,3,4,5,6,7,8,9,10,4,6,8,10,12,14,16,18,20,9,12,15,18,21,24,27,30,16,20,24,28,32,36,40,25,30,35,40,45,50,36,42,48,54,60,49,56,63,70,64,72,80,81,90,100]
Prelude> [x*y|x<-[1..10],y<-[x..10],x+y<10]
[1,2,3,4,5,6,7,8,4,6,8,10,12,14,9,12,15,18,16,20]
Prelude> [x*y|x<-[1..10],y<-[x..10],(x+y<10)&&(x+y>4)]
[4,5,6,7,8,6,8,10,12,14,9,12,15,18,16,20]
Prelude> [x*y|x<-[1..10],y<-[x..10],x+y<10&&x+y>4]
[4,5,6,7,8,6,8,10,12,14,9,12,15,18,16,20]


:{
do 
	x<-[1..10]
	y<-[x..10]
	if x+y <10
		then return x * y
		else []





:}


```


### 八皇后

#### 魔力haskell动态规划

```haskell
module Queens where

import Control.Monad

safe :: Int -> [Int] -> Int -> Bool
safe _ [] _ = True
safe x (x1:xs) n =
    x /= x1
    && x /= x1 + n && x /= x1 - n
    && safe x xs (n+1)

queensN :: Int -> [[Int]]
queensN n = queens n
  where
    queens 0 = [[]]
    queens m = [ x : y | y <- queens (m-1), x <- [1..n], safe x y 1]


main :: IO ()
main = forM_ [5..10] $ \n -> do
    putStrLn $ "Solutions for queen" ++ show n ++ " problem:"
    let solutions = queensN n
    forM_ solutions $ print


```


#### 张淞《》章节八皇后回溯方法

排列组合全排列插入法矩阵乘法组合数学


```haskell
--全排列
-- Permutation.hs
insert :: a -> [a] -> [[a]]
insert n [] = [[n]]
insert n (n':ns) = (n:n':ns):[n':ns'|ns'<-insert n ns]

permutation [] = [[]]
permutation (x:xs)= concat [insert x permuxs|permuxs<-permutation xs]





```





```haskell


```











```haskell
-- EightQueens.hs
import Data.List (permutations)
positions 0 n = [[]]
positions k n = [x:xs|  x <- [1..n], xs <- positions (k-1) n]

noSameRow [] = True
noSameRow (x:xs) = (not $ elem x xs) && noSameRow xs

noSameDiag [] = True
noSameDiag xs@(x:xs') = and [abs (i1-i)/=abs (p1-p)|(i,p)<-ip] && noSameDiag xs'
                where (i1,p1):ip = zip [1..] xs

queen n = [xs| xs <- positions n n, noSameRow xs, noSameDiag xs]

positions' 0 n = [[]]
positions' k n = [p:ps| ps<-positions' (k-1) n,p <- [1..n], isSafe p ps]

isSafe p ps = not ((elem p ps) || (sameDiag p ps))
     where sameDiag p ps = any (\(dist,q) -> abs (p-q)==dist) $ zip [1..] ps

queens = positions' 8 8

queens' :: Int -> [[Int]]
queens' n = [xs| xs <- permutations [1..n], noSameDiag xs]

```


### MonadPlus
与选择应用函子Applicative（Control.Applicative）类似，选择单子类型类MonadPlus，定义在Control.Monad

```haskell  
Prelude> import Control.Monad
Prelude Control.Monad> :i MonadPlus
class (GHC.Base.Alternative m, Monad m) =>
      MonadPlus (m :: * -> *) where
  mzero :: m a
  mplus :: m a -> m a -> m a
  	-- Defined in ‘GHC.Base’
instance MonadPlus [] -- Defined in ‘GHC.Base’
instance MonadPlus Maybe -- Defined in ‘GHC.Base’
instance MonadPlus IO -- Defined in ‘GHC.Base’


Prelude Control.Monad> :k MonadPlus
MonadPlus :: (* -> *) -> Constraint
```







  

##  ！结构控制函数

可组合的判断循环功能，

具体使用例子《魔力haskell》有写，

还可以看官方教程Doc的Example使用说明

或者stackflow


### sequence/sequence_

```haskell

Prelude Control.Monad> :i sequence
class (Functor t, Foldable t) => Traversable (t :: * -> *) where
  ...
  sequence :: Monad m => t (m a) -> m (t a)
  	-- Defined in ?瓺ata.Traversable’



```
### mapM/mapM_  forM/forM_

```haskell
Prelude Control.Monad> :i mapM
class (Functor t, Foldable t) => Traversable (t :: * -> *) where
  ...
  mapM :: Monad m => (a -> m b) -> t a -> m (t b)
  ...
  	-- Defined in ‘Data.Traversable’

:i forM
forM :: (Traversable t, Monad m) => t a -> (a -> m b) -> m (t b)
  	-- Defined in ‘Data.Traversable’



```



forM :: (Traversable t, Monad m) => t a -> (a -> m b) -> m (t b) Source#

forM is mapM with its arguments flipped. For a version that ignores the results see forM_.






### replicateM/replicateM_

```haskell

Prelude Control.Monad> :i replicateM
replicateM :: Applicative m => Int -> m a -> m [a]
  	-- Defined in ‘Control.Monad’





```
### forever

```haskell
Prelude Control.Monad> :i forever
forever :: Applicative f => f a -> f b
  	-- Defined in ‘Control.Monad’


```
### filterM

```haskell

Prelude Control.Monad> :i filterM
filterM :: Applicative m => (a -> m Bool) -> [a] -> m [a]
  	-- Defined in ‘Control.Monad’

```
### foldM/foldM_





```haskell

  Prelude Control.Monad> :i foldM
foldM ::
  (Foldable t, Monad m) => (b -> a -> m b) -> b -> t a -> m b
  	-- Defined in ‘Control.Monad’

  

```




### IFElse/Monad-Loops/Concatenative......

IFElse
https://hackage.haskell.org/package/ifElse


Monad-Loops
https://hackage.haskell.org/package/monad-loops

Concatenative
https://hackage.haskell.org/package/concatenative




# 语言扩展编译原理函数库过程分析等+快速检查

## 开启扩展

源文件

```haskell
{-# LANGUAGE MultiWayif #-}
```


开启扩展，或者winGHC``` ：set -XMultiwayIf```


# 标记语义常态弱常态


为了解决任务盒堆积问题，需要了解：

标记语义denotational semantics/referential transparency应用透明原则:inline,simplify,fusion优点，缺点是函数调用被core优化掉都不自知

## 调试求值过程


：print 大多用在获取一个多态polymorphism类型的绑定在某个时刻的具体类型。 


：print  尝试在不求值的情况下，打印绑定的相关信息。如果遇到任务盒，则会在打印出的绑定名称前加上_表示这是一个没被求值的任务盒


:sprint    和：print类似，但不会绑定新的变量名。如果遇到任务盒，简单显示为_

:force  和：print类似，但是会强制对绑定的表达式求值


例子：sprint


```haskell
Prelude> let a= 1+1::Int
Prelude> :sprint a
a = _
Prelude> :print a
a = (_t1::Int)
Prelude> a
2
Prelude> :sprint a
a = 2
Prelude> import Data.List
Prelude Data.List> let a=sort[1,23,4,6,1,6,2,3]::[Int]
Prelude Data.List> :sprint a
a = _
Prelude Data.List> take 3 a
[1,1,2]
Prelude Data.List> :sprint a
a = 1 : 1 : 2 : _

--：sprint查看数字类型时要声明类型说明，比如Int,[Int]，如果不声明Num a=1+1在每次查看a时都会重新求值
--对比
Prelude Data.List> let a=sort[1,23,4,6,1,6,2,3]
Prelude Data.List> :sprint a
a = _
Prelude Data.List> take 3 a
[1,1,2]
Prelude Data.List> :sprint a
a = _       --所以这里还是任务盒




```



完全求值之后的表达式叫做常态normal form


```haskell
Prelude Data.List> let a=sort[1,23,4,6,1,6,2,3]::[Double]
Prelude Data.List> :sprint a
a = _
Prelude Data.List> last a
23.0
Prelude Data.List> :sprint a
a = [1.0,1.0,2.0,3.0,4.0,6.0,6.0,23.0]
--常态a

```
弱常态weak head normal form有几种情况：
1. 形如\x-> ... 匿名表达式，如\x->2+2
2. 某些不饱和内置函数，（+2）sqrt...
3. 表达式最外层函数是一个构造函数，例如”（1+1，2+2），“最外层是构造函数“，”

```haskell
Prelude Data.List> let a=sort["Hello","World"]
Prelude Data.List> :sprint a
a = _
Prelude Data.List> length a
2
Prelude Data.List> :sprint a
a = [('H' : _),('W' : _)]


```


弱常态求值状态不是最终常态，弱常态共同特点：底层中的表示和计算任务（一定是函数应用形式）不同

韩冬说几点重要的：

- 所有使用构造函数创建的数据都处于弱常态
- 弱常态可以成为一个任务盒，比如匿名函数传参数
- 弱常态表达式可能包含任务盒，比如（1+2，7+2）中任务盒1+2
- 弱常态想变成常态必须最全部完成
- 任务盒求值往往是新的弱常态

## seq（$!）/deepseq第一个参数完全求值($!)函数应用前把参数求值为常态/force x把x求值为常态,副作用版id
call-by-need   

为了解决任务盒堆积问题，强迫计算任务盒seq/deepseq




foldlseq.hs


```haskell

module Main where

foldl2 :: (b->a->b)->b->[a]->b
foldl2 _ acc []=acc
foldl2 f acc (x:xs)=
       let acc'=f acc x
       in seq acc' (foldl2 f acc' xs)
x=foldl2 (+) 0 [1..10000000]::Int
main=print x

```




foldl.hs



```haskell


module Main where

foldl2 :: (b->a->b)->b->[a]->b
foldl2 _ acc []=acc
foldl2 f acc (x:xs)=foldl f (f acc x)xs
x=foldl2 (+) 0 [1..10000000]::Int
main=print x

```

编译执行GHC能看出明显快慢。

```shell
ghc foldlseq.hs
foldlseq.exe
--快很多
ghc foldl.hs
foldl.exe



```




严格性分析strictness anaysis  判读哪些函数一定会被求值，消除惰性求值任务盒堆积

# 看Stackage/Hackage文档学习才是真正的变成的语言学习方法，用到什么学什么么查什么

cabal run/build/clean/sdist/upload *.gz

``` haddock Main.hs -o -o ./doc```把注释生成Doc文档，cabal haddock自动生成文档

**Hackage大部分文档函数库附带详细的模块文档，其中模块功能，包含的数据类型，绑定等信息简单介绍，附带重要的类型类。**通过阅读类型说明，可以快速理解这套函数库的全部原理与功能。




## 《the Haskell Report》一定要打印出来的manual电子书
https://www.haskell.org/onlinereport/haskell2012/
下载
https://www.haskell.org/definition/haskell2012.pdf/

```haskell
-- 注释
{-
注释
-}

```


### 魔力haskell------magic-haskell.com

### 《张淞》

















# 尾递归代替循环技巧

## "小白文和"不动点递归替代循环技巧

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


尾递归ba
现算被子装水过程，盒子装数字过程，独立出来的变量使
平台无关(代码实现越基础代表硬件无关，大数计算实现更加抽象可靠1234567890987654321*1234567890098765432333333333333345678999999999999999876543211111111111111112345666666都能算出来不会出现溢出之类的程序员想不到的意外！包括it*it还可以算！这也太神奇了吧。但是sin(pi/6)还是0.49999999994没办法变成0.5？如何精准数学运算？符号解？

)+防止“千年问题”+没有NULL安全，基石稳固因为学习本质就应该从搭积木最原始的bingdings和递归等放诸四海皆用的道理开始，越抽象普世性越强越难学，越具体越容易出bug的时候不知道到底问题出在哪儿。比如没人管理的python packages，环境安装都头痛，linux系统会好很多，windows不开源唯一解决办法就是打包MingGW有上百份gcc！
站在巨人肩膀上的可能是 懒人，是废人，淹没在一堆复杂度超乎常理的 troubles from" a lower level of abstraction".只会调包的废人比不过会做积木的工匠！做tensorflow远比会用tensorflow牛逼太多了。
这，才是知识！所以需要学习！C++用OJ的gcc有原因的，垃圾Visual Studio 神他妈“printf_s,scanf_s”神他妈预编译头，
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



# 如何用flodr实现flodl



https://www.cnblogs.com/flytrace/archive/2012/02/19/haskell.html

```haskell
foldl :: (a->b->a)->a->[b]->a
foldl f a bs = foldr(\b g x ->(f x b))id bs a


{-
comments
foldl f a bs = (foldr(\b g x ->(f x b))id bs) a




-}

```
# 树的递归技巧












# 伊塔转换
$$/eta$$  -conversion 韩冬P49说证明两个函数相等的唯一办法，就是证明所有输入的情况下，两个函数输出相等。张淞书上说，排序算法呢？算法复杂度不一样呀。


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



# 词汇表









saturated饱和      
fully applied完全应用





arity参数数量






nullary/unary/binary/ternary零一二三元



closure 闭包，函数体内引用了外围作用域中的自由变量free variable的函数


combinator 自由函数，闭包反义词，不包含自由变量的函数。







