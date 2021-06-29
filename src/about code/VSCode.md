# VSCode
## 快捷键

### 全局

```python
Ctrl + Shift + P			# 显示所有命令
Ctrl + Shift + X			# 打开应用商店(会与QQ浏览器的区域截图快捷键冲突)
```
### 文本

```python
F5		# 运行程序
Ctrl + D		# 将下一个查找匹配项添加到选择
```

### Ctrl + Shift + P

- `Ctrl + Shift + P`		# 显示所有命令

```python
//	命令						//中文
view:toggle menu bar		# 视图：切换菜单栏
```

### 快捷键终结设置教程

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

### vscode-icons

- 根据 文件类型 显示 图标。

> 个人感觉非常好用，毕竟撸代码的心情会好很多。

### Bracket Pair Colorizer

- 为括号生成不同颜色，能醒目的区分括号。
- 编写多层结构时简直不要太好用。

![](https://i.loli.net/2021/06/29/1HyTLbI3wcnlYxm.png)

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

# VSCode for Python

## 插件

### 必装插件

- __Python__

写 Python 不装 Python 插件怎么玩？

### 常用插件

- __配置 flake8__

安装 flake8 之后写代码的时候编辑器就会提示哪里出错，代码格式不规范也会提示。

1. 打开命令行
2. 输入 "pip install flake8"
3. 安装flake8成功后，打开VScode，文件->首选项->用户设置，在settings.json文件中输入"python.linting.flake8Enabled": true

> 新手推荐使用一下，大佬就不用受这个约束了，大佬心中自有法则。

# 遇到的问题

## 通用问题

### lauch.json

- 生成：进入 __调试__ 界面，点击 __配置__ 按钮。

- 查看：__工作目录__ --> __.vscode__

## Python

### VScode Python no module

在lauch.json中，修改 "env": {}为 ：

`"env": {"PYTHONPATH":"${workspaceRoot}"}`

修改后，就可以在 __vscode__ 调用自己的包了。

### pylint 不足以应对 django 框架

[解决方案](https://www.bbsmax.com/A/A2dmq7Aqde/)