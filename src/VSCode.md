# VSCode
## 快捷键

```python
F5		# 运行程序
```
## 插件

- __vscode-icons__

根据 文件类型 显示 图标。

> 个人感觉非常好用，毕竟撸代码的心情会好很多。

# 初次接触VSCode先做些什么？

- 下载--安装，开源且免费，没啥好说的。

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