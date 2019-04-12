其实这只是[windows](https://www.baidu.com/s?wd=windows&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)的一个目录，这里关系着系统的更新问题，如下级目录的download是下载补丁。由于[WINDOWS](https://www.baidu.com/s?wd=WINDOWS&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)在[WINDOWS](https://www.baidu.com/s?wd=WINDOWS&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)pUPDATE时会在硬盘上建立相应记录文件夹，该文件夹就是C：/Windows/SoftwareDistribution，并把相应升级信息写入注册表，假如升级出现错误，注册表也相应记录错误信息。并在每次WINDOWSpDATE中去自动访问SoftwareDistribution目录，以至于出现依次升级错误就会造成以后屡次出现错误，而造成升级次次失败。SoftwareDistribution由于在正常模式下系统会自动调用，所以正常模式下无法改名或删除。进入安全模式修改后，再次WINDOWSpUPDATE，系统找不到该文件夹，会自动重建该目录，并重新扫描系统升级信息，以至可以成功升级  
  
说到这，再说一件事，就是系统更新错误（0x8024001d），其实是系统系列号没有验证对，微软不给更新，换一个序列号，到[http://www.microsoft.com/resources/howtotell/zh-chs/windows/default.mspx](http://www.microsoft.com/resources/howtotell/zh-chs/windows/default.mspx)验证，如果对了，打开服务（本地）或直接运行[services.msc](https://www.baidu.com/s?wd=services.msc&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)，把automatic update的服务给停止了，把SoftwareDistribution的目录下的东西全删了，然后，启动服务，更新。其实也可以在自动更新里改，但得重启，相信不会用这种办法。  
  
如果你的系统最近更新过那最好不要删除.因为这写是你系统升级的一写文件.  
  
C盘空间不够可以考虑一下几个地方清理  
1.打开“我的电脑”-“工具”-“[文件夹选项](https://www.baidu.com/s?wd=%E6%96%87%E4%BB%B6%E5%A4%B9%E9%80%89%E9%A1%B9&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)”-“查看”-在“显示所有文件和文件夹”选项前打勾-“确定”  
  
2.删除以下文件夹中的内容：  
  
x:\\Documents and Settings\\用户名\\Cookies\\下的所有文件(保留index文件)  
  
x:\\Documents and Settings\\用户名\\Local Settings\\Temp\\下的所有文件(用户临时文件)  
  
x:\\Documents and Settings\\用户名\\LocalSettings\\TemporaryInternet Files\\下的所有文件(页面文件)  
  
x:\\Documents and Settings\\用户名\\Local Settings\\History\\下的所有文件(历史纪录)  
  
x:\\Documents and Settings\\用户名\\Recent\\下的所有文件(最近浏览文件的快捷方式)  
  
x:\\WINDOWS\\Temp\\下的所有文件(临时文件)  
  
x:\\WINDOWS\\ServicePackFiles(升级sp1或sp2后的备份文件)  
  
x:\\WINDOWS\\Driver Cache\\i386下的压缩文件(驱动程序的备份文件)  
  
x:\\WINDOWS\\SoftwareDistribution\\download下的所有文件  
  
3.如果对系统进行过windoes updade升级，则删除以下文件：  
  
x:\\windows\\下以 $u... 开头的隐藏文件  
  
4.然后对磁盘进行碎片整理，整理过程中请退出一切正在运行的程序  
  
5.碎片整理后打开“开始”-“程序”-“附件”-“系统工具”-“系统还原”-“创建一个还原点”(最好以当时的日期作为还原点的名字)  
  
6.打开“我的电脑”-右键点系统盘-“属性”-“磁盘清理”-“其他选项”-单击系统还原一栏里的“清理”-选择“是”-ok了  
  
7、在各种软硬件安装妥当之后，其实XP需要更新文件的时候就很少了。删除系统备份文件吧：开始→运行→sfc.exe /purgecache近3xxM。(该命令的作用是立即清除"Windows [文件保护](https://www.baidu.com/s?wd=%E6%96%87%E4%BB%B6%E4%BF%9D%E6%8A%A4&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)"文件高速缓存，释放出其所占据的空间)  
  
8、删掉\\windows\[system32](https://www.baidu.com/s?wd=system32&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)\\dllcache下dll档(减去200——300mb),这是备用的dll档， 只要你已拷贝了安装文件，完全可以这样做。  
  
9、XP会自动备份硬件的驱动程序，但在硬件的驱动安装正确后，一般变动硬件的可能性不大，所以也可以考虑将这个备份删除，文件位于\\windows\\driver cache\\i386目录下，名称为driver.cab，你直接将它删除就可以了，通常这个文件是74M。  
  
10、删除不用的输入法：对很多网友来说，Windows XPt系统自带的输入法并不全部都合适自己的使用，比如IMJP8_1 [日文输入法](https://www.baidu.com/s?wd=%E6%97%A5%E6%96%87%E8%BE%93%E5%85%A5%E6%B3%95&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、IMKR6_1 [韩文输入法](https://www.baidu.com/s?wd=%E9%9F%A9%E6%96%87%E8%BE%93%E5%85%A5%E6%B3%95&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)这些输入法，如果用不着，我们可以将其删除。输入法位于\\windows\\ime\\文件夹中，全部占用了88M的空间。  
  
11、升级完成发现windows\\多了许多类似$NtUninstallQ311889$这些目录，都干掉吧，1x-3xM  
  
12、另外，保留着\\windows\\help目录下的东西对我来说是一种伤害，呵呵。。。都干掉！  
  
13、关闭系统还原：系统还原功能使用的时间一长，就会占用大量的硬盘空间。因此有必要对其进行手工设置，以减少硬盘占用量。打开"系统属性"对话框，选择"系统还原"选项，选择"在所有驱动器上关闭系统还原"复选框以关闭系统还原。也可仅对系统所在的磁盘或分区设置还原。先选择系统所在的分区，单击"配置"按钮，在弹出的对话框中取消"关闭这个驱动器的系统还原"选项，并可设置用于系统还原的磁盘空间大小。  
  
14、休眠功能会占用不少的硬盘空间，如果使用得少不妨将共关闭，关闭的方法是的：打开"控制面板"，双击"电源选项"，在弹出的"电源选项属性"对话框中选择"休眠"选项卡，取消"启用休眠"复选框。  
  
15、卸载不常用组件：XP默认给[操作系统](https://www.baidu.com/s?wd=%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)安装了一些系统组件，而这些组件有很大一部分是你根本不可能用到的，可以在"添加/删除Windows组件"中将它们卸载。但其中有一些组件XP默认是隐藏的，在"添加/删除Windows 组件"中找不到它们，这时可以这样操作：用记事本打开\\windows\\inf\\sysoc.inf这个文件，用查找/替换功能把文件中的"hide"字符全部替换为空。这样，就把所有组件的隐藏属性都去掉了，存盘退出后再运行"添加-删除程序"，就会看见多出不少你原来看不见的选项，把其中那些你用不到的组件删掉（记住存盘的时候要保存为sysoc.inf，而不是默认的sysoc.txt），如Internat信使服务、传真服务、Windows messenger，码表等，大约可腾出近50MB的空间。  
  
16、清除系统临时文件：系统的临时文件一般存放在两个位置中：一个Windows安装目录下的Temp文件夹；另一个是x:\\Documents and Settings"用户名"\\Local Settings\\Temp文件夹(Y:是系统所在的分区)。这两个位置的文件均可以直接删除。  
  
17、清除Internet临时文件：定期删除上网时产生的大量Internet临时文件，将节省大量的硬盘空间。打开[IE浏览器](https://www.baidu.com/s?wd=IE%E6%B5%8F%E8%A7%88%E5%99%A8&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)，从"工具"菜单中选择"Internet选项"，在弹出的对话框中选择"常规"选项卡，在"Internet临时文件"栏中单击"删除文件"按钮，并在弹出"删除文件"对话框，选中"删除所有脱机内容"复选框，单击"确定"按钮。  
  
18、清除预读文件：Windows XP的预读设置虽然可以提高系统速度，但是使用一段时间后，预读文件夹里的文件数量会变得相当庞大，导致系统搜索花费的时间变长。而且有些应用程序会产生死链接文件，更加重了系统搜索的负担。所以，应该定期删除这些预读文件。预计文件存放在Windows [XP系统](https://www.baidu.com/s?wd=XP%E7%B3%BB%E7%BB%9F&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)文件夹的Prefetch文件夹中，该文件夹下的所有文件均可删除。  
  
19、压缩NTFS驱动器、文件或文件夹：如果你的硬盘采用的是NTFS文件系统，空间实在紧张，还可以考虑启用NTFS的压缩功能。右击要压缩的驱动器－"属性"－"常规"－"压缩磁盘以节省磁盘空间"，然后单击"确定"， 在"确认属性更改"中选择需要的选项。这样可以节省约20% 的硬盘空间。在压缩C盘的时候，最好在安全模式下压缩，这样效果要好一些。  
  
20、关闭华医生Dr.Watson：要关闭Dr.Watson可打开注册表编辑器，找到"HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\WindowsNT\\CurrentVersion\\AeDebug"分支，双击其下的Auto键值名称，将其"数值数据"改为0，最后按F5刷新使设置生效，这样就取消它的运行了。也在"开始"->"运行"中输入"drwtsn32"命令，或者"开始"->"程序"->"附件"->"系统工具"->"系统信息"->"工具"->"Dr Watson"，调出系统里的华医生Dr.Watson ，只保留"转储全部线程上下文"选项，否则一旦程序出错，硬盘会读很久，并占用大量空间。如以前有此情况，请查找user.dmp文件，删除后可节省几十MB空间。  
  
21、关闭远程桌面："我的电脑"->"属性"->"远程"，"远程桌面"里的"允许用户远程连接到这台计算机"勾去掉。  
  
22、取消XP对ZIP支持：Windows XP在默认情况下打开了对zip文件支持，这要占用一定的系统资源，可选择"开始→运行"，在"运行"对话框中键入"regsvr32 /u zipfldr.dll"，回车确认即可取消XP对ZIP解压缩的支持，从而节省系统资源。  
  
23、关闭错误报告：当应用程序出错时，会弹出发送错误报告的窗口，其实这样的错误报告对普通用户而言几乎没有任何意义，关闭它是明智的选择。在"系统属性"对话框中选择"高级"选项卡，单击"错误报告"按钮，在弹出的"错误汇报"对话框中，选择"禁用错误汇报"单选项，最后单击"确定"即可。另外我们也可以从组策略中关闭错误报告：从"运行"中键入"gpedit.msc"，运行"组策略编辑器"，展开"计算机配置→管理模板→系统→错误报告功能"，双击右边设置栏中的"报告错误"，在弹出的"属性"对话框中选择"已禁用"单选框即可将"报告错误"禁用。  
  
24、关掉不用的设备：Windows XP总是尽可能为电脑的所有设备安装驱动程序并进行管理，这不仅会减慢系统启动的速度，同时也造成了系统资源的大量占用。针对这一情况，你可在 设备管理器中，将PCMCIA卡、调制解调器、红外线设备、打印机端口(LPT1)或者串口(COM1)等不常用的设备停用，方法是双击要停用的设备，在其属性对话框中 的"常规"选项卡中选择"不要使用这个设备(停用)"。在重新启动设置即可生效，当需要使用这些设备时再从设备管理器中启用它们。  
  
25、定期清理系统还原点：打开磁盘清理，选择其他选项－>清理系统还原点，点击清理。  
  
26、卸载不需要的程序，这个就不用我多说了  
  
27、其它优化：  
  
a 将应用软件装在其它硬盘（不要安装在系统盘下，这对重装系统也有好处）;  
b 将"我的文档"文件夹都转到其他分区：在桌面的"我的文档"图标上是右击鼠标，选择"属性"->"移动" ；  
c 将IE临时文件夹都转到其他分区：打开IE浏览器，选择"工具"->"internet选项"->"常规"->"设置"->"移动文件夹"；  
d 把虚拟内存也转到其它硬盘；  
e 把pagefile.sys文件都指向一个地方：控制面板→系统→性能—高级→虚拟内存→更改，注意要点"设置"才会生效；  
f 在桌面的"我的电脑"图标上是右击鼠标，选择"属性"->"高级－性能设置"－>"高级－虚拟内存"，调至330－720。而且定时清理。