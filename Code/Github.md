# Git 版本管理控制系统

- 常规命令一张图演示

![image](https://img-blog.csdnimg.cn/img_convert/b7c2d1149f813df1097f1888eb04e94f.png)

# Git 基本操作

## Git 工作流程

- 工作目录 —— 暂存区 —— Git仓库

### 查看指令

```python
git log				# 查看日志信息
git relog				# 查看一行日志
git remote -v		# 查看当前项目的远程git地址
cat .git/HEAD		# 查看当前HEAD
```
### 设置指令

```python
# 和远程仓库建立连接
git remote add origin https://github.com/Jacob-xyb/Projiect  
git remote remove origin https://github.com/Jacob-xyb/Projiect	# 删除远程仓库
```

## Git 基本配置

### Git 配置

- 全局配置：

在使用 git 前，需要告诉 git 你是谁，在向 git 仓库中提交时需要用到的命令：

1. 配置提交人姓名：`git config --global user.name 提交人姓名`
2. 配置提交人邮箱：`git config --global user.email 提交人邮箱`
3. 查看 git 配置信息：`git config --list`

---

- 单独配置;

```python
git config user.name 提交人姓名
git config user.email 提交人邮箱
```

## Git提交

```python
git init				# 初始化仓库
git status				# 查看文件状态
git add 文件列表			# 追踪文件（提交到暂存区）
git commit -m "提交信息"	# 向仓库中提交代码
git log					# 查看提交记录
```

## Git撤销

### 几种常见的撤销场景

1. 用暂存区中的文件覆盖工作目录中的文件：

`git checkout 文件名字`

2. 从暂存区中删除文件：

`git rm --cached 文件`

3. 将 git 仓库中指定的更新记录恢复出来，并且覆盖暂存区和工作目录：

```python
git reset --hard commitID		# 恢复到指定ID版本
git reset --hard HEAD^		# 回退上一个版本
git reset --hard HEAD~1		# 回退上一个版本 // ～n 就是回退n个版本
```

- 注意：如果将版本指针前置的话，指针后面的日志就会消失。

4. 删除 远程仓库 中的文件

`git rm -r --cached 文件`

5. 修改提交的commit注释

`git commit --amend`

然后会进入默认的vim编辑器，修改后保存即可。

### 参数讲解

- `--mixed`

不删除工作空间改动代码，撤销commit，并且撤销git add . 操作

这个为默认参数，`git reset --mixed HEAD^` 和 `git reset HEAD^` 效果是一样的。

- `--soft`

不删除工作空间改动代码，撤销`commit`，不撤销 `git add .`

- `--hard`

删除工作空间改动代码，撤销 `commit`，撤销 `git add .`

注意完成这个操作后，就恢复到了上一次的commit状态。

## Git 分支

### 分支细分

1. 主分支（master）：第一次向 git 仓库中提交更新记录时自动产生的一个分支。
2. 开发分支（develop）：作为开发的分支，基于 master 分支创建。
3. 功能分支（feature）：作为开发具体功能的分支，基于开发分支创建。

### 查看本地和远程分支

```python
# 查看本地分支（*为当前分支）
git branch == git branch --list == git branch -l
# 查看本地和远程分支
git branch --all == git branch -a
# 查看远程所有分支
git branch --remote == git branch -r
# 切换分支
git checkout 分支名称
# 分支重命名
git branch -m [oldName] [newName]
```

- 切换分支之前要保持当前暂存区完全干净，不然会出现错误。

	- 这是由于 git 的暂存区是所有分支共享的，因此，只要未提交(commit)的内容都会在所有分支上呈现。有时，我们还未完成当前分支的功能开发，但是又亟需在另一个分支上修改内容(如：修复一个 BUG)。

	- 一种方式是通过“git commit”(提交)，解决这个问题。但在正常使用中，我们应该在完成某个功能的开发后才提交一个版本，而不是频繁的提交。

[这时，我们可以使用“git stash”(储藏)来解决这个问题。](https://zhuanlan.zhihu.com/p/347073892)

### 创建分支

```python
git branch 分支名称			# 创建分支（基于所在分支创建）
git checkout -b branchName commitId	# 根据指定版本号创建分支
```

### 合并和删除分支

- 合并

```python
git merge 来源分支			# 合并分支（将来源分支合并到当前分支）
```
- 删除

```python
git branch -d 分支名称		# 删除本地分支（如果删除的分支没有被合并是不能删除的）
git branch -D 分支名称		# 强制删除本地分支
git push origin -d 分支名称	# 删除远程分支(Git > v1.7.0)[推荐]
git push origin :分支名称	# 删除远程分支(":"代表删除)
```


### 暂时保存更改

在 git 中，可以暂时提取分支上所有的改动并存储，让开发人员得到一个干净的工作副本，临时转向其他工作。

使用场景：分支临时切

```python
git stash		# 临时保存
git stash pop	# 恢复保存
```

### 分支管理

```python
# 将本地develop分支强制（-f）推送到远程master
# （Jx极力推荐，不过用前三思）
git push origin develop:master -f
# 重置的方法
git checkout master		# 切换到旧分支
git reset --hard develop		# 将本地的旧分支master重置成develop
git push origin master --force	# 强制推送
# 删除远程分支
git push origin --delete develop	# 删除远程仓库
git push origin:develop			# 推送至服务器才行
```


## git config 配置

 Git 有一个工具被称为 git  config，它允许你获得和设置配置变量；这些变量可以控制Git的外观和操作的各个方面。

### 配置文件的存储位置

1. 仓库级：该文件位于当前仓库下，路径`.git/`，文件名为`.gitconfig`，这个配置中的设置只对当前所在仓库有效。	

2. 全局级：`~/.gitconfig` 文件 ：具体到你的用户。PC为例就是`C:\Users\name\.gitconfig`。

3. 系统级：位于git安装目录的config文件，也就是`D:\Program Files\Git\etc\.gitconfig`

### 配置文件生效顺序

- __仓库级 > 全局 > 系统__

### git config 查看

- `git config [--local|--global|--system] --list`

命令参数：`--list`  简写：`-l` （不建议用简写）

```python
git config --local --list		# 查看仓库级
git config --global --list		# 查看全局级
git config --system --list		# 查看系统级
git config --list		# 查看生效配置(三个级别最终计算后的配置信息)
```

### git config 编辑

- `git config [-–local|-–global|-–system] --edit`

命令参数：`--edit`  简写：`-e` （不建议用简写）

```python
git config --local --edit		# 编辑仓库级
git config --global --edit		# 编辑全局级
git config --system --edit		# 编辑系统级
git config --list		# 默认编辑仓库级(这与 --list稍有不同)
```

### git config 增加配置

- `git config [-–local|–-global|-–system] -–add section.key value` (默认是添加在local配置中)

__tips:__ 

1. add后面的section,key,value一项都不能少，否则添加失败。
2. add是增加一项配置，不是将一项配置重新赋值。

### git config 获取配置

- 不需要查看所有配置，只查看某个配置项的值。

- `git config [–-local|–-global|–-system] -–get section.key` (默认提取 local 配置中的内容)

__tips:__ 

1. 如果获取一个section不存在的key值，不会返回任何值。
2. 如果获取一个不存在的section的key值，则会报错。

### git config 删除配置

- `git config [–-local|–-global|-–system] –-unset section.key` (默认删除 local 配置中的内容)

### 全局忽略

- 首先找到全局目录，也就是`C:\Users\name\.gitconfig`所在的目录，Mac一次类推。在全局目录下创建一个文件`.gitignore_global`，里面写好需要忽略的内容，使用以下命令进行连接，这样在全局忽略就可以生效了，`git config --global --list`可以查看检查一下。
- __tips:__全局忽略的好处就是可以删除本地的`.gitignore`文件，GitHub上就不会显示项目中忽略了什么文件了。

```python
git config --global core.excludesfile ~/.gitignore_global		# 设置全局有效
# 设置后，如果仓库中还有.gitignore文件，则两者均会生效，猜测本地的会强一些。
git config --list
```

- __只对本地生效__
  原理很简单，还是在全局目录里创建一个忽略文件，暂且叫`gitignore_global`，填好忽略信息后就可以执行命令了，就会将忽略信息和`gitignore_global`连接起来了，这样忽略只会对本地仓库生效。
```python
git config core.excludesfile ~/.gitignore		# 只对本地有效，不会上传到远程仓库
```


### git config 其他操作

```python
git config http.sslVerify "false"  # 忽略证书错误
```

## git tag

- 标签可以针对某一时间点的版本做标记，常用于版本发布。

### 查看标签

```python
git tag			# 打印出当前仓库的所有标签
git tag -l "v0.1.*"		# 搜索符合模型的标签
git ls-remote --tags origin		# 打印所有的远程标签
git show [tagName]		# 查看标签的版本信息
```

### 打标签

```python
# 轻量标签是指向提交对象的引用（不推荐）
## 创建轻量标签不需要传递参数，直接指定标签名称即可。
git tag [tagName]-light		
# 附注标签则是仓库中的一个独立对象。（推荐）
## 创建附注标签时，参数a即annotated的缩写，指定标签类型，后附标签名。参数m指定标签说明，说明信息会保存在标签对象中。(很奇怪的是有一次忘记写 -a 也是可以添加成功的)
git tag -a [tagName] -m "0.1.2版本"

---

# 补打标签，也就是不必打在head上。
git log		# 获取commitID
git tag -a [tagName] [前七位commitID]
```

### 切换到标签

```python
git checkout [tagName]		# 切换到标签
```

### 删除标签

```python
git tag -d [tagName]		# 删除标签

# 删除远程标签
git push origin :refs/tags/[tagName]
git push origin -d tag [tagName]	# (Git > v1.7.0)
```

### 发布标签

- 通常的git push不会将标签对象提交到git服务器，我们需要进行显式的操作：

```python
git push origin [tagName]		# 单独发布
git push origin --tags			# 将本地所有标签一次性提交
```

# GitHub

## 概念相关

### 提取和拉取

在vs中的GitHub插件的 `同步`选项中，存在`提取`、`拉取`两个选择，都能起到获取最新版代码的作用。

- `提取`为`fetch`，`拉取`为`pull`。
    `提取/fetch`: 从远程获取最新版本文件到本地，不自动合并/merge，最新版本在“分支”选项中的“remotes/origin”文件夹下可以查看，可以选择将其合并到master分支上。
    
    `拉取/pull`: 从远程仓库拉取最新版本文件到本地，自动合并/merge。
    实际使用中，使用“提取/fetch”更安全，在merge之前可以看清楚更新情况再决定是否合并。

> 谨记：一个branch（分支）只有在被合并后才可以被删除。 

## 多人协作开发流程

### 远程仓库

- 将本地仓库推送到远程仓库

1. `git push 远程仓库地址 分支名称` # 最基本的推送方式

2. 为 远程仓库地址 取一个别名， 这样每次就不用复制 远程仓库地址了

`git remote add origin 远程仓库地址`    # 这样就将 远程仓库地址 取了一个别名 origin

> 取了别名后，推送就可以直接用这个命令了：`git push origin 分支名称`

> Win10系统下，第一次推送会提示输入账号密码，然后Win10会将账号密码进行保存，在之后的提交中就不需要再次输入了。存储位置：控制面板--凭据管理器--Windows凭据--github账号。

3. 更为简洁的提交方式（不是很推荐）

`git push -u origin master` # 添加 -u 参数后，git 会将提交方式默认为 origin master.

`git push`  # 直接输入默认提交即可，不是很推荐就是了。

---

- 克隆仓库

`git clone 远程仓库地址`

---

- 协同开发

1. 发出邀请：在 github 上找到项目的 Settings--Collaborators 填写合作者的 github ID，就会得到一个邀请链接，发送给合作者访问，同意后就可以协作开发了。

2. 跨团队协作：在 github 上应用一个项目时（你不是项目开发人员），发现了一些问题但是你修补了他，没有提交权限时，应该如何提出申请呢？这时就需要用到 fork 功能。

> fork 后就可以在自己的 github 里进行提交修改等操作了，进行修改后就可以向原作者提交申请了。

    （1）在 github 中点击 Pull requests -- New pull request -- Create pull request，可以在页面最下面看到代码的更新，并且可以在文本框中进行对话。
    
    （2）流程回顾：developer fork 仓库 -- developer clone 在本地修改 -- developer push origin master -- developer 发起 pull request -- author 审核 -- author merge.

---

- 拉取远程仓库中最新的版本

`git pull 远程仓库地址 分支名`  # 拉取属于 读 操作，因此不需要验证身份。

---

- 解决冲突

如果两个人修改了同一个文件的同一个地方，就会发生冲突。冲突需要人为解决。

发生冲突时，第二个推送的人是无法将本地文件推送到远程仓库的，因此需要先 pull 仓库，然后再解决冲突。

> 文件内冲突的讲解：

```python
<<<<<<< HEAD    # 冲突的开始
·······（代码） # 本地代码
=======         # 分隔线
·······（代码） # 远程代码
>>>>>>> 版本号  # 冲突的结束
```

> 解决冲突：就是将开始、分隔线、结束都删除，将两个代码进行整合再上传。

---

## git 忽略清单

将不需要被 git 管理的 文件/文件夹 名字添加到此文件中，git就会忽略这些文件。

> 在项目根目录创建 `.gitignore`

__.gitignore格式规范:__

1.所有空行或者以注释符号 ＃ 开头的行都会被 Git 忽略。

2.可以使用标准的 glob 模式匹配。

3.匹配模式最后跟反斜杠（/）说明要忽略的是目录。

4.要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（! ）取反。

> 所谓的 glob 模式是指 shell 所使用的简化了的正则表达式。星号（*）匹配零个或多个任
意字符； [abc] 匹配任何一个列在方括号中的字符（这个例子要么匹配一个 a，要么匹配一
个 b，要么匹配一个 c）；问号（?）只匹配一个任意字符；如果在方括号中使用短划线分
隔两个字符，表示所有在这两个字符范围内的都可以匹配（比如 [0-9] 表示匹配所有 0 到
9 的数字）。

__.gitignore范例:__

`# 说明`    # 此为注释 – 将被 Git 忽略

`build/`    # 忽略 build/ 目录下的所有文件

`/TODO`     # 仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO

`*.a`       # 忽略所有 .a 结尾的文件

`!lib.a`    # 但 lib.a 除外

`doc/*.txt` # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt

---

## ssh 相关

https 协议仓库地址，是需要账号密码进行验证的。

ssh 协议，可以通过秘钥实现免登录。

公钥和私钥必须匹配才可以通过验证。公钥相当于一个门锁，私钥相当于钥匙。公钥和私钥需要开发者使用命令生成，也就是两个文件：公钥放在 github 账户中，私钥保留在开发者电脑中。当开发者通过 ssh 协议向远程仓库推送内容时，公钥和私钥会进行配对，如果配对成功，就会推送成功。

### ssh密钥生成

- 首先可以确认一下本机是否已经生成了一个公钥。

```python
% cd ~/.ssh
% ls
id_rsa		id_rsa.pub	known_hosts
```

如果有`id_rsa` 和 `id_rsa.pub` （或者类似之类成对的文件）， 有 `.pub` 后缀的文件就是公钥，另一个文件就是密钥。

- 生成ssh

1. 在 git bash 中输入 `ssh-keygen`，回车，此时会要求输入一些参数，但是可以使用默认值，可以一直回车到底（参数的含义以后再研究）。
2. 秘钥生成后会生成两个文件，存放在 user/.ssh/ 目录中，目录中会有两个文件。`id_rsa` 就是私钥，需要保存在开发者电脑中；`id_rsa.pub` 是公钥，放在 github 服务器中； `rsa` 代表一种非对称加密方式（此处不深究）。
3. 复制 `id_rsa.pub` 中的内容，打开 github -- 账户头像 -- Settings -- SSH and GPG kyes -- New SSH key.(标题可以不填，但不能有中文)
4. 测试是否设置成功，输入 `ssh -T git@github.com` 如果看到 `Hi xxx!` 说明设置成功了；没有的话会提示你生成配置文件，输入 `yes` 即可。

### 修改git的remote url

- `git remote -v` 查看当前的 `remote url`

如果结果是以 `https://` 开头，说明此项目是使用 `https://` 协议进行访问的，这种协议某些时候会报一些莫名的错误，如果是 `git@github` 开头的则是git协议，即ssh。

- 在GitHub上找到ssh地址，使用以下命令来重置url。

`git remote set-url origin ssh-url`

​    如果没有添加过url地址可以使用：

​    `git remote add origin ssh-url`

- `git remote -v` 检查一下是否替换过来，然后就可以免登录管理仓库了。


# git 上有关 Linux 的一些操作

```python
touch 文件      # 创建一个文件
```

# git 问题汇总

## git clone 时遇到的问题

### OpenSSL SSL_read: Connection was reset, errno 10054 

执行 `git clone 项目地址` 后，出现的报错，以下是报错原文。

> fatal: unable to access 'https://github.com/项目地址': OpenSSL SSL_read: Connection was reset, errno 10054

- 首先，有可能是网络不稳定，连接超时导致的，如果多次尝试后依旧报错，可以执行以下命令：

```python
git config --global http.sslVerify "false"
```

- 然后再执行 `git clone 项目地址` 即可。

## 连接问题

### LibreSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443

梯子将配置信息写入了 `~/.gitconfig` 里面，使用以下命令即可：

```python
git config --global http.sslBackend "openssl" 
```

## ssh: connect to host github.com port 22: Connection timed out

- 前提

`C:\Users\userName\.ssh` 目录下是有公钥和秘钥文件的，没有的请去配钥匙，不然无法使用ssh加密。

- 缘由

```cpp
->git pull
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

->ssh -T git@github.com
ssh: connect to host github.com port 22: Connection timed out
```

- 解决方案

`C:\Users\userName\.ssh` 目录下创建一个文件 `config`，复制以下内容

```cpp
Host github.com
User yourEmail
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 443
```

里面需要改动内容只有`yourEmail`！

- 测试

```cpp
ssh -T git@github.com
```

