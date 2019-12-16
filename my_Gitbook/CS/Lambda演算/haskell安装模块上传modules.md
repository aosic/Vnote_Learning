# haskell安装模块上传modules

安装
Haskell 中的模块是含有一组相关的函数，类型和类型类的组合。而 Haskell 进程的本质便是从主模块中引用其它模块并调用其中的函数来执行操作。这样可以把代码分成多块，只要一个模块足够的独立，它里面的函数便可以被不同的进程反复重用。这就让不同的代码各司其职，提高了代码的健壮性。
https://www.bbsmax.com/A/WpdKgaKAdV/

在 Haskell中，装载模块的语法为 import，这必须得在函数的定义之前，所以一般都是将它置于代码的顶部。无疑，一段代码中可以装载很多模块，只要将 import 语句分行写开即可。装载 Data.List 试下，它里面有很多实用的 List 处理函数.

import Geometry
将 Geometry.hs 文件至于用到它的进程文件的同一目录之下.


模块也可以按照分层的结构来组织，每个模块都可以含有多个子模块。而子模块还可以有自己的子模块。我们可以把 Geometry分成三个子模块，而一个模块对应各自的图形对象.

首先，建立一个 Geometry 文件夹，注意首字母要大写，在里面新建三个文件

如下就是各个文件的内容:

sphere.hs



























#  module工程

大抵说下我学习用cabal来build以及引用build的module的心得吧。

假定你是用Linux的（我用的ubuntu,windows下没有做过尝试）。

一个传统的流程是：
1. cabal init，就会创建一个project
2. 在创建的project目录中编写代码
3. 测试完成后， 修改project目录中的.cabal配置文件， 然后cabal configure，cabal build
4. cabal build

如果按照上面的流程走下去，那么编写的library或者executable会被安装到~/.cabal中去，可以直接引用了。

不过目前似乎更提倡使用sandbox来build，使用sandbox的流程是：
1. cabal init
2. cabal sandbox init
3. 编写代码，以及修改.cabal文件
4. cabal configure
5. cabal build
6. cabal install

这个时候，project不是被安装到了~/.cabal，而是被安装到了你的project目录中的.cabal-sandbox中，此时，如果别的本地project想要引用这个project，需要使用cabal sandbox add-source /path/to/dependency/library/

1. 导入
（1）import Data.List
导入Data.List.*，但是不会导入子模块

（2）import Data.List (permutations, subsequence)
只导入Data.List模块中的permutations和subsequence

（3）import Data.List hiding (head, tail)
导入Data.List.*，除了head和tail

（4）import Chapter3.ParamPoly (Client())
只导入类型，不导入值构造器

（5）import Chapter3.ParamPoly (Client(GovOrg,Individual))
导入类型，以及一部分值构造器

（6）import Chapter3.ParamPoly (Client(..))
导入类型，以及所有的值构造器

（7）import qualified Data.List (filter, permutations)
以带限定名的方式导入，使用方式为Data.List.filter

（8）import qualified Data.List as L
以带限定名的方式导入，并修改限定名，使用方式为L.filter
又例如，import qualified Data.List (permutations, subsequences) as L

2. 导出
（1）module M where
导出所有的type class，type，value

（2）module M (f) where
只导出f

（3）module Chapter2.DataTypes (ConnOptions(), connDefault) where
只导出ConnOptions类型，以及导出connDefault

注：
如果不导出值构造器，其他模块中如果用到值构造器产生编译错误https://www.jianshu.com/p/0ac339f79001

 2016.03









只需要在cmd或terminal更改当前目录至本地模块文件夹中，输入命令ghci，Enter, 然后:l <module_name>

记得采纳。







----------------------


https://segmentfault.com/a/1190000002753143







上传



# cabal init
C:\Users\admin\Documents\Tridu33\!jobswork\!数据结构课程设计\maze-solver-haskell>cabal init
Please choose version of the Cabal specification to use:
 * 1) 1.10   (legacy)
   2) 2.0    (+ support for Backpack, internal sub-libs, '^>=' operator)
   3) 2.2    (+ support for 'common', 'elif', redundant commas, SPDX)
   4) 2.4    (+ support for '**' globbing)
Your choice? [default: 1.10   (legacy)]
Package name? [default: maze-solver-haskell] tridu33
Package version? [default: 0.1.0.0]
Please choose a license:
   1) GPL-2
   2) GPL-3
   3) LGPL-2.1
   4) LGPL-3
   5) AGPL-3
   6) BSD2
 * 7) BSD3
   8) MIT
   9) ISC
  10) MPL-2.0
  11) Apache-2.0
  12) PublicDomain
  13) AllRightsReserved
  14) Other (specify)
Your choice? [default: BSD3] 8
Author name? Tridu33
Maintainer email? 2055969978@qq.com
Project homepage URL? tridu33.github.io.com
Project synopsis?
Project category:
 * 1) (none)
   2) Codec
   3) Concurrency
   4) Control
   5) Data
   6) Database
   7) Development
   8) Distribution
   9) Game
  10) Graphics
  11) Language
  12) Math
  13) Network
  14) Sound
  15) System
  16) Testing
  17) Text
  18) Web
  19) Other (specify)
Your choice? [default: (none)] 12
What does the package build:
   1) Library
   2) Executable
   3) Library and Executable
Your choice? 3
What is the main module of the executable:
 * 1) Main.hs (does not yet exist, but will be created)
   2) Main.lhs (does not yet exist, but will be created)
   3) Other (specify)
Your choice? [default: Main.hs (does not yet exist, but will be created)] 1
Source directory:
 * 1) (none)
   2) src
   3) Other (specify)
Your choice? [default: (none)] 2
What base language is the package written in:
 * 1) Haskell2010
   2) Haskell98
   3) Other (specify)
Your choice? [default: Haskell2010]
Add informative comments to each field in the cabal file (y/n)? [default: n]

Guessing dependencies...

Generating LICENSE...
Generating Setup.hs...
Generating CHANGELOG.md...
Generating src\Main.hs...
Generating tridu33.cabal...

Warning: no synopsis given. You should edit the .cabal file and add one.
You may want to edit the .cabal file and add a Description field.


















