# make  
https://blog.csdn.net/u014543725/article/details/82622759


https://www.cnblogs.com/haoyul/p/5606720.html             MATLAB中mexFunction函数的接口规范

# mex hello

https://wenku.baidu.com/view/7e26556f27d3240c8447ef5b.html

接口规范


https://www.cnblogs.com/haoyul/p/5606720.html

www.cnblogs.com/tjulxh/archive/2012/04/23/2467087.html



https://wenku.baidu.com/view/7e26556f27d3240c8447ef5b.html  入门整理



# mex
https://blog.csdn.net/zhanshen112/article/details/79484031

有用解决问题



Error using mex
No supported compiler or SDK was found. You can
install the freely available MinGW-w64 C/C++
compiler; see Install MinGW-w64 Compiler. For
more options, visit
http://www.mathworks.com/support/compilers.

Error in runCFAR (line 8)
mex avgRegionImage.cpp
 



报错
```
Building with 'MinGW64 Compiler (C)'.
Warning: You are using an unsupported version
of MinGW Compiler. To install the supported
version of MinGW compiler, see: Install
MinGW-w64 Compiler.
 For a list of currently supported compilers
 visit
 http://www.mathworks.com/support/compilers. 
Error using mex
C:\Users\shinelon\Documents\WeChat
Files\W4401821997\FileStorage\File\2019-05\Matlab2017bÉÏÔËÐÐCFARËã·¨£¨Êý¾Ý+´úÂë+½Ì³Ì£©\yprime.c:1:0:
sorry, unimplemented: 64-bit mode not compiled
in
 /*=================================================================
/=-=- ------------------ -=-=\
|=|   COMPONENT LICENSES   |=|
\=-=- ------------------ -=-=/









  ^
```






```

>> mex -setup
MEX 配置为使用 'MinGW64 Compiler (C)' 以进行 C 语言编译。
警告: MATLAB C 和 Fortran API 已更改，现可支持
	包含 2^32-1 个以上元素的 MATLAB 变量。不久以后，
	 您需要更新代码以利用
	 新的 API。您可以在以下网址找到相关详细信息:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html。

要选择不同的语言，请从以下选项中选择一种命令:
 mex -setup C++ 
 mex -setup FORTRAN










```


```


>> mex -setup
MEX configured to use 'MinGW64 Compiler (C)' for C language compilation.
Warning: The MATLAB C and Fortran API has changed to support MATLAB
	 variables with more than 2^32-1 elements. You will be required
	 to update your code to utilize the new API.
	 You can find more information about this at:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html.

To choose a different language, select one from the following:
 mex -setup C++ 
 mex -setup FORTRAN
MEX configured to use 'MinGW64 Compiler (C++)' for C++ language compilation.
Warning: The MATLAB C and Fortran API has changed to support MATLAB
	 variables with more than 2^32-1 elements. You will be required
	 to update your code to utilize the new API.
	 You can find more information about this at:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html.

To choose a different C++ compiler, select one from the following:
MinGW64 Compiler (C++)  mex -setup:'D:\Program Files\MATLAB\R2017b\bin\win64\mexopts\mingw64_g++.xml' C++
MinGW64 Compiler with Windows 10 SDK or later (C++)  mex -setup:'D:\Program Files\MATLAB\R2017b\bin\win64\mexopts\mingw64_g++_sdk10+.xml' C++
Error using mex
No supported compiler or SDK was found. For
options, visit
https://www.mathworks.com/support/compilers.
 
MEX configured to use 'MinGW64 Compiler (C++)' for C++ language compilation.
Warning: The MATLAB C and Fortran API has changed to support MATLAB
	 variables with more than 2^32-1 elements. You will be required
	 to update your code to utilize the new API.
	 You can find more information about this at:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html.

To choose a different C++ compiler, select one from the following:
MinGW64 Compiler (C++)  mex -setup:C:\Users\shinelon\AppData\Roaming\MathWorks\MATLAB\R2017b\mex_C++_win64.xml C++
MinGW64 Compiler with Windows 10 SDK or later (C++)  mex -setup:'D:\Program Files\MATLAB\R2017b\bin\win64\mexopts\mingw64_g++_sdk10+.xml' C++
MEX configured to use 'MinGW64 Compiler (C++)' for C++ language compilation.
Warning: The MATLAB C and Fortran API has changed to support MATLAB
	 variables with more than 2^32-1 elements. You will be required
	 to update your code to utilize the new API.
	 You can find more information about this at:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html.
MEX configured to use 'MinGW64 Compiler with Windows 10 SDK or later (C++)' for C++ language compilation.
Warning: The MATLAB C and Fortran API has changed to support MATLAB
	 variables with more than 2^32-1 elements. You will be required
	 to update your code to utilize the new API.
	 You can find more information about this at:
	 http://www.mathworks.com/help/matlab/matlab_external/upgrading-mex-files-to-use-64-bit-api.html.
>> 
>
```
https://bbs.csdn.net/topics/391080514



