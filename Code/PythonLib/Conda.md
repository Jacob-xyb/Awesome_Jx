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

### 查看

```python
# 列举当前所有环境
conda info --envs
conda env list
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