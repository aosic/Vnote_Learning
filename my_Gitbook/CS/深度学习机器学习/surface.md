# surface










很多朋友的笔记本和平板电脑都是品牌机，其 BIOS 中内置了 Windows 产品密钥，导致无法自己重装系统，在此，我将我的方法告诉大家，希望能够给大家一点帮助，如果有问题可以加 Microsoft Surface Pro 平板电脑讨论群（群号：禁止发布非官方群，再有下次，禁防！）。

从 U 盘或刻录 DVD 全新安装 Windows 7 或者 Windows 8 Pro 系统：
只需在系统安装根目录下的 resource  目录下新建一个 ei.cfg 文件，打开后输入以下内容保存，然后再引导安装系统即可：
[EditionID]
Professional
[Channel]
Retail
[VL]
0

Surface 使用外部驱动器引导的方法：
设置>更改电脑设置>常规>高级启动>立即启动>使用设备（使用 U 盘、网络连接或 windows 恢复 DVD）>UEFI：设备名称，选中重启，就可以从外部驱动器引导安装系统了。 [此种方式不需要将 BIOS 中的 Secure Boot（安全启动）]

Surface 进入 BIOS 开启 Secure Boot（安全启动）的方法：
按音量减号键，再按电源键，当 Surface 文字在屏幕上出现时松开电源键，然后大约 5 秒后松开音量减号键。

注意事项：
引导系统只能是 64位系统，32位系统盘可能无法引导。













