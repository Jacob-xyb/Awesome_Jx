# Git 版本管理控制系统

- 常规命令一张图演示

![image](https://img-blog.csdnimg.cn/img_convert/b7c2d1149f813df1097f1888eb04e94f.png)

# Git 基本操作

## Git 工作流程

- 工作目录 —— 暂存区 —— Git仓库

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

### 提交步骤

1. `git init`           # 初始化仓库
2. `git status`         # 查看文件状态
3. `git add 文件列表`   # 追踪文件（提交到暂存区）
4. `git commit -m 提交信息` # 向仓库中提交代码
5. `git log`            # 查看提交记录

### 撤销步骤

1. 用暂存区中的文件覆盖工作目录中的文件：

`git checkout 文件名字`

2. 从暂存区中删除文件：

`git rm -- cached 文件`

3. 将 git 仓库中指定的更新记录恢复出来，并且覆盖暂存区和工作目录：

`git rest --hard commitID`

- 注意：如果将版本指针前置的话，指针后面的日志就会消失。

4. 删除 远程仓库 中的文件

`git rm -r --cached 文件`

## Git 分支

### 分支细分

1. 主分支（master）：第一次向 git 仓库中提交更新记录时自动产生的一个分支。
2. 开发分支（develop）：作为开发的分支，基于 master 分支创建。
3. 功能分支（feature）：作为开发具体功能的分支，基于开发分支创建。

### 分支命令

1. `git branch` # 查看分支（*为当前分支）
2. `git branch 分支名称`    # 创建分支（基于所在分支创建）
3. `git checkout 分支名称`  # 切换分支（切换分支之前要保持当前暂存区完全干净，不然会出现错误。）

    - 这是由于 git 的暂存区是所有分支共享的，因此，只要未提交(commit)的内容都会在所有分支上呈现。有时，我们还未完成当前分支的功能开发，但是又亟需在另一个分支上修改内容(如：修复一个 BUG)。
    
    - 一种方式是通过“git commit”(提交)，解决这个问题。但在正常使用中，我们应该在完成某个功能的开发后才提交一个版本，而不是频繁的提交。

    [这时，我们可以使用“git stash”(储藏)来解决这个问题。](https://zhuanlan.zhihu.com/p/347073892)
    
4. `git merge 来源分支` # 合并分支（将来源分支合并到当前分支）
5. `git branch -d 分支名称` # 删除分支（如果删除的分支没有被合并是不能删除的）

    - `git branch -D 分支名称`  # 强制删除分支
    
### 暂时保存更改

在 git 中，可以暂时提取分支上所有的改动并存储，让开发人员得到一个干净的工作副本，临时转向其他工作。

使用场景：分支临时切

>> `git stash` # 临时保存

>> `git stash pop` # 恢复保存

# GitHub

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

- git 忽略清单

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

- ssh 免登录

https 协议仓库地址，是需要账号密码进行验证的。

ssh 协议，可以通过秘钥实现免登录。

公钥和私钥必须匹配才可以通过验证。公钥相当于一个门锁，私钥相当于钥匙。公钥和私钥需要开发者使用命令生成，也就是两个文件：公钥放在 github 账户中，私钥保留在开发者电脑中。当开发者通过 ssh 协议向远程仓库推送内容时，公钥和私钥会进行配对，如果配对成功，就会推送成功。

> 具体操作步骤：

1. 在 git bash 中输入 `ssh-keygen`，回车，此时会要求输入一些参数，但是可以使用默认值，可以一直回车到底（参数的含义以后再研究）。
2. 秘钥生成后会生成两个文件，存放在 user/.ssh/ 目录中，目录中会有两个文件。`id_rsa` 就是私钥，需要保存在开发者电脑中；`id_rsa.pub` 是公钥，放在 github 服务器中； `rsa` 代表一种非对称加密方式（此处不深究）。
3. 复制 `id_rsa.pub` 中的内容，打开 github -- 账户头像 -- Settings -- SSH and GPG kyes -- New SSH key.(标题可以不填) 


# git 上有关 Linux 的一些操作

```python
touch 文件      # 创建一个文件
```

# git 问题汇总

## git clone 时遇到的问题

### OpenSSL SSL_read: Connection was reset, errno 10054 

执行 `git clone 项目地址` 后，出现的报错，一下是报错原文。

> fatal: unable to access 'https://github.com/项目地址': OpenSSL SSL_read: Connection was reset, errno 10054

- 首先，有可能是网络不稳定，连接超时导致的，如果多次尝试后依旧报错，可以执行以下命令：

```python
git config --global http.sslVerify "false"
```

- 然后再执行 `git clone 项目地址` 即可。