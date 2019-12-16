# git_clone

要克隆的仓库太大，文件多，导致`git clone`失败。

解决：

-   方法1：增加git缓冲区大小

```
git config --global http.postBuffer 524288000
git config --list
```

-   方法2：浅层克隆，深度设置为1

在git clone时加上--depth=1即可解决，

**depth用于指定克隆深度，为1即表示只克隆最近一次commit.**



```
git clone http://github.com/target.git --depth 1  # target.git 为目标地址
cd target
git fetch --unshallow
```



远端的git仓库大导致clone总是失败

网上搜索方法如下：

$ git clone --depth 1 [https://github.com/dogescript...](https://github.com/dogescript/dogescript.git)  
$ git remote set-branches origin 'remote\_branch\_name'  
$ git fetch --depth 1 origin remote\_branch\_name  
$ git checkout remote\_branch\_name

stackoverflow上的一个答案， 个人问题可以解决  
[https://stackoverflow.com/que...](https://stackoverflow.com/questions/23708231/git-shallow-clone-clone-depth-misses-remote-branches)



[https://blog.csdn.net/github_37847975/article/details/86477343](https://blog.csdn.net/github_37847975/article/details/86477343)

##  git报错--RPC failed; curl 18 transfer closed with outstanding read data remaining

**这个错误是因为项目太久，tag资源文件太大**

https://blog.csdn.net/it_liuchengli/article/details/77040806


## git clone 子文件夹

[https://segmentfault.com/q/1010000006666948](https://segmentfault.com/q/1010000006666948)


[https://blog.csdn.net/qq_36560161/article/details/78260532](https://blog.csdn.net/qq_36560161/article/details/78260532)



[DownGIT ！https://blog.csdn.net/u012104219/article/details/79057489](https://blog.csdn.net/u012104219/article/details/79057489)





















