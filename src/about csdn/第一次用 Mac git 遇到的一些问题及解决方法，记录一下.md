# 第一次用 Mac git 遇到的一些问题及解决方法，记录一下

## 前言
近期入手了一台 MacBook Pro ，奈何 MacOS 真是让人又爱又恨，学不会呀学不会，那还不得慢慢学。这次记录的是第一次用 Mac git 遇到的一些问题。

- 首先介绍一下配置过程，有点套娃：
1. 首先第一步要下载 git ，Mac 怎么下软件？ App Store？找不到呀，官网？不敢乱下，这可是 M1 芯片。
2. 使用 Mac 真正的 'App Store' ：Homebrew（ [MacOs M1安装Homebrew 在国内最简单方法](https://blog.csdn.net/sinat_38184748/article/details/114115441)）
3. 下载好后直接 `brew install git` 就装好 git 了。

提醒一下，M1芯片的终端是默认 zhs，命令不要用错了。
## Q1：Git中全局忽略.DS_Store文件
git 安装好后第一件事那当然是首先 `git clone your_love` ，这个过程极其舒适，极其丝滑，没有任何的报错啊，然后问题来了。

将代码克隆到本地后，`git status` 发现密密麻麻的 `untrack .DS_Store`，对于处女座的我怎么能忍受这样的事情发生呢，直接上干货：

__忽略当前仓库的 `DS_Store`：__
- 在 `.gitignore`里面添加`.DS_Store` 和 `*/.DS_Store` 。(`Command + Shift + .` 打开隐藏文件)

__[Git中全局忽略.DS_Store文件](https://www.jianshu.com/p/8c0d262e49a6)：__我不太喜欢全局设置，有兴趣的可以自己看看。

---

> 你以为结束了吗，不，上面是卖家秀，下面来看看买家秀吧。

首先，我以为 `.DS_Store` 这个玩意是一个文件夹，然后我添加的是 `*.DS_Store/`，小心翼翼的只 `git add .gitignore` 然后 `commit` , `status` 发现还是会有  `untrack .DS_Store`，鬼使神差的以为是 `.gitignore` 没有生效，其实已经生效了，但是我提交了，这边本地和远程仓库中都有了`DS_Store`。

- 这就是后续问题的背景。

## Q2：macos LibreSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443
标题看得懂不，我反正看不懂，但我知道这是报错。

这是 `git push` 时产生的报错，不是 `time out`，是 `SSL_ERROR`，我尝试性的开了一下我的梯子，很顺利的就push上去了，但是我在Windows下可是不需要梯子就能push的，问题在哪呢？

- 其实就是我的梯子搞的鬼，梯子将配置信息写入了 `~/.gitconfig` 里面，使用以下命令即可：

`git config --global http.sslBackend "openssl" `

## Q3：如何删除 Mac 和 github 的 .DS_Store
网络上有很多见解下，那种高级命令说实话我不是很敢用，我列出来你们用用：

```python
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
```
命令解释：在当前文件夹以及当前文件夹的子文件夹中找到所有的.DS_Store文件，并将找到的文件通过管道传给xargs来处理。注意几个参数的理解： 

-print0：在find后不添加换行符（-print默认会添加换行符） 

-0：将管道送来的字符串当做普通的字符串，不做任何转义处理。

---

如果文件结构不是很复杂，可以先在 github 上删除所有的  .DS_Store，然后 `git pull`，这时你可能会出现这样的报错：
```
error: failed to push some refs to 'git@github.com---------.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
这就是 `.DS_Store` 在Mac本地进行了更新，导致你没法提交代码，所以不忽略这个玩意的人肯定会后悔的，还会有泄密的可能性哟。
- 先将本地仓库版本回退到上个版本。
`git reset --hard`	 
- 然后再 拉取代码。
`git pull`
---
github主页:[https://github.com/Jacob-xyb](https://github.com/Jacob-xyb)
