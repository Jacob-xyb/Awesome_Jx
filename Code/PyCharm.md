# 相关博客

[PyCharm选择性忽略PEP8代码风格警告信息](https://blog.csdn.net/zgljl2012/article/details/51907663)

[**右键显示  Edit with idle**](https://jingyan.baidu.com/article/c1a3101e13087ade656deb83.html)

[快捷键](https://github.com/Jacob-xyb/Anything_is_Hotkey/blob/master/%E5%A4%A7%E5%9E%8B%E8%BD%AF%E4%BB%B6/PyCharm.md)

# 手动同步设置

## 实时模板

**jx_logo**

```python
"""
__author__ = "Jacob-xyb"
__web__ = "https://github.com/Jacob-xyb"
__time__ = "$data$ $time$"
"""

# 变量
data = date()	True
time = time()	True
```

**jx_split_annotation**

```python
# == $Annotation$
$End$
# ========
```

# 设置

## 控制台变量

运行 -> 编辑配置 -> 控制台运行

## 取消 pytest 模式

问题：在Pycharm中右键运行python程序时出现Run 'pytest in XXX.py'

解决办法：

进入到File->Settings->Tools->Python integrated Tools页面

找到Testing下的Default test runner

把Pytest设置为Unittests就可以了

![img](https://upload-images.jianshu.io/upload_images/12840157-ecc974f5fefc1f35.png?imageMogr2/auto-orient/strip|imageView2/2/w/1023/format/webp)

# 插件

## 插件下载

进入**File -> Settings -> Plugins**，根据需要搜索插件名称（记得是在Marketplace中搜索），然后点击Install按钮，需要重启才能生效。

![img](https://i.loli.net/2021/10/27/Hlf5TVxPhNaR4Kz.jpg)

## IdeaVim

linux中的vim大家该听过吧，而 IdeaVim 就可以让你在 Pycharm 中操作 Vim 的功能。

在tools中勾选Vim Emulator即可使用，取消勾选回到正常编辑状态。

![img](https://pic3.zhimg.com/80/v2-bfaef098d69fa4e6094063e06bdbf3ba_720w.jpg)

## **Rainbow Brackets**

Rainbow Brackets可以让代码块之间清晰的显示出各种颜色，比如括号相同颜色，选中区域代码高亮的功能等，并且支持支持Java, Python, JavaScript,Go, PHP等多种编程语言。

![img](https://pic1.zhimg.com/80/v2-f3de49ec40831ead402e2f4e6b24f45c_720w.jpg)

## Chinese

中文插件还是香的，该快捷键比较能看得懂。

## Material Theme UI

可以换主题

![image-20211027094119389](https://i.loli.net/2021/10/27/tWJPv7haL3GpdDE.png)

## Atom Material Icons

官方图标插件，你不安装吗

## CSV

将csv数据对齐，且分颜色高亮

![image-20211027101656027](https://i.loli.net/2021/10/27/1fgtcUJNMrTsX37.png)

## CodeGlance

将类似于Sublime中的代码小地图嵌入到编辑器窗格中。使用自定义颜色进行语法高亮，同时使用明暗主题。

![img](https://img-blog.csdnimg.cn/20200729170139198.png)

# 破解教程

[PyCharm2020.1破解教程（已验证）](https://www.cnblogs.com/mingyue5826/p/12913008.html)

[PyCharm2018.3.4破解教程 for mac（未验证）](https://www.cnblogs.com/clnZ/p/13131350.html)

[2022激活教程](https://www.hicxy.com/9907.html)

[激活码获取地址2022(激活码只能激活一个月)](http://idea.hicxy.com/)

## 插件激活路径

配置插件的路径，与插件的位置要一致，保存后，重启IDE
这里主要是看ja-netfilter.jar的存放位置
Windows：
-javaagent:D:\Program Files\pycharm2021.3.3\plugins\ja-netfilter\ja-netfilter.jar

Mac:
-javaagent:/Users/自定义文件名称/ja-netfilter.jar

Linux:
-javaagent:/home/自定义文件名称/ja-netfilter.jar

- 如果配置错误
  pycharm64.exe.vmoptions文件在这里打开
  C:\Users\【系统用户名】\AppData\Roaming\JetBrains\pycharm2021.3\pycharm64.exe.vmoptions。
  注意了：AppData是隐藏文件来的。
  注意了：AppData是隐藏文件来的。

## 2022激活教程

- 激活补丁

链接：https://pan.baidu.com/s/1_ESL3u351gsx-IR_DznLBw 
提取码：bznb

- 适用版本

  2018-2022

这种激活方式，是通过官方的屏蔽官网的网络校验来达成的永久激活PyCharm目的。（但是并不影响任何使用）

### 步骤

1. 下载上面链接的激活补丁

下载之后解压，目录如下 (ja-netfilter.jar 为核心文件)
建议解压到一个稳定的目录，确保后期不会被删除！（注意是整个文件夹是一个整体）

![file](https://i0.hdslb.com/bfs/article/e332124fac2d30864f983f93e9fe8287260289a3.png@942w_209h_progressive.webp)

2. 登录PyCharm

这个时候选择注册一个账号，可以免费试用30天的PyCharm（如果有小伙伴账号已经过期了，不用慌，往下看）

3. 试用

这个时候回到PyCharm界面，点击 Start Trial，开始使用即可，上面的两个选项不用勾选

![file](https://i0.hdslb.com/bfs/article/35de01d0c1c48d7dd7e6215c171b1081c9f9abc5.png@942w_567h_progressive.webp)

4. 配置

这个时候随便创建一个PyCharm项目，先进入到PyCharm里面。
进来之后在菜单栏中点击`Help - > Edit Custom VM Options...`

![file](https://i0.hdslb.com/bfs/article/ea86a5953a1416a2c7ee1a8ce0996d8fd284c310.png@942w_626h_progressive.webp)

在 `pycharm64.exe.vmoptions`文件中配置上`ja-netfilter.jar`路径
语法为

`-javaagent:[ja-netfilter.jar路径]`

那我配置的内容是

```python
-javaagent:E:\\ja-netfilter\\ja-netfilter.jar
```

![file](https://i0.hdslb.com/bfs/article/396a0d2e777adb991fa7e96b174f33422212d5d4.png@942w_293h_progressive.webp)

5. 重启即可

Register 检查一下激活日期即可

![file](https://i0.hdslb.com/bfs/article/12f4d5cb6437b931a47cb848c106a90ff3000722.png@942w_636h_progressive.webp)

![file](https://i0.hdslb.com/bfs/article/7c949db25c64fe39d3163e57ed7c6b96f3a42109.png@942w_420h_progressive.webp)

6. 补充

如果已经过了使用期限，需要分情况讨论。优先在C盘寻找`pycharm.vmoptions` 这样的配置文件，每个系统下的各版本的名字会有所差异

```python
C:\Users\Administrator\AppData\Roaming\JetBrains\PyCharm2021.3
```

![file](https://i0.hdslb.com/bfs/article/1f96a5ba0acd5af773f65f4d6f104130ac34fe2c.png@942w_429h_progressive.webp)

没找到就在安装目录的bin文件中去找（记住！优先C盘查找）

![file](https://i0.hdslb.com/bfs/article/7b2a829bb42697149cef3f6dc9b05740876b5c27.png@942w_552h_progressive.webp)

依然是在末尾添加补丁的路径

```python
-javaagent:E:\\ja-netfilter\\ja-netfilter.jar
```

