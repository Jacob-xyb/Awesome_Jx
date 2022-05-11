

# 参考链接

[Homebrew使用详解，macOS的第二个Mac App Store!](https://zhuanlan.zhihu.com/p/30704752)

[Mac安装Homebrew的正确姿势](https://www.jianshu.com/p/e0471aa6672d?utm_campaign=hugo)

# Homebrew

## 什么是Homebrew

Homebrew是 mac的包管理器，仅需执行相应的命令,就能下载安装需要的软件包，可以省掉自己去下载、解压、拖拽(安装)等繁琐的步骤。 比如安装服务器 nginx，打开终端执行以下命令即可安装:

```python
brew install nginx
```

## 安装

- **官方安装方式：**

    速度很慢。

```python
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

- **安装镜像：**

    中科大镜像

```python
/bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"
```

## 配置

前面已经提到，Homebrew通常用来下载软件的，但它在安装软件时非常慢。为了提升安装速度，需要更改 Homebrew 的安装源，将其替换成国内镜像。

这里用的是由中科大负责托管维护的 Homebrew 镜像。其中，前两个为必须配置的项目，后两个可按需配置。

- 替换 brew.git

```python
git -C "$(brew --repo)" remote set-url origin https://mirrors.ustc.edu.cn/brew.git
```

- 替换 homebrew-core.git

```python
git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
```







​    