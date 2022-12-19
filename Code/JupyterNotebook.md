# 基础使用说明

## 安装及运行

- 安装

1. 如果只有python环境，就直接用 pip安装	`pip install notebook`	
2. 如果安装了 `anaconda`，会自带 JupyterNotebook
3. 如果安装了 `miniConda` ，可以使用 conda 安装 `conda install notebook`

- 运行

​	`jupyter notebook`

## 编辑模式

- 绿色：编辑模式 

- 蓝色：命令行模式

> 编辑模式下按 Esc 进入命令行模式
>
> 命令行模式下按 Enter 进入编辑模式

## 相关设置说明

### exe所在位置

一般只有用miniconda安装时开始菜单中才会不显示。

地址：D:\ProgramData\miniconda3\Scripts\jupyter-notebook.exe

### 创建/初始化 config文档

- 打开anaconda prompt
- 输入：`jupyter notebook --generate-config`
- 生成：`Writing default config to: /Users/name/.jupyter/jupyter_notebook_config.py`

### 设置默认打开目录

- 打开文件：`jupyter_notebook_config.py`
- 找到：`# c.NotebookApp.notebook_dir = ''` 
- 去掉该行前面的 `#`；在打算存放文件的位置先新建一个文件夹（很重要，最好是英文的），然后将新的路径设置在单引号中，保存配置文件。  

![img](https://i.loli.net/2021/07/14/sS69drQGoWP5gEz.png)

- 最后还需要在开始菜单找到 `jupyter notebook` 快捷键，右键➡更多➡打开文件所在位置，找打快捷方式在文件中的位置，右键➡属性➡目标，去掉最后的`"%USERPROFILE%"`，应用，确定。
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

### 切换内核

1. 在 base 环境中安装 nb_conda

   `conda install nb_conda`

2. 在需要切换的环境中安装 jupyter

   `conda install jupyter`

3. 需要注意的是，运行的内核需要安装 autopep8

   `pip install autopep8`

# jupyter notebook主题

**[主题展示](https://blog.csdn.net/qq_41621362/article/details/89894126?utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromMachineLearnPai2~default-2.control&dist_request_id=1332024.6981.16189848172240689&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromMachineLearnPai2~default-2.control)；[详细操作](https://blog.csdn.net/qq_30565883/article/details/79444750#commentsedit)；**

## 安装主题

```python
pip install jupyterthemes		# anaconda prompt || cmd

# 常用操作
jt -l		# 查看主题
jt -r		# 恢复默认主题
jt -h		# 查看帮助
```

## 可用参数

![img](https://img-blog.csdn.net/2018030513433616)

## 推荐主题

```python
jt -t chesterish -fs 14 -cellw 85% -ofs 13 -dfs 11 -T
jt -t chesterish -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N	# 1
jt -t grade3 -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t gruvboxd -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N		# 2
jt -t gruvboxl -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t monokai -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t oceans16 -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t oceans16 -f fira -fs 13 -cellw 90% -ofs 11 -dfs 11 -T			# 1
jt -t onedork -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t solarizedd -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N
jt -t solarizedl -f fira -fs 11 -cellw 70% -ofs 11 -dfs 11 -T -N

# 含义
-f(字体)  -fs(字体大小) -cellw(占屏比或宽度)  -ofs(输出段的字号)  -dfs(表头的字号) -T(显示工具栏)  -N(显示自己主机名)
```

- 8:`jt -t oceans16 -f fira -fs 13 -cellw 90% -ofs 11 -dfs 11 -T`

![img](https://img-blog.csdn.net/20180305134952457)

## 修改主题

**注释字体修改（Italia 斜体改 normal）**

打开文件夹 `C:\Users\Lyun\.jupyter\custom`

找到文件并打开 `custom.css`

找到`cm-comment`中的内容，原内容为：

```
.cm-s-ipython span.cm-comment {
 color: #928374;
 font-style: italic;
}
```

修改后

```
.cm-s-ipython span.cm-comment {
 color: #928374;
 font-style: normal;
}
```

# Nbextensions

## 安装

试了很多次，conda暂时没有这个源，`pip`是可以安装成功的。

清华源比较快 :smile:

`pip install jupyter_contrib_nbextensions -i https://pypi.tuna.tsinghua.edu.cn/simple`

安装完记得配置一下，不然不会显示的

`jupyter contrib nbextension install --user`

## 个人配置

![img](https://i.loli.net/2021/06/11/HLFnG9CArI6WamR.png?ynotemdtimestamp=1626252559989)

### Variable Inspector

推荐指数：:star::star::star::star::star:

变量监控

![Variable Inspector icon](https://s2.loli.net/2022/04/06/UEqXvOKrYTJIkPp.png)

### Table of Contents (2)

推荐指数：:star::star::star::star::star:

目录

### Autopep8

推荐指数：:star::star::star::star:

需要库：`autopep8`

pep8格式化单元格，默认快捷键：`ctrl + l`

### Collapsible Headings

折叠单元格的功能

![](https://s2.loli.net/2022/04/06/b9YqfOR3JtZc5uA.png)

### Highlight selected word

高亮选中文本

# 遇到的问题

## pytorch

### matplotlib.pyplot出现服务器挂掉、崩溃的问题

点击启动Jupyter notebook的终端程序，终端上会记录Jupyter notebook的运行信息，可以从中查看错误原因

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201201215552550.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDY3MTQxOA==,size_16,color_FFFFFF,t_70)

```cpp
OMP: Error #15: Initializing libiomp5md.dll, but found libiomp5md.dll already initialized.
OMP: Hint This means that multiple copies of the OpenMP runtime have been linked into the program. That is dangerous, since it can degrade performance or cause incorrect results. The best thing to do is to ensure that only a single OpenMP runtime is linked into the process, e.g. by avoiding static linking of the OpenMP runtime in any library. As an unsafe, unsupported, undocumented workaround you can set the environment variable KMP_DUPLICATE_LIB_OK=TRUE to allow the program to continue to execute, but that may cause crashes or silently produce incorrect results. For more information, please see http://www.intel.com/software/products/support/.
[I 21:55:26.126 NotebookApp] KernelRestarter: restarting kernel (1/5), keep random ports
kernel 4e65633e-7300-4a63-a0fc-1df4e657672f restarted
```

解决：
在pytorch中导入以下模块:

```python
import os
os.environ["KMP_DUPLICATE_LIB_OK"]="TRUE"
```

 