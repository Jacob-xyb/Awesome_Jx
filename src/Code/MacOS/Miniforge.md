# 配置Miniforge

## 安装后需要进行配置

- 安装完成后需要配置一下路径：（zsh下）

  ```
  path=('/Users/liuyue/miniforge3/bin' $path)
  export PATH
  ```

- 存盘后执行命令：

  `source ~/.zshrc`

## 下载源配置

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


# Conda 命令

## 查看命令

```csharp
conda info		# 查看当前 conda 的基本内核，平台，等等信息
conda --version		# 查看conda版本，验证是否安装
conda config --show		# 查看当前下载源
```

## 更新命令

```
conda update conda		# 更新至最新版本，也会更新其它相关包
conda update --all		# 更新所有包
```

