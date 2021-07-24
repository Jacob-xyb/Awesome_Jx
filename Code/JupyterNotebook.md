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
- 去掉该行前面的 `#`；在打算存放文件的位置先新建一个文件夹（很重要，最好是英文的），然后将新的路径设置在单引号中，保存配置文件。  

![img](https://i.loli.net/2021/07/14/sS69drQGoWP5gEz.png)

- 最后还需要在开始菜单找到 `jupyter notebook` 快捷键，右键➡更多➡打开文件所在位置，找打快捷方式在文件中的位置，右键➡属性➡目标，去掉最后的`%USERPROFILE%`，应用，确定。
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

# jupyter notebook主题

**[主题展示](https://blog.csdn.net/qq_41621362/article/details/89894126?utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromMachineLearnPai2~default-2.control&dist_request_id=1332024.6981.16189848172240689&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromMachineLearnPai2~default-2.control)；[详细操作](https://blog.csdn.net/qq_30565883/article/details/79444750#commentsedit)；**

## 安装主题

```python
pip install --upgrade jupyterthemes		# anaconda prompt

# 常用操作
jt -l		# 查看主题
jt -r		# 恢复默认主题
```

## 推荐主题

```python
jt -t chesterish -fs 14 -cellw 85% -ofs 13 -dfs 11 -T
jt -t chesterish -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N		# 1
jt -t grade3 -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t gruvboxd -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N		# 1
jt -t gruvboxl -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t monokai -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t oceans16 -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t onedork -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t solarizedd -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t solarizedl -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N

# 含义
-f(字体)  -fs(字体大小) -cellw(占屏比或宽度)  -ofs(输出段的字号)  -dfs(表头的字号) -T(显示工具栏)  -N(显示自己主机名)
```

## 修改主题

**注释字体修改（Italia 斜体改 normal）**

打开文件夹 `C:\Users\Lyun\.jupyter\custom`

找到文件并打开 `custom.css`

找到`cm-comment`中的内容，原内容为：

```
 color: #75715e;
 font-style: italic
```

修改后

```
color: #75715e;
font-style: normal
```

# Nbextensions

## 个人配置

![img](https://i.loli.net/2021/06/11/HLFnG9CArI6WamR.png?ynotemdtimestamp=1626252559989)