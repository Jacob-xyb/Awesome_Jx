# Mac偏好设置

## delete速度非常慢

- 感觉是比较非人的设置，不明白系统默认设置的初衷是为何。

![截屏2021-06-30 23.17.50](https://i.loli.net/2021/06/30/ClEyRxsc7T3bHBg.png)

- 按照以上设置，将 `按键重复调至最高` 和 `重复前延迟调至最短`，这样 `delete`就能很快的删除了。

# 重要操作

## 文件管理

- 剪切文件

## 终端运行shell脚本(.sh文件)

1. 创建脚本 `touch deploy.sh`
2. 编写脚本：
```d 
git add .
git commit -m "update blog"
git push origin master
```

3. 设置权限：如果报错 `Permission denied`，说明没有权限。

   解决方式为输入命令: `chmod 777 deploy.sh`或者`chmod +x deploy.sh`
   
   __tips:__ 777 权限谨慎使用 为高权限

---

- 写入、读取和执行权限具有以下数字值：
  - r（读）= 4
  
  - w（写）= 2
  
  - x（可执行) = 1
  
  - 无权限 = 0
  
  特定用户类的权限数字是该类的权限值之和。
  
- 777 代表 `属主：7；属组：7；其他：7`为最高权限，一般 750 即可。

---

4. 设置环境变量：如果报错 `command not found: deploy.sh`，说明需要设置 PATH。

   原因：如果执行 `deploy.sh`, shell 会在 `$PATH` 变量包含的路径里去找文件。但是，Unix/Linux 为了安全问题，并没有把当前路径放到 `$PATH` 中，所以有两种方案：

   - `./deploy.sh`: 从当前路径查找。可以使用，但不推荐。

   - 设置PATH：在  `deploy.sh` 文件头部添加 `#!/bin/bash`

     ```
     #!/bin/bash
     git add .
     git commit -m "update blog"
     git push origin master
     ```

# 大型软件安装

## Anaconda

- [M1 mac系统配置Python3开发环境](https://v3u.cn/a_id_189)

### 下载

- 只有 condaforge 支持 ARM 架构。

- 首先下载 [Miniforge3](https://github.com/conda-forge/miniforge/#download)  // 找到对应版本，下载.sh文件。

- Command + Space 打开应用栏搜索终端

- cd .sh 文件所在目录

- 输入 `sh filename`，一路yes到最后即可安装完成。

### 配置

- `vim ~/.zshrc`，加入以下内容：(注意更改自己Mac用户名)

```python
path=('/Users/Jacob/miniforge3/bin' $path)
export PATH
```

> [后续使用教程](https://github.com/Jacob-xyb/Awesome_Jx/blob/master/src/about%20code/MacOS/Miniforge.md)

## VSCode

- 下载地址

  [VSCode官网](https://code.visualstudio.com)

  M1芯片记得选arm架构的下载。

- 由于是微软的官网下载，下载的速度非常非常的慢，发现一个很强的方法可以突破苍穹。

  1. 首先在下载列表中复制下载的链接。

  2. 然后用 `vscode.cdn.azure.cn` 替换下载链接中 `/stable` 之前的内容，然后就会发现速度飞起了。

# APP推荐

## 解压缩工具 Myzip

- Better 365 团队出品，免费，好用，不得不说速度是真的很快很快。

- 同时也想说：这个团队的 APP 其实都很可，哈哈。

## 键指如飞/FlyKey

- Better 365 团队出品，双击Command，集中展示当前 App 快捷键，助你迅速掌握 App 快捷键。

- 快捷键一览无余。

## Better And Better

- Better 365 团队出品，触控板神器，鼠标神器，定制快捷键等等，重要的是，还可以编辑脚本。

# Mac小常识

## Shell

Bash 是最常见的 shell，Mac 中默认 shell 就是 bash；但是mac 10.15 系统以后 shell 默认用得是 zsh。

很多人的 mac 中会使用 zsh 而不是 bash，一大半是因为 oh-my-zsh 这个配置集，它兼容 bash，还有自动补全等好用的功能。zsh 的配置文件\~/.zshrc 。

[知乎 shell、bash 和 zsh](https://zhuanlan.zhihu.com/p/34197680)

