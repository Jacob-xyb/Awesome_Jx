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

### Jacob推荐设置

1. **Darker**主题

	![image-20220605140308529](https://s2.loli.net/2022/06/05/OqMY23tU1gypdRa.png)
	
2. 设置风格

  ![image-20220605140511724](https://s2.loli.net/2022/06/05/wB69faGU3L8jZzo.png)

  ```python
  # 标签页
  {
      标签页高度： 22
      活动页标签高亮色： E91E36
  }
  # 紧凑
  {
      除紧凑下拉菜单和紧凑菜单外全选：高度：18
  }
  # 项目视图： 自定义列表项高度 22
  # 组件： 反转代码补全选中色
  # 功能： 使用编辑器默认字体
  ```

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

## 无限重置试用期

- [👉 **无限重置 Pycharm 30天试用期（补丁）**](http://www.itmind.net/11397.html)；
  **PS: 此方法仅适用于 Pycharm 2021.2.2 (包含 2021.2.2 版本) 以下版本，可下载 Pycharm 历史版本来使用。**

  历史版本下载链接：https://www.jetbrains.com/pycharm/download/other.html

## 2021激活教程

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

## 2022激活教程

![](https://img.chajianxw.com/chajian/164991158927667)

- **本教程适用于 Pycharm 2022.1 以下所有版本，请放心食用~**
- **本教程适用于 JetBrains 全系列产品，包括 Pycharm、IDEA、WebStorm、Phpstorm、Datagrip、RubyMine、CLion、AppCode 等。**
- **本教程适用 Windows/Mac/Linux 系统，文中以 Windows 系统为例做讲解，其他系统按照教程顺序即可。**

最新版补丁获取地址: https://3.jetbra.in/

1. 下载补丁

   链接：https://pan.baidu.com/s/15_8E2EVH3ZWFLJ1vAAl1Dg 
   提取码：bznb

   ![](https://img.chajianxw.com/chajian/164404017671073)

   可以看到，相比较激活补丁之前的版本，新版本补丁z大新加了两个文件夹：

   - scripts: 放置了相关脚本，包含自动安装、卸载破解补丁脚本（Windows、Mac、Linux 对应系统的脚本都有）；
     之前的 Pycharm 版本，我们都是手动在 pycharm.vmoptions 配置文件引入破解补丁，但是有部分小伙伴反映找不到 pycharm.vmoptions 文件，这次，通过运行脚本可以直接引入补丁，针对小白，方便了很多。
   - vmoptions： 放置了 JetBrains 产品的 pycharm.vmoptions 配置文件。之前版本都是通过在这个文件中手动引入破解补丁，但是最新版本 Pycharm 2022.1 官方加入了反制手段，在用户目录下已经找不到这个文件了，新版本我们直接引用这个文件夹下的 pycharm.vmoptions 配置文件；

2. 运行激活脚本

   将 ja-netfilter-all激活文件夹移动到电脑上某个位置，笔者这里放置在 D 盘根目录下：

   ![](https://img.chajianxw.com/chajian/164412033477656)

   Windows 系统，点击运行 install-current-user.vbs 脚本，为当前用户安装破解补丁。

   Mac/Linux 系统，点击运行 install.sh 脚本安装。
   PS: install-all-users.vbs 为系统所有用户安装，不太推荐。unistall-*前缀的是卸载补丁脚本。
   点击安装，会弹出如下提示：

   ![](https://img.chajianxw.com/chajian/164412225024259)

   告诉我们，运行此补丁大约花费几秒钟，点击 确定，等待 Done 完成提示框出现，到这里，表示补丁安装成功。

   ![](https://img.chajianxw.com/chajian/164412243670186)

   注意：运行此脚本因为需要添加 pycharm.vmoptions 文件的环境变量，可能会被杀毒软件误报为木马，大家允许运行即可。

   实在不放心的小伙伴也可打开该脚本，看看源码.  

   代码主要是为 JetBrains 系列产品在外置 .vmoptions 配置文件中引用破解补丁：

   ![](https://img.chajianxw.com/chajian/164612530383324)

   以及添加Pycharm.vmoptions 文件的环境变量，脚本运行成功后，打开环境变量看下，如下：

   ![](https://img.chajianxw.com/chajian/164612547735063)

   可以看到，除了为 Pycharm 添加 .vmoptions 环境变量外，还有其他产品的，如 IDEA 等。

   所以，小伙伴们不用担心是木马啥的，安心运行等待安装成功就行。

3. 打开 Pycharm, 填入指定激活码完成激活

   运行脚本安装破解补丁完成后，**一定要重启 Pycharm**，然后，填入下面的激活码，点击激活即可。

   ```python
   LI6NHIQPEY-eyJsaWNlbnNlSWQiOiJMSTZOSElRUEVZIiwibGljZW5zZWVOYW1lIjoiY2F0IG1ldGhvZCIsImFzc2lnbmVlTmFtZSI6IiIsImFzc2lnbmVlRW1haWwiOiIiLCJsaWNlbnNlUmVzdHJpY3Rpb24iOiIiLCJjaGVja0NvbmN1cnJlbnRVc2UiOmZhbHNlLCJwcm9kdWN0cyI6W3siY29kZSI6IlBXUyIsImZhbGxiYWNrRGF0ZSI6IjIwMjMtMDYtMDEiLCJwYWlkVXBUbyI6IjIwMjMtMDYtMDEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUEMiLCJmYWxsYmFja0RhdGUiOiIyMDIzLTA2LTAxIiwicGFpZFVwVG8iOiIyMDIzLTA2LTAxIiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJQU0kiLCJmYWxsYmFja0RhdGUiOiIyMDIzLTA2LTAxIiwicGFpZFVwVG8iOiIyMDIzLTA2LTAxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBQQyIsImZhbGxiYWNrRGF0ZSI6IjIwMjMtMDYtMDEiLCJwYWlkVXBUbyI6IjIwMjMtMDYtMDEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUENXTVAiLCJmYWxsYmFja0RhdGUiOiIyMDIzLTA2LTAxIiwicGFpZFVwVG8iOiIyMDIzLTA2LTAxIiwiZXh0ZW5kZWQiOnRydWV9XSwibWV0YWRhdGEiOiIwMTIwMjIwNjAxUFNBTjAwMDAwNSIsImhhc2giOiJUUklBTDotOTAzMzA4Mjg0IiwiZ3JhY2VQZXJpb2REYXlzIjo3LCJhdXRvUHJvbG9uZ2F0ZWQiOmZhbHNlLCJpc0F1dG9Qcm9sb25nYXRlZCI6ZmFsc2V9-KQpLf82QBZFqJ2idWt8Jdhfc22XRMene8p4H+xOM8QPX2DJBN9uGjtZGhI8kIW5ZSCzBB63tsNryDYbauM7YxxBzLRY51ft8ePgHaNyqQdkMfEypCKTiQ9RMmB08Yw5ODkPYANUw+9QKmYzYv24Fr24TsCHPJtdQN2+bHMYGWDnerchOLuOkRLzEeJ3a2hU6Ds9UqXMLZl8UdX47ssZfB+7Ox/Hr9cqWmBsk6yMlqaZtNJ58dnnRCSmX+NRH6xM0DfDKTfdfWmVTk8baMcmL5nsRqSW7f64tohXi7pqfPMxeh2XsSsDQv3FJ6CnLvWY1p/J5kYmaesphWuTMZvcdFg==-MIIETDCCAjSgAwIBAgIBDTANBgkqhkiG9w0BAQsFADAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBMB4XDTIwMTAxOTA5MDU1M1oXDTIyMTAyMTA5MDU1M1owHzEdMBsGA1UEAwwUcHJvZDJ5LWZyb20tMjAyMDEwMTkwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCUlaUFc1wf+CfY9wzFWEL2euKQ5nswqb57V8QZG7d7RoR6rwYUIXseTOAFq210oMEe++LCjzKDuqwDfsyhgDNTgZBPAaC4vUU2oy+XR+Fq8nBixWIsH668HeOnRK6RRhsr0rJzRB95aZ3EAPzBuQ2qPaNGm17pAX0Rd6MPRgjp75IWwI9eA6aMEdPQEVN7uyOtM5zSsjoj79Lbu1fjShOnQZuJcsV8tqnayeFkNzv2LTOlofU/Tbx502Ro073gGjoeRzNvrynAP03pL486P3KCAyiNPhDs2z8/COMrxRlZW5mfzo0xsK0dQGNH3UoG/9RVwHG4eS8LFpMTR9oetHZBAgMBAAGjgZkwgZYwCQYDVR0TBAIwADAdBgNVHQ4EFgQUJNoRIpb1hUHAk0foMSNM9MCEAv8wSAYDVR0jBEEwP4AUo562SGdCEjZBvW3gubSgUouX8bOhHKQaMBgxFjAUBgNVBAMMDUpldFByb2ZpbGUgQ0GCCQDSbLGDsoN54TATBgNVHSUEDDAKBggrBgEFBQcDATALBgNVHQ8EBAMCBaAwDQYJKoZIhvcNAQELBQADggIBAB2J1ysRudbkqmkUFK8xqhiZaYPd30TlmCmSAaGJ0eBpvkVeqA2jGYhAQRqFiAlFC63JKvWvRZO1iRuWCEfUMkdqQ9VQPXziE/BlsOIgrL6RlJfuFcEZ8TK3syIfIGQZNCxYhLLUuet2HE6LJYPQ5c0jH4kDooRpcVZ4rBxNwddpctUO2te9UU5/FjhioZQsPvd92qOTsV+8Cyl2fvNhNKD1Uu9ff5AkVIQn4JU23ozdB/R5oUlebwaTE6WZNBs+TA/qPj+5/we9NH71WRB0hqUoLI2AKKyiPw++FtN4Su1vsdDlrAzDj9ILjpjJKA1ImuVcG329/WTYIKysZ1CWK3zATg9BeCUPAV1pQy8ToXOq+RSYen6winZ2OO93eyHv2Iw5kbn1dqfBw1BuTE29V2FJKicJSu8iEOpfoafwJISXmz1wnnWL3V/0NxTulfWsXugOoLfv0ZIBP1xH9kmf22jjQ2JiHhQZP7ZDsreRrOeIQ/c4yR8IQvMLfC0WKQqrHu5ZzXTH4NO3CwGWSlTY74kE91zXB5mwWAx1jig+UXYc2w4RkVhy0//lOmVya/PEepuuTTI4+UJwC7qbVlh5zfhj8oTNUXgN0AOc+Q0/WFPl1aw5VV/VrO8FCoB15lFVlpKaQ1Yh+DVU8ke+rt9Th0BCHXe0uZOEmH0nOnH/0onD
   ```

   ![](https://img.chajianxw.com/chajian/164612565030059)

   PS: 有部分小伙伴反应，重启 Pycharm 填入激活码依然无法激活，重启系统才行，如果有小伙伴遇到这种情况，不妨试试看~

###  Q&A 

 一切按照教程来的，还是提示 Key is invalid？

- 1、执行脚本提示 Done, 检查配置环境变量的值：**路径中是否包含中文**, 包含中文是不行的，换成英文路径；
- 2、笔者亲测的版本 2022.1、2021.3.3、2021.3.2 都是可以的，确认你的版本号是否是最新的这两个版本，太老的版本请用第一种方法；
- 3、有些小伙伴是重启系统后，才行的，这种法子也可以尝试一下；
- 4、检查破解补丁的位置是否动了，切记不要动，不然重启 IDE 又找不到补丁位置了，自然就失败了；

### 激活成功后，不要升级 Pycharm 版本

官方反制手段越来越严厉，这个版本能激活，新版本大概率补丁就被搬了。所以，如果打开 Pycharm 后，右下角若出现提示升级新版本，请不要升级版本。能用就行，它不香嘛！
也可以手动关闭升级提示，这样就可以防止控制不住自己升级了。

### 激活成功后，补丁文件夹能不能删掉或者移动？

前文中的环境变量，小伙伴也看到了，对应了你放置补丁位置的路径，删除掉或者移动，再打开 Pycharm 就找不到对应文件了，激活也就失效了。放着吃灰就行，别动它。
