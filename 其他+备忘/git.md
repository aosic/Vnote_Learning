# downgit.zhoudaxiaa.com/#/home
https://www.zhihu.com/question/21248859/answer/593173022
```
! [remote rejected] master -> master (pre-receive hook declined)

```
### 1.将所要push的内容所在的分支的protected权限关闭

(1)进入所在项目的settings

![](http://i.imgur.com/F8Lgf37.png)

(2)点击进入Protected branches,点击unprotected将master分支的权限改变，即关闭master的protected权限

![](http://i.imgur.com/aLQQpJn.png)

### 2.新建其它分支，将项目push到新建的分支上，后期再进行merge

(1)新建分支

```
git branch 分支名
```

(2)切换分支

```
git checkout 分支名
```

(3)进行项目上传

```
git add .

git commit -m "提交的信息"

git remote add origin 远程仓库地址

git push -u origin 分支名
```

















>现在有一个**test**仓库https://github.com/mygithub/test  
你要gitclone里面的**tt**子目录：  
在本地的硬盘位置打开**Git Bash**

git init test && cd test     //新建仓库并进入文件夹

git remote add -f origin <url_>例如：
git remote add origin git@github.com:mygithub/test.git  //这里换成你要克隆的项目和库

git config core.sparsecheckout true //设置允许克隆子目录

echo 'tt*' >> .git/info/sparse-checkout //设置要克隆的仓库的子目录路径   //空格别漏
>接下来你需要告诉Git哪些文件或者文件夹是你真正想Check Out的，你可以将它们作为一个列表保存在.git/info/sparse-checkout文件中。 例如：
>
>>$echo “libs” >> .git/info/sparse-checkout
>
>>$echo “apps/register.go” >> .git/info/sparse-checkout
>
>>$echo “resource/css” >> .git/info/sparse-checkout
>


最后，你只要以正常方式从你想要的分支中将你的项目拉下来就可以了：

$git pull origin master
具体您可以参考Git的Sparse checkout文档： http://schacon.github.io/git/git-read-tree.html#_sparse_checkout


--------------------- 
作者：周大侠啊 
来源：CSDN 
原文：https://blog.csdn.net/qq_36560161/article/details/78260532 
版权声明：本文为博主原创文章，转载请附上博文链接！


echo '密码学与网络安全' >> .git/info/sparse-checkout
echo '信息安全原理' >> .git/info/sparse-checkout
echo '图像信息处理' >> .git/info/sparse-checkout
echo '常微分方程' >> .git/info/sparse-checkout
echo '操作系统原理' >> .git/info/sparse-checkout
echo '操作系统原理实验' >> .git/info/sparse-checkout
echo '数值分析' >> .git/info/sparse-checkout
echo '毕业设计' >> .git/info/sparse-checkout
echo '概率论与数理统计' >> .git/info/sparse-checkout
echo '汇编与接口' >> .git/info/sparse-checkout
echo 'README.md' >> .git/info/sparse-checkout
echo '数据结构基础' >> .git/info/sparse-checkout
echo '机器人学/实验' >> .git/info/sparse-checkout
echo '汇编语言程序设计基础' >> .git/info/sparse-checkout
echo '离散数学及其应用' >> .git/info/sparse-checkout
echo '程序设计基础' >> .git/info/sparse-checkout
echo '程序设计方法学' >> .git/info/sparse-checkout
echo '编译原理' >> .git/info/sparse-checkout
echo '编译系统设计/作业' >> .git/info/sparse-checkout
echo '计算机体系结构' >> .git/info/sparse-checkout
echo '计算机系统概论' >> .git/info/sparse-checkout
echo '计算机组成' >> .git/info/sparse-checkout
echo '计算机网络基础' >> .git/info/sparse-checkout
echo '计算机视觉' >> .git/info/sparse-checkout
echo '计算理论' >> .git/info/sparse-checkout
echo '量子力学' >> .git/info/sparse-checkout
echo '资产定价' >> .git/info/sparse-checkout
echo '软件工程' >> .git/info/sparse-checkout
echo '逻辑与计算机设计基础' >> .git/info/sparse-checkout
echo '面向对象程序设计' >> .git/info/sparse-checkout
echo '面向信息技术的沟通技巧' >> .git/info/sparse-checkout
echo '高级数据结构和算法分析' >> .git/info/sparse-checkout
echo 'Java应用技术' >> .git/info/sparse-checkout
echo '' >> .git/info/sparse-checkout







































