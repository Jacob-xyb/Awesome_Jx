# 基础使用说明

## 编辑模式

- 绿色：编辑模式 

- 蓝色：命令行模式

> 编辑模式下按 Esc 进入命令行模式
>
> 命令行模式下按 Enter 进入编辑模式

## 相关设置说明

### 创建/初始化 config文档

- 打开anaconda prompt
- 输入：`jupyter notebook --generate-config`
- 生成：`Writing default config to: /Users/name/.jupyter/jupyter_notebook_config.py`

### 设置默认打开目录

- 打开文件：`jupyter_notebook_config.py`
- 找到：`#c.NotebookApp.notebook_dir = ‘’`
- 修改为你想设置的路径，然后保存
- 最后还需要在开始菜单找到 jupyter notebook 快捷键，右键➡更多➡打开文件所在位置，找打快捷方式在文件中的位置，右键➡属性➡目标，去掉最后的 %USERPROFILE%，应用、确定。
![更改默认目录](https://img-blog.csdnimg.cn/20190827175022714.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMTA4ODAz,size_16,color_FFFFFF,t_70)

> MacOS并不需要设置，会在当前目录启动 `jupyter notebook`。

### 设置默认浏览器

- 打开文件：jupyter_notebook_config.py

- 找到：找到 # c.NotebookApp.browser = ''''

- 在下方添加

```python
import webbrowser
webbrowser.register("chrome",None,webbrowser.GenericBrowser(r"C:\\ProgramFiles(x86)\\Google\\Chrome\\Application\\chrome.exe"))
c.NotebookApp.browser = 'chrome'
```

> MacOS并不需要设置，会用系统默认的浏览器。