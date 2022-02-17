# pip 操作

## 相关操作

### 控制台常用操作

- `pip --version` ：显示版本和路径

- `pip --help` ：获取帮助

- `pip install -U pip` : 升级 pip

  平替：`sudo easy_install --upgrade pip`

- `pip list` ：查看python安装的第三方模块

- `pip freeze` ：老版本通用

### 代码操作

```python
import networkx 
networkx.__version__
```

## 下载

### 基础操作

- 最基础操作

  ```python
  # 安装包
  pip install SomePackage              # 最新版本
  pip install SomePackage==1.0.4       # 指定版本
  pip install SomePackage>=1.0.4       # 最小版本
  pip install SomeWhat.whl		# 安装当前路径的 whl 文件
  
  # 升级包
  pip install --upgrade SomePackage
  # 升级指定的包，通过使用==, >=, <=, >, < 来指定一个版本号。
  
  # 卸载包
  pip uninstall SomePackage
  
  # 搜索包
  pip search SomePackage
  
  # 显示安装包信息
  pip show 
  
  # 查看指定包的详细信息
  pip show -f SomePackage
  
  # 已安装包列表
  pip list
  
  # 查看可升级的包
  pip list -o
  ```
  

### 下载加速

pip安装是默认国外的镜像，速度可能会很慢

可以通过修改源进行加速：`pip install package -i web`

web:

```python
https://pypi.tuna.tsinghua.edu.cn/simple		# 清华大学
https://pypi.douban.com/simple					# 豆瓣(douban) 
https://pypi.mirrors.ustc.edu.cn/simple/		# 中国科技大学 
http://mirrors.aliyun.com/pypi/simple/			# 阿里云 
http://pypi.mirrors.ustc.edu.cn/simple/			# 中国科学技术大学
```

example：

```python
pip install PyQt5 -i https://pypi.douban.com/simple
```

- 默认设置链接（不推荐）

```python
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

### conda虚拟环境pip下载

这是一个非常不好弄的问题，查看当前的环境的指令一般是：`pip list` 。但是往往有虚拟环境存在时，打印出来的是全局的包列表，显然用 `conda list` 才是当前环境安装的包。

问题出现了，`conda create -n env_name` 创建一个新的虚拟环境后，直接 `pip install` 发现并没有将依赖包安装到当前环境，而是安装到 `base` 环境中了，试了千百种方法，踩过无数大坑，最终想出一种比较稳妥的方法。

- 为什么执着于 `pip install` 安装？

  `conda install` 很香，但是

  ```python
  # 1.有些包conda无法安装；
  # 2.pip安装更智能；
  # 3.pip download 可以导入当前环境的所有包（这也是我用虚拟环境的原因，严格把控环境配置）
  ```

- `pip install` 是何物？

  由于我最常用的电脑是有加密系统的，可能大家并没有我类似的烦恼，但是，我找出的方法 `有理可据，深入原理` 。

  `pip install` 底层无非调用当前环境的 `pip.exe` (不限pip3.exe等等)，以这个角度出发，直接调用当前环境的 `pip.exe` 是不是就能完美解决问题呢。

  事实证明的确如此

  ```python
  # 原代码
  pip install package_name
  # 替换成
  D:\ProgramData\Anaconda3\envs\env_name\Scripts\pip.exe intall package_name
  ```

  `conda list` 即可查看是否安装成功。

# pip 自动化安装

## 打包已安装的依赖包

`pip freeze >requirements.txt`  生成已安装包清单

如本地未保留之前下载的各依赖包whl/tar/zip包，则需要用下面的命令从网络下载

```python
pip download xlrd==1.2.0		# 下载到当前文件夹下
pip download -r .\requirements.txt		# 依据requirements.txt 下载到当前文件夹下
pip download -d d:\lib -r .\requirements.txt		# 指定文件下载whl
```

## 批量安装离线whl包

- `pip install --no-index --find-links=path -r requirements.txt`

将 packages 文件夹和 requirements.txt 拷贝至离线机器上某个目录下，

 packages文件夹/ 和 requirements.txt 放在D:\下，命令窗口进入D:\，输入以下命令，依赖包即可批量安装完成

` pip install --no-index --find-links=d:\packages -r requirements.txt`   离线安装依赖包

或者放在同一文件夹下

`pip install --no-index -r requirements.txt`

requirements.txt 内直接是文件名也可以。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200903170105976.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0NjI0MzE1,size_16,color_FFFFFF,t_70#pic_center)

- 下载地址

  packages中的文件就是从https://pypi.python.org/pypi/上下载的whl/zip/gz等包，zip/gz无需解压

## 卸载

`pip uninstall -r requirements.txt -y` 

-y: 默认全部同意

# Python大型库安装

## TensorFlow

一般安装：

`pip install tensorflow`

`pip install tensorflow-gpu`

> 一般方法很慢很慢，因为需要翻墙，因此换用国内源比较快。

`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ tensorflow `

TensorFlow 2.4.0 已经适配 python 3.8 

`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ tensorflow==2.4.0`

---

tips: TensorFlow 2.4.0 目前只有清华源才有镜像（但是容易卡住）

## Pytorch

- Mac安装教程

  打开 pytorch.org 官网，可以选择安装器，Python版本，CUDA 版本。

  例如 Mac Conda Python3.6 CUDA 9.0 的安装命令为：

  ```python
  conda install pytorch torchvision -c pytorch
  ```

  ![PyTorch  Mac 安装教程](http://pytorchchina.com/wp-content/uploads/2018/12/WechatIMG1313.jpeg)

  如果是更加常见的 pip 安装的命令则是：

  ```
  pip3 install torch torchvision
  ```

## PyQt5

- 在线安装

  ```python
  pip install PyQt5 -i https://pypi.douban.com/simple
  ```

- 离线安装

  PyQt5_Qt5-5.15.2-py3-none-win_amd64.whl
PyQt5_sip-12.9.1-cp38-cp38-win_amd64.whl
  PyQt5-5.15.6-cp36-abi3-win_amd64.whl

# Python小型库安装

## 局部敏感哈希包lshash

[官方文档](https://github.com/kayzhu/LSHash)

 在使用局部敏感哈希算法的过程中，发现python有相关实现，但是在下载时报错，很让人抓狂！ 

![](https://img2018.cnblogs.com/blog/1459610/201810/1459610-20181025180207960-1587585797.png)

[解决方法](https://github.com/kayzhu/LSHash/pull/18)：lshash 0.0.4dev 版本的包基于旧版本python开发，新版的python使用会有问题，所以作者搞了个 lshash3 版本，安装时使用

```python
pip install lshash3
```

 命令就可以了。注意：安装时依赖gcc，使用mac的同学可能麻烦点～ 