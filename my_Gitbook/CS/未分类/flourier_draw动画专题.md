# 傅里叶动画专题和生态完善flourier_draw
 ## 前置知识
[原理教程可以先看视频了解下](https://www.bilibili.com/video/av49238862)
[想看更多可以点这儿。](https://www.youtube.com/watch?v=qS4H6PEcCCA)

[玩玩看](https://brettcvz.github.io/epicycles/)
[更多在线玩耍](www.jezzamon.com/fourier/index.html)

实际上我更加建议看知乎《掐死教程》，3b1b卷起来积分求重心的奇趣思路，还有教材和papers。


## Open-Projects
 >C语言版本演示：https://www.bilibili.com/video/av61073276
http://www.bilibili.com/video/av61073276  傅里叶画图               
https://github.com/TheKOG/Fourier_Draw 用c程序
简单介绍一下算法吧(反正也没人看QAQ)
首先用边缘算子提取出位图轮廓点, 然后对点集进行三角剖分得到O(n)条边形成的图(Delaunay算法), 然后在图的基础上求最小生成树(kruskal算法), 然后求出树的直径, 从直径一端出发遍历整棵树, 并按遍历顺序记录点序列, 最后对点序列(也就是一条路径)进行平滑处理(Douglas算法);
考虑点序列同时也是向量序列, 所以对点序列进行傅里叶变换(FFT), 然后在用逆离散傅里叶变换进行曲线拟合(IDFT).
 
 >mathworld.wolfram.com › FourierSeries.html
Fourier Series -- from Wolfram MathWorld傅里叶mma项目 
https://mathematica.stackexchange.com/questions/171755/how-can-i-draw-a-homer-with-epicycloids.     实锤了，Mma就是拿来玩的。感觉这里的原理，代码演示和实现过程，举例，说得很明白了。


>https://zhuanlan.zhihu.com/p/72632360  可达鸭教程
>python
>https://github.com/biran0079/circle.git.  
 
>前端项目
>https://github.com/andymac-2/fourier-polygon
>在线演示
>https://andymac-2.github.io/fourier-polygon/

 >https://github.com/ruanluyu/FourierCircleDrawing.git 中梓星音
 >计算程序是MIT开源的。介绍视频看av28374720。
 >源码仓库上了，里面还有对于贝塞尔曲线转换的简单技术性描述文档，有闲心可以来读读（https://github.com/ruanluyu/FourierCircleDrawing）。
 >网页端 http://fcd.milai.tech/ 点下面的run按钮就能计算。play能播放动画。你想画自己的形状就去Ai画个一笔画，然后把svg代码替换掉文本框里的代码就行.
 

都跑过，效果都不错，非常感谢上述以及互联网各种开源网站给我们生活带来的便利和舒适。

之前，用自己头像证件照做成svg做过视频，写这篇文章的目的算是整理下整个傅里叶动图生态和处理流程吧。

就以最后一个为例写个使用教程吧。

**假装有原图**

不敢放上来(-_-#

我真的忘了自己怎么处理自己的证件照的了。

反正就是花点心思，凭着PS选修课的记忆，慢慢调。

搜了两个看着靠谱的教程[1](huanlan.zhihu.com/p/38661540)[2](zhuanlan.zhihu.com/p/71927421)

其实图片操作[matlab](https://blog.csdn.net/tangg555/article/details/73480371)也能直接做。
不过PS能做，我真懒得用matlab。

然后得到近似素描的头像位图。

接着软件VertorMagic矢量图初步转换成SVG矢量图，这个比较关键。当然，位图转矢量图很多方法，用手描肯定好，如果你手残如我，呃...

导入AI进行处理，去除杂点噪声之类的（可以看到，我的头像就是SVG噪点，拟合后耳朵两侧噪点来回波荡，不过我没什么动力在svg一行行代码里修，嫌麻烦）,也可以用SVG专门的编辑器或者网站在线编辑。

AI导出的图像其实就可以直接用了，编过网站，前端能看懂，我发现乍一眼看过去我居然以前不常见path是视频里这种代码的SVG，问了中梓星音UP主本人，没回答我。

我后来琢磨了下，发现他是AI直接导出的。

比较了下，发现其实和我常见的SVG一样，只是路径矢量path后面跟着的不是空格改成逗号，正常我的SVG改成逗号也成。

直接看这三者处理的效果图吧。
![三位一体](_v_images/三位一体_1567323050_12301.jpg)

这三张图片分别是:
ps后的，VectorMagic后的，Ai处理导出处理的SVG。
（只露个1/4脸，这样子应该不会被人认出来了吧）

行了，准备工作差不多了。

对了，有一点这个项目的Up主搞错了，不一定要一笔画的SVG，多笔画SVG和一笔画一样的。



在下面列出了SVG `<path>`元素的虚拟画笔可以使用的命令。大小的指令通常将参数坐标解析为绝对坐标。小写的指令通常将参数坐标解析为相对坐标。

| 指令 | 参数 | 名称 | 描述 |
| --- | --- | --- | --- |
| M | x,y | moveto | 移动虚拟画笔到指定的（x,y）坐标，仅移动不绘制 |
| m | x,y | moveto | 移动虚拟画笔到指定的（x,y）坐标，这个坐标是相对于当前画笔的坐标，仅移动不绘制 |
| L | x,y | lineto | 从当前画笔所在位置绘制一条直线到指定的（x,y）坐标 |
| l | x,y | lineto | 从当前画笔所在位置绘制一条直线到指定的（x,y）坐标，(x,y)坐标是相对于花瓣位置的点 |
| H | x | horizontal lineto | 绘制一条水平直线到参数指定的x坐标点，y坐标为画笔的y坐标 |
| h | x | horizontal lineto | 绘制一条水平直线到参数指定的x坐标点（当前x + 指定的x），x坐标相对于当前画笔x坐标 |
| V | y | vertical lineto | 从当前位置绘制一条垂直直线到参数指定的y坐标 |
| v | y | horizontal lineto | 从当前位置绘制一条垂直直线到参数指定的y坐标，y坐标相对于当前画笔的y坐标 |
| C | x1,y1 x2,y2 x,y | curveto | 从当前画笔位置绘制一条三次贝兹曲线到参数（x,y）指定的坐标。x1，y1和x2,y2是曲线的开始和结束控制点，用于控制曲线的弧度 |
| c | x1,y1 x2,y2 x,y | curveto | 于大小C指令相同，但是坐标是相对于画笔的坐标 |
| S | x2,y2 x,y | shorthand / smooth curveto | 从当前画笔位置绘制一条三次贝兹曲线到参数（x,y）指定的坐标。x2,y2是结束控制点。开始控制点和前一条曲线的结束控制点相同 |
| s | x2,y2 x,y | shorthand / smooth curveto | 和大小的S指令相同，但是坐标是相对于当前画笔的坐标点 |
| Q | x1,y1 x,y | 二次贝兹曲线 | 从当前画笔位置绘制一条二次贝兹曲线到参数（x,y）指定的坐标。x1,y1是控制点，用于控制曲线的弧度 |
| q | x1,y1 x,y | 二次贝兹曲线 | 和大小的Q指令相同，但是坐标是相对于当前画笔的坐标点 |
| T | x,y | 平滑的二次贝兹曲线 | 从当前画笔位置绘制一条二次贝兹曲线到参数（x,y）指定的坐标。控制点被假定为最后一次使用的控制点 |
| t | x,y | 平滑的二次贝兹曲线 | 和大小的T指令相同，但是坐标是相对于当前画笔的坐标点 |
| A | rx,ry x-axis-rotation large-arc-flag,sweepflag x,y | 椭圆弧线 | 从当前画笔位置开始绘制一条椭圆弧线到（x,y）指定的坐标。rx和ry分别为椭圆弧线水平和垂直方向上的半径。x-axis-rotation指定弧线绕x轴旋转的度数。它只在rx和ry的值不相同是有效果。large-arc-flag是大弧标志位，取值0或1，用于决定绘制大弧还是小弧。sweep-flag用于决定弧线绘制的方向 |
| a | rx,ry x-axis-rotation large-arc-flag,sweepflag x,y | 椭圆弧线 | 和大写的A指令相同，但是坐标是相对于当前画笔的坐标点 |
| Z | 无 | 闭合路径 | 从结束点绘制一条直线到开始点，闭合路径 |
| z | 无 | 闭合路径 | 从结束点绘制一条直线到开始点，闭合路径 |
| z | 无 | 闭合路径 | 同Z |

注意:所有的这些字符命令都可以用大小写两种形式。大小表示绝对位置，而小写表示相对位置。











举例，我的头像自动生成的SVG，其实很多个path,并不需要直接导入底图Ai参考着一笔画,其实svg文件path可以去掉Z直接接在一起。

这个如果你用Emacs,M-%可以批量替换，当然正则表达式会方便很多。同理，会Regex会很方便([30分钟入门](http://deerchao.net/tutorials/regex/regex.htm))，嫌麻烦还可以用Word替换技巧。

然后我编辑SVG文件，合并所有path之后写进txt,再次感谢，用工程跑出来了data.txt。

这里值得注意的是，data.txt写入Archive中data.js的时候，需要加逗号，同样M-%就行。

ren其中victor.js是github开源的一个JavaScript 2D矢量类,renderer.js控制速度等等信息，roattionSpeed变成0.00295可以开一点，太快会漏点。


接着浏览器打开网页，那就能看动图。到此，从任何一张图像变成矢量图svg，再到傅里叶的生态链条算是被开源社区前赴后继的大佬们搞妥了！









































