# Conda介绍

[MiniConda官网下载地址](https://docs.conda.io/en/latest/miniconda.html)

# Conda常用命令

```python
conda --version		# 获取版本号
conda -V			
conda --help		# 获取帮助
conda -h
conda update --help	# 获取某一条帮助
conda remove --help
conda env -h		# 查看环境管理的全部命令
```

## 环境管理操作

```python
# 系统变量
1）C:\Users\Administrator\Miniconda3;
2）C:\Users\Administrator\Miniconda3\Scripts;
3）C:\Users\Administrator\Miniconda3\Library\bin; 
```

### 查看

- 查看环境相关信息

```python
# 列举当前所有环境
conda info --envs
conda info -e
conda env list
```

- 查看环境安装包信息

```python
conda list    			    # 查看当前环境下已安装的包
conda list -n [your_env]   	# 查看某个指定环境的已安装包
```

### 创建

```python
# 创建环境
conda create --name your_env_name
# 创建指定python版本的环境
conda create --name your_env_name python=2.7
conda create --name your_env_name python=3
conda create --name your_env_name python=3.5
# 创建包含某些包的环境
conda create --name your_env_name numpy scipy
```

### 环境操作

```python
# 激活环境
conda activate your_env_name
# 退出环境
conda deactivate 
# 复制环境
conda create --name new_env_name --clone old_env_name 
# 删除环境
conda remove --name your_env_name --all
```

### 下载源配置

```csharp
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/

conda config --set show_channel_urls yes
```

- `conda config --show`		# 查看当前下载源

- `conda config --set show_channel_urls yes`		# 设置搜索时显示通道地址

- `conda config --remove channels [urls] ` 

# Conda常见问题

## conda install 和 pip install 的区别

![img](https://pic1.zhimg.com/80/v2-381c9fe52ef815184fc117ad565b9d7d_720w.jpg?source=1940ef5c)

1. **源不同**

   首先他们的源肯定是不同的，虽然好像都可以替换为国内的源，但是本质上他们使用的源还是不同的。

2. **可安装范围不同**

   pip是一个纯粹的管理和安装python库的工具；

   而conda(主要指conda install)不仅仅可以安装python库，一些依赖的c/c++库或者其他语言库，也是可以一并安装的。比如mkl、cuda这种c c++写的包。

3. **依赖处理的逻辑不同**

   虽然两者都会校验依赖，但是校验的逻辑和方法是不同的。

   pip是按顺序一个一个检查，如果安装第一个库时，引入了第二个库为不兼容的库，那么安装第二个库的时候，就会存在问题；

   而conda是在执行命令时，对所需安装的库做统一的兼容检查，以安装最合适的版本。

   所以使用anaconda的虚拟环境时，最好还是使用conda来安装。

4. **文件不同**

   conda安装的都是编译好的二进制包，不需要你自己编译。这导致了conda装东西的体积一般比较大，尤其是mkl这种，动不动几百兆甚至一G多。

   但pip有时候系统环境没有某个编译器可能会失败，conda不会。

5. **目录**

   conda install xxx：这种方式安装的库都会放在`anaconda3/pkgs`目录下，这样的好处就是，当在某个环境下已经下载好了某个库，再在另一个环境中还需要这个库时，就可以直接从pkgs目录下将该库复制至新环境而不用重复下载。

   pip install xxx：分两种情况，一种情况就是当前conda环境的python是conda安装的，和系统的不一样，那么xxx会被安装到`anaconda3/envs/current_env/lib/python3.x/site-packages`文件夹中，如果当前环境用的是系统的python，那么xxx会通常会被安装到`~/.local/lib/python3.x/site-packages`文件夹中

   这里引出一个问题：conda和pip安装同一个xxx库情况下，conda环境下python代码中import xxx时，谁安装的xxx优先级较高会被import，这个问题通过下面这条命令可以解决：

   ```python
   (py3.6) [~/anaconda3/pkgs @ s64]$ python -m site
   sys.path = [
       '~/anaconda3/pkgs',
       '~/anaconda3/envs/py3.6/lib/python36.zip',
       '~/anaconda3/envs/py3.6/lib/python3.6',
       '~/anaconda3/envs/py3.6/lib/python3.6/lib-dynload',
       '~/anaconda3/envs/py3.6/lib/python3.6/site-packages',
   ]
   USER_BASE: '~/.local' (exists)
   USER_SITE: '~/.local/lib/python3.6/site-packages' (doesn't exist)
   ENABLE_USER_SITE: True
   ```

   这里的USER_BASE 和USER_SITE其实就是用户自定义的启用Python脚本和依赖安装包的基础路径，从上面的输出可以看到，import xxx时，先找的是anaconda3/pkgs目录，所以conda安装的包会被import进来。

   

