# VSCode

## 初次接触VSCode先做些什么？

- __下载--安装，开源且免费，没啥好说的。__

- __自动保存文件__

主界面 -- 文件 -- 首选项 -- 设置 -- 常用设置 -- File:Auto Save -- 选择打开即可。

---

1. 英文不好的同学安装的第一个插件应该就是 `Chinese` ，安排！。

![](https://i.loli.net/2021/06/11/JDx67bpEdo2I4nm.png)

安装好后重启一下即可生效。

2. 如何快速了解 vscode 中的快捷键？

百度、官网 or vscode。

`Crtl + k  Ctrl + s`	# 个人理解： keyboard shortcut (k, s)

or

`文件 -- 首选项 -- 键盘快捷方式`

![](https://i.loli.net/2021/06/11/Q8KE63dwZpMaVHk.png)

常用快捷键见汇总章节。

3. 用 Microsoft or github 账号登陆后可以同步 VSCode 的设置。

![](https://i.loli.net/2021/06/11/XEPx4kwbS8lQdYI.png)

## 快捷键终极设置教程

1. 简单的设置方式

- 文件 -> 首选项 -> 键盘快捷方式

![](https://i.loli.net/2021/06/29/SsGFRMhyTjnO94g.png)

- 这里就可以自定义自己喜欢的快捷键了

2. 进阶教程

- 在上述界面中找到右上角的图标，打开键盘快捷键方式(JSON)

![](https://i.loli.net/2021/06/29/TqVZtdXLW9AwKuH.png)

- 可以在`.json`文件中自由编辑快捷键的方式了，command命令可以在上一个界面右键复制命令ID获取。

![](https://i.loli.net/2021/06/29/Mnwi8yHh2rZqXSU.png)

## 插件

- 边框栏右拉可以查看插件图标、评价、启用情况等。

### vscode-icons

- 根据 文件类型 显示 图标。

> 个人感觉非常好用，毕竟撸代码的心情会好很多。

### Bracket Pair Colorizer

- 为括号生成不同颜色，能醒目的区分括号。
- 编写多层结构时简直不要太好用。

![](https://i.loli.net/2021/06/29/1HyTLbI3wcnlYxm.png)

### Markdown All in One

- 将MarkDown配置好，还有许多快捷键。

![image-20210630164723603](https://i.loli.net/2021/06/30/RmOBTfNYuWD4XF6.png)

### Markdown Preview Github Styling

- 这个不多说，将MarkDown预览变为github风格

![image-20210630164834343](https://i.loli.net/2021/06/30/heTYxkIv9qsZOdM.png)

### filesize

- 最下方显示文件大小

![image-20210706092251403](https://i.loli.net/2021/07/06/l8H9DayKSMVqbXm.png)

### Code Runner

- 我刚开始感觉还用不上，运行代码找不到快捷键后试了一下真香，默认快捷键`Ctrl + Alt + N` 一键运行代码。

![image-20210713163827767](https://i.loli.net/2021/07/13/21MPWJa7EoDUAxp.png)

### TabOut

- tab键直接从括号或者引号中跳出，不再需要去按方向键或者end键。强推！！

![image-20210723172104701](https://i.loli.net/2021/07/23/ZeNsOhwMr27dY4W.png)

# VSCode 进阶

## 工作区详解

VSCode的工作区和文件夹是有区别的，工作区是为了更好地管理自己的工作环境，例如JAVA环境，C++环境和python环境，每个环境只需要开启对应环境的插件即可，不必占用多余的内存。

### VSCode 设置

![](https://i.loli.net/2021/06/29/u9tdw2ELmPX87zc.png)

- 设置的优先级：

  系统默认(不可修改)  <  用户设置  <  工作区设置  <  文件夹设置

- [如何理解](https://www.jianshu.com/p/25706af1f6a7)

1. 用户设置即全局设置，用户自行设定好后，每次打开VSCode即使用的此设定，若某项无设定即使用默认设置。
2. 工作区设置即工作环境设置，可对不同的工作环境是用不同的工作环境，若某项无设定，即使用上述设置。
3. 文件夹设置即为项目设置，将一个文件夹当成一个项目，对同一个工作环境下的不同项目，使用不同的设置，若某项无设定，即使用上述设置。

### 创建工作区

1. 首先要创建一个工作区(`.code-workspace` 结尾的文件)：由 `文件 -- 工作区另存`创建一个工作区，放在`./project` 比较好。

- 例如我创建了 `python.conde-worksapce` 工作区，然后在增加path路径，就可以添加别的项目了。

![image-20210629181010923](https://i.loli.net/2021/06/29/sd6UPOX3ZtuSq81.png)

### 如何在不同的工作区启用/禁用不同的插件

- 找到当前工作区不需要的插件，选择"禁用(工作区)"

# VSCode for Python

## 常用设置

### 工作台-双击开启

- vscode默认是单击打开文件，用惯pycham的我是非常不习惯的，而且有时候单击选定就会打开文件这就很奇怪，所以找到 `工作台 -- Open Mode` 选择 `doubleClick`即可。

![image-20210707103802055](https://i.loli.net/2021/07/07/mlU1RP5Nax9ShD2.png)

### 配置 flake8

安装 flake8 之后写代码的时候编辑器就会提示哪里出错，代码格式不规范也会提示。

1. 打开命令行
2. 输入 "pip install flake8"
3. 安装flake8成功后，打开VScode，文件->首选项->用户设置，在settings.json文件中输入"python.linting.flake8Enabled": true

> 新手推荐使用一下，大佬就不用受这个约束了，大佬心中自有法则。

## 插件

- 必装插件

### Python

写 Python 不装 Python 插件怎么玩？

### Python Preview

- `Python Preview`可展现可视化调试的过程，并添加到我们的Python代码中。它将调试代码转换为带有动画和图形元素的交互式会话，以表示应用程序状态，对于代码调试非常直观

![img](https://img-blog.csdnimg.cn/img_convert/7e35deb82d27edb53c1abc255ca7852b.gif)

### python snippets

- 代码块提示，很方便。

![image-20210712153815167](https://i.loli.net/2021/07/12/2BNXAKjEsV8MIWk.png)

### Python Docstring Generator

- 编写说明文档自动扩展，必装。

![image-20210712170650222](https://i.loli.net/2021/07/12/FhJec6QHaWSCABY.png)

---

- 比较推荐

### AREPL for python

- AREPL automatically evaluates python code in real-time as you type.
- 如果是频繁写入写出的话记得要关掉。

![image-20210712162140152](https://i.loli.net/2021/07/12/XdFBatjxENGZJWu.png)

### Kite AutoComplete AI Code: Python

- kite功能非常强大，可以更方便的查看函数文档，但是最强大的代码补全和代码补全插件有点重复了，也不知道怎么关，有点忧伤。

![image-20210712172634364](https://i.loli.net/2021/07/12/3kHtF7G5WeTIUXd.png)

## 插件相关设置

### Code Runner

- 使用 Code Runner 时切换目录

  `shift + ctrl + p` 打开 `setting设置`
  
  ![image-20210824153541121](https://i.loli.net/2021/08/24/36Eb5HICQDmiayZ.png)
  
  ![image-20210824154258211](https://i.loli.net/2021/08/24/BOkIG8RSsv7DugM.png)
  
  python那一行改为：`"python": "cd $dir \n python -u $fileName",` 即可。

# VSCode for C++

## 如何用VSCode写C++

### Mac篇

1. 需要安装一个编译器：command line tools

在终端中输入以下指令：

`xcode-select --install`

如果出现：

`xcode-select: error: command line tools are already installed, use "Software Update" to install updates`

说明你的Mac已经安装了编译器，直接进行下一步即可，否则按照提示安装编译器。

2. vs code需要安装的插件

目前我是安装了两个插件：`C/C++` 和 `code runner`

其中`code runner` 插件中进行设置一下，搜索框中搜索`terminal` 将 `Run IN Terminal` 打勾。

![image-20210718192655391](https://i.loli.net/2021/07/18/ctu7A8fSTHbk1ZQ.png)

3. 运行一个代码

然后创建一个`.cpp`文件，运行一下代码：

```cpp
#include <iostream>
int main()
{
    std::cout<<"hello world"<<std::endl;
    return 0;
}
```

能打印出`hello world`就说明最最基本的C++环境已经配置成功了～

### Windows篇
毕竟vscode是全平台，visualstudio虽然很强大，但是Unix并没有，而且有时还会写一下其他的语言，接下来讲解一下Windows下如何配置vscode写C++。
> 编译器

- 下载

  同样的Windows下需要安装一个编译器：[mingw-w64](http://www.mingw-w64.org/doku.php/download)

- 配置环境

  以WIN10为例 ，`此电脑-属性-高级系统设置-环境变量-系统变量-path`，添加一条D:\Program Files\mingw-w64\i686-8.1.0-posix-dwarf-rt_v6-rev0\mingw32\bin（你安装编译工具路径）

- 检查是否配置成功

  打开cmd终端，输入`gcc -v`，没有报错就算配置成功了~
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210720094210271.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDU2MDY5OA==,size_16,color_FFFFFF,t_70)
> 安装插件

- C/C++

  这是必备的，不用解释。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210720094822238.png)
- Code Runner
  
  这个插件可以直接运行C++代码。快捷键：`Ctrl + Alt + N`

  `Ctrl + P` 搜索  `Run In Terminal `，打上`√` 就可以让程序直接运行在vscode的集成控制台上。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210720094900880.png)

      code runner插件有一个局限,code runner插件的原理其实是自动在控制台下帮助我们输入g++ xxx.cpp -o xxx.exe(假设是默认情况)这条编译指令,不会再添加额外的命令,比如如果代码中使用了winsock2用g++编译的话需要额外添加-lwsock32指令,即完整指令为g++ xxx.cpp -o xxx.exe -lwsock32,此时直接使用code runner的话会无法编译,这种情况应该使用上面提到的vscode集成控制台手动输入编译指令编译。

> TODO

- 若是要问我如何`F5`调试，抱歉，我亲生使用大佬们的各种方法，百花齐放没有一个在我身上成功过，目前能直接运行已经很满意了，调试的事情等我回炉深造一下再来讲解~

# 遇到的问题

## 通用问题

### lauch.json

- 生成：进入 __调试__ 界面，点击 __配置__ 按钮。
- 查看：__工作目录__ --> __.vscode__

### setting.json

- 左下角`设置`  --  右上角`打开设置json`

[setting.json打开方式](https://www.jb51.net/softjc/730336.html)

### MarkDown图片无法显示

- 这是由于 VSCode 中MarkDown默认配置中只允许载入安全内容，更改设置即可。

- 在MarkDown文件中输入快捷键 `Ctrl + Shift + P` 打开命令框，搜索MarkDown，找到更改预览安全设置。

![image-20210630181155527](https://i.loli.net/2021/06/30/PSF6ayrQEit8ezl.png)

- 选择 `允许不安全内容` 即可。

![image-20210630181422694](https://i.loli.net/2021/06/30/JvrBVZLf9T1tuik.png)

## Python

### VScode Python no module

- 测试环境

在lauch.json中，修改 `"env": {}` 为 ：

`"env": {"PYTHONPATH":"${workspaceRoot}"}`

修改后，就可以在 __vscode__ 调用自己的包了。

- 终端

将项目路径添加到系统路径中即可。

```python
import sys
sys.path.append("绝对路径/相对路径")		# 用两种路径都是可以的
```

- 详细剖析

说到底就是一个系统路径配置的一个问题，工作目录是动态的，因此没法在系统路径中间进行配置，coding时需要临时配置，pycharm帮忙完成了这个过程，VSCode则需要自己手动完成，所以Pycharm运行代码不报错，VSCode和终端运行则报错。

```python
Pycharm会自动添加当前的工作目录；因此，如果我添加一个包含在CWD中的模块，而这个模块不在PythonPath中，它可以正常工作。

但是当从终端运行时，Python确实会报错，因为我的import语句引用了不可访问的模块，因为CWD没有添加到PYTHONPATH中。（在从Pycharm和terminal运行时，我确实验证了打印出 `sys.path` 的内容）
```

**举个例子：**

项目结构如下图：

![image-20210706163021018](https://i.loli.net/2021/07/06/jrDAkByVR786XN3.png)

`__class__.py` 运行 `from Jx.__main__ import *` ，这在pycharm是不会报错的，但是在VSCode会报错。

我们此时打印一下运行时的环境：

```python
import sys
print(sys.path)
```

**pycharm**

```python
['~\database-search-algorithm\\Jx', '-\database-search-algorithm', *基础环境]
```

**VSCode**

```python
['~\database-search-algorithm\\Jx', *基础环境]
```

可以看出VSCode是没有添加工作区的根目录进去的，我们尝试着手动添加进去：

```python
import sys
sys.path.append("../")
print(sys.path)
```

然后你会发现，工作区的根目录就添加进去了，然后VSCode也没有报错了。

**加深理解：**

如果项目结构是这样的：

![image-20210706164653933](https://i.loli.net/2021/07/06/vKZxon7dQUrbwGe.png)

由于 `'~\database-search-algorithm\\Jx'` 是默认添加到系统路径了的，因此在`__class__.py` 运行 `from tests.__main__ import *` 在pycharm和VSCode里都不会报错。

> 个人还是认为每次手动添加会很麻烦，也不知道会不会影响打包，如有新发现，会立即更新。

### pylint 不足以应对 django 框架

[解决方案](https://www.bbsmax.com/A/A2dmq7Aqde/)

### Python in VSCode 非常慢

- 对比 `Pycharm` 速度是3倍的差距。
- 仔细分析后 F5 运行 python 是进入了 `debug console`，所以导致速度极低。
- 右键菜单  --  `在终端中运行python文件`
- 有大佬说如果使用了anaconda，终端运行时会自动激活conda环境，导致运行的很慢。

关闭方法：在 `setting.json` 中添加 `"python.terminal.activateEnvironment": false`

|       类型       |  速度  |
| :--------------: | :----: |
|     pycharm      | 163.53 |
|  vscode(debug)   | 293.22 |
| vscode(terminal) | 167.46 |
|  vscode(nocoda)  | 165.56 |

> 关不关conda影响好像不大，但是我觉得开着没必要所以就关了。

### VSCode找不到相对路径文件

遇到的问题是使用相对路径时，VSCode找不到文件会报错，但是pycharm不会，说明代码是没有写错的，问题在于VSCode的配置和pycharm是不一样的。

- `"cwd": "${fileDirname}"`

百度90%的答案都是：更改`launch.json`设置。

在configurations中加入语句`"cwd": "${fileDirname}"`即可变成常规的相对路径模式；否则是以VSCode打开工作区的根目录为当前路径。

但是这只是生效于调试模式，所以很多网友会在下面留言亲测无效，其实有效，只是对于调试模式有效，如何彻底解决这个问题，首先要弄懂终端运行和调试模式的工作地点。

>​    没有`launch.json`的需要在调试里面添加设置，然后在.vscode文件夹里，`Ctrl + P`全局搜索一下就知道有没有了。

- 终端运行和调试模式的工作地点

**终端：** 工作地点就是终端所在目录，初始都是默认在工作区根目录，如果相对路径报错，说明运行的文件是不在当前目录的，可以 cd 切换到运行的文件所在的目录，但是这样过于繁琐，可以在设置中进行设置，我用的是python插件，因此搜索 `execute in file dir`，打勾即可，意思为是否在终端执行命令时使用文件的路径代替现在打开的目录。

**调试：** 调试模式就关联 `launch.json`，默认工作目录就是工作区根目录只能在 json文件里面修改，就是在configurations中加入语句`"cwd": "${fileDirname}"`。

## C++

###  C++ 中文乱码

- 解决 VSCode 终端中运行 C++ 中文乱码

  目前只有`c/c++`文件遇到了乱码问题，因此只更改这两种文件的编码方式，由于以`gbk`方式写代码没有问题，那就在vscode上以`gbk`方式写`c/c++`文件就完事大吉，目前的别扭之处在于每次都要切换一下编码方式，太不友善，而且容易忘，在`setting.json`里面加入以下设置，即可解决我目前遇到的问题。

```cpp
    "[cpp]": {
        "files.encoding": "gbk"
    },
    "[c]": {
        "files.encoding": "gbk"
    }
```

​        这样，只对针对创建这两种文件的编码方式为`gbk`。

### C++  在 windows 上使用utf-8

- 目的是实现`cpp`代码全平台统一

  解释一下why，因为`unix`我改变不了它！！！反观`visual studio`因为莫名的强大，`gbk`和`utf-8`均可拿下，但是Windows上的vscode只能运行`gbk`，现在只需要让vscode灵活起来就OK了。

- 百度千篇一律的复制粘贴

  我不忍想吐槽一下，那些复制粘贴的大佬，你们真的试验成功了吗？fu*k，熬了一个夜，无限的下翻百度，CSDN也被我挖穿，永远都是一样的回答，突然发现了光的时候，什么玩意，娱乐圈乌烟瘴气，IT界也需要开会员引流了？见下图！

  - 好牛皮的CV工程师，好牛皮的CV大佬，我先呕为敬。

  ![image-20210721100806828](https://i.loli.net/2021/07/21/AmW54KtsNUI8cBG.png)

  - 我真的呕了，有技术有必要这样？看ID我更呕了，让我联想到 `Kris Wu`，我呕够了再来写后续...

  ![image-20210721101014178](https://i.loli.net/2021/07/21/V4QGBIxeJ1sf8CW.png)

  ![image-20210721101031994](C:\Users\94978\AppData\Roaming\Typora\typora-user-images\image-20210721101031994.png)

- 1.解决Windows终端

  vscode是使用终端运行代码，虽然vscode有自己的集成终端，但是`Run Code`会自己调用外部终端（因为使用`Run Code`必须要开启`"code-runner.runInTerminal": true`），这就导致了C++代码其实是在`终端`中运行的，请注意我说的是`终端`。

  我很想当然的认为`终端`就是`cmd`，百度`windows 修改 cmd 编码格式`，结果是千篇一律但是都是有效的。

  `Windows + R  -- regedit -- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Command Processor`

  ![](https://i.loli.net/2021/07/21/QJ5KjNp9C4oGtL7.png)

  `右键 -- 新建 -- 字符串值 -- 命名：autorun -- 数值：chcp 65001`

  ![image-20210721102040633](https://i.loli.net/2021/07/21/UC37twGOxRcpb2l.png)

  `autorun`代表运行，相当于打开`cmd`就运行了`chcp 65001`。是的，你想的没错，在vscode里面的终端直接输入也是可以的，但是激活`utf-8`页面后呢，再次`Run Code`他会为你新建一个终端，你气不气，就问你气不气。

  现在可以试一试是否设置成功：`Windows + R -- cmd -- 右键终端窗口 -- 属性`

  ![image-20210721102530132](https://i.loli.net/2021/07/21/wQayWJFGvo5fLsI.png)

  爽翻了，以为万事大吉，看进度条没这么简单。

- 2.深度理解vscode

  在vscode里面当然还是会乱码啦，然后现在要理解一个概念，`终端`只是一个表现形式，`cmd`只是一个`终端`的具体表象，另外一个表象则是`Windows PowerShell`，恰巧vscode默认用的这个。

  ```python
  Windows PowerShell
  版权所有 (C) Microsoft Corporation。保留所有权利。
  ```

  我以为不能切换，OK，我能改`cmd`还不能改`PowerShell`？抱歉，不能，真的不能，[CV工程范例](https://blog.csdn.net/u014756245/article/details/100536552)；包括我添加`autorun`也是没有反应的，我气冲冲的冲到`PowerShell`老家(`.exe`所在地)也没有任何办法。

  思考中：vscode真的不可以切换终端吗？在这里我找到了我要的光。

  打开 vscode 设置，搜索`终端`：

  ![image-20210721103837171](https://i.loli.net/2021/07/21/ZW9ax67YUyXl1rz.png)

  发现终端设置是有69个，我一个一个排查，发现了很多有趣的设置，也发现了我要的光。

  ![image-20210721104039255](https://i.loli.net/2021/07/21/TeimNVtJwOCKXAE.png)

  搜索`terminal win`就会发现有关`windows`下的设置，将`default profile`设置成 `Command Prompt`即可，这就是我们刚刚改好的`cmd`，就又可以开心的敲代码了。

- 小结

  1. 更改`cmd`编码：`Windows + R  -- regedit -- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Command Processor`；`右键 -- 新建 -- 字符串值 -- 命名：autorun -- 数值：chcp 65001`。
  2. 更改`vscode`设置：`设置 -- terminal win`；`default profile:Windows`改为  `Command Prompt`即可。
  3. 好处，不会影响Windows上其他依赖`gbk`的程序，因为大部分都是用`PowerShell`运行的，同时vscode下也可以在`gbk`和`utf-8`来回切换。

# VSCode使用小技巧

## 快捷键篇

```python
F2		# 文件重命名(需点击选中)
F5		# debug模式运行
Ctrl + F5		# debug模式运行(不调试)
```

## 应用篇

### 多开项目

- 一般可以 `Ctrl + Shift + N` 新建窗口然后打开文件夹。
- 更快捷的是 `文件 -- 打开最近文件 -- Ctrl+单击` 即可新建窗口。(快捷方式：`Alt+F -- R -- Ctrl+单击`)

### 快速翻滚

- 按住Alt + 滚轮可以实现快速翻滚，翻滚速度在 `设置 -- 文本编辑器 -- Editor:Fast Scroll Sensitivity` 处调节。(默认为5还比较适用)

![image-20210707112438300](https://i.loli.net/2021/07/07/QV45luvCtBSo2Hm.png)