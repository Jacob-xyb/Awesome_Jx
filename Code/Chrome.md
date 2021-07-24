# 有关iCloud

## 同步

因为习惯了多系统操作，`QQ Browser` 现在是不支持macOS了，因此我一直用的是 `Chrome` 进行书签同步，但是馋MacBook上的 `Safari` 联动太好，因此再将 `Safari` 与 `Chrome` 进行同步，其实很简单：

1. 因为自己也会使用到 `iCloud` ，下载一个 `iCloud Windows` 即可（[地址](https://support.apple.com/zh-cn/HT204283)）；
2. 然后在Chrome插件商店下载安装 `iCloud 书签` 和 `iCloud 密码`；

## 重置系统后同步失败

昨天把系统重装了以后发现了一些问题，`Chrome` 无法识别我已经安装好的 `iCloud`，为此我尝试了一晚上都没能解决，第二天大早发现书签同步上了，解决的方式就是，重启电脑！`iCloud 密码` 同理。

## iCloud Drive 缓存文件夹位置

如果不作任何调整，`iCloud`会将缓存文件建立在 `C:\Users\XXXX\iCloudDrive`下，也就是你的用户的根目录，占据你C盘的空间。

这个目录是可以更改的，需要的操作是 `符号链接` ，类似于快捷方式，但绝不是快捷方式，不要自作聪明，也不要问我为什么(因为我帮你们排完了所有的雷)。

关键步骤：

- 首先需要注销你的 `iCloud 账户` 不然是无论如何也无法成功的；

- 例如我想缓存在 `E:\iCloudDrive` 目录下，那就必须要保证此目录下是空的；如果不是空的，`iCloud` 会又在用户根目录创建一个 `iCloud Drive` ；

- 用管理员打开cmd：

  操作：`windows键 -- 输入cmd -- 右键管理员打开`， 输入一下指令：`MKLINK /D C:\Users\XXXX\iCloudDrive E:\iCloudDrive`

  排雷：`Windows PowerShell` 没有此命令，所以一定要是cmd；

- 登陆iCloud账户即可。



