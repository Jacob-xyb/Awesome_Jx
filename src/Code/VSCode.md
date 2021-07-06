# VSCode

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

- 边框栏右拉可以查看插件图标、大小、启用情况等。

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



# 初次接触VSCode先做些什么？

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

# 遇到的问题

## 通用问题

### lauch.json

- 生成：进入 __调试__ 界面，点击 __配置__ 按钮。
- 查看：__工作目录__ --> __.vscode__

### setting.json

- 左下角`设置`  --  右上角`打开设置json`

[setting.json打开方式](https://www.jb51.net/softjc/730336.html)

### VSCode中MarkDown图片无法显示

- 这是由于 VSCode 中MarkDown默认配置中只允许载入安全内容，更改设置即可。

- 在MarkDown文件中输入快捷键 `Ctrl + Shift + P` 打开命令框，搜索MarkDown，找到更改预览安全设置。

![image-20210630181155527](https://i.loli.net/2021/06/30/PSF6ayrQEit8ezl.png)

- 选择 `允许不安全内容` 即可。

![image-20210630181422694](https://i.loli.net/2021/06/30/JvrBVZLf9T1tuik.png)

## Python

### VScode Python no module

在lauch.json中，修改 "env": {}为 ：

`"env": {"PYTHONPATH":"${workspaceRoot}"}`

修改后，就可以在 __vscode__ 调用自己的包了。

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

![image-20210706133959357](C:\Users\94978\Desktop\5gJoNj4VwWtPlfz.png)