setenv('MW_MINGW64_LOC','C:\TDM-GCC-32')位置





[Windows sdk 7.1 安装错误的解决方法](https://blog.csdn.net/u011926310/article/details/12837015 "Windows sdk 7.1 安装错误的解决方法")[错误回放一: A problem occurred while installing selected Windows SDK components. Installation of the "Microsoft Windows SDK for Windows 7 Compilers for x86" product has reported the following error:](https://blog.csdn.net/u011926310/article/details/12837015 "错误回放一:


A problem occurred while installing selected Windows SDK components.
Installation of the "Microsoft Windows SDK for Windows 7 Compilers for x86" product has reported the following error: ")

[![](https://profile.csdnimg.cn/F/4/9/1_zhao4zhong1)![](https://g.csdnimg.cn/static/user-reg-year/2x/12.png)](https://my.csdn.net/zhao4zhong1)

[赵4老师](https://my.csdn.net/zhao4zhong1 "赵4老师")

![Bbs12](https://csdnimg.cn/jifen/images/xunzhang/jianzhang/bbs12.png)

![Blank](https://csdnimg.cn/jifen/images/xunzhang/xunzhang/zhuangyuan.png) ![Blank](https://csdnimg.cn/jifen/images/xunzhang/xunzhang/banyan.png) ![Blank](https://csdnimg.cn/jifen/images/xunzhang/xunzhang/tuanhua.png) ![Blank](https://csdnimg.cn/jifen/images/xunzhang/xunzhang/jinshi.png)

不要做A语言代码修改为B语言代码的无用功。  
也不要做用A语言代码直接调用B语言代码库这样复杂、这样容易出错的傻事。  
只需让A、B语言代码的输入输出重定向到文本文件，或修改A、B语言代码让其通过文本文件输入输出。  
即可很方便地让A、B两种语言之间协调工作。  
比如：  
A将请求数据写到文件a.txt，写完后改名为aa.txt  
B发现aa.txt存在时，读取其内容，调用相应功能，将结果写到文件b.txt，写完后删除aa.txt，改名为bb.txt  
A发现bb.txt存在时，读取其内容，读完后删除bb.txt  
以上A可以替换为任何一种开发语言或开发环境，B可以替换为任何一种与A不同的开发语言或开发环境。  
除非A或B不支持判断文件是否存在、文件读写和文件更名。  
但是谁又能举出不支持判断文件是否存在、文件读写和文件更名的开发语言或开发环境呢？  
可以将临时文件放在RamDisk上提高效率减少磨损磁盘。  
数据的结构很复杂的话，文本文件的格式问题可参考json或xml  
  
共享临时文本文件这种进程之间的通讯方法相比其它方法的优点有很多，下面仅列出我现在能想到的：  
·进程之间松耦合  
·进程可在同一台机器上，也可跨机，跨操作系统，跨硬件平台，甚至跨国。  
·方便调试和监视，只需让第三方或人工查看该临时文本文件即可。  
·方便在线开关服务，只需删除或创建该临时文本文件即可。  
·方便实现分布式和负载均衡。  
·方便队列化提供服务，而且几乎不可能发生队列满的情况（除非硬盘空间满）  
·……  
  
“跨语言、跨机，跨操作系统，跨硬件平台，跨国，跨*.*的”苦海无边，  
回头是“使用共享纯文本文件进行信息交流”的岸！































































































































