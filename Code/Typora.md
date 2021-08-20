# 设置

## 主题

### Typora如何自动生成标题序号

- __打开主题文件夹:__

  设置  ->  偏好设置  ->  打开主题文件夹
  
- __新建base.user.css__

  拷贝以下内容：
  
```python
#write {
    counter-reset: h1
}
 
h1 {
    counter-reset: h2
}
 
h2 {
    counter-reset: h3
}
 
h3 {
    counter-reset: h4
}
 
h4 {
    counter-reset: h5
}
 
h5 {
    counter-reset: h6
}
 
#write h1:before {
    counter-increment: h1;
    content: counter(h1) ". "
}
 
#write h2:before {
    counter-increment: h2;
    content: counter(h1) "." counter(h2) ". "
}
 
#write h3:before,
h3.md-focus.md-heading:before {
    counter-increment: h3;
    content: counter(h1) "." counter(h2) "." counter(h3) ". "
}
 
#write h4:before,
h4.md-focus.md-heading:before {
    counter-increment: h4;
    content: counter(h1) "." counter(h2) "." counter(h3) "." counter(h4) ". "
}
 
#write h5:before,
h5.md-focus.md-heading:before {
    counter-increment: h5;
    content: counter(h1) "." counter(h2) "." counter(h3) "." counter(h4) "." counter(h5) ". "
}
 
#write h6:before,
h6.md-focus.md-heading:before {
    counter-increment: h6;
    content: counter(h1) "." counter(h2) "." counter(h3) "." counter(h4) "." counter(h5) "." counter(h6) "."
}
 
#write > h3.md-focus:before,
#write > h4.md-focus:before,
#write > h5.md-focus:before,
#write > h6.md-focus:before,
h3.md-focus:before,
h4.md-focus:before,
h5.md-focus:before,
h6.md-focus:before {
    color: inherit;
    border: inherit;
    border-radius: inherit;
    position: inherit;
    left: initial;
    float: none;
    top: initial;
    font-size: inherit;
    padding-left: inherit;
    padding-right: inherit;
    vertical-align: inherit;
    font-weight: inherit;
    line-height: inherit;
}
```

- **重启Typora**

**tips:** 目录功能没有同步标题名称。

---

- __为了与已有主题区分，也可以：__

新建立主题(copy 已有主题文件夹和css)  ->  并加入上面的css。  // 主题名称不能包含 `大写字母`，可以包含中文。

[Typora添加主题](https://www.cnblogs.com/superdrew/p/12821051.html)

[Typora主题下载](https://theme.typora.io/)

# Typora 联动 Picgo

## PicGo SM.MS图床设置

- 之前一直白嫖PicGo的SM.MS图床，最近图片总是上传失败，百度一下后发现可谓是众说纷纭。但是矛头都是指向了 `没有对PicGO进行配置`，首先声明这个结论是对的，PicGo 不进行配置的话可能会用的很难受。(新版可以直接Token登陆，不要装插件，会安装很多多余的软件。)

- 到 `SM.MS` 的官网注册一下，直接上链接：[SM.MS](https://sm.ms/)

![image-20210629183029477](https://i.loli.net/2021/06/29/NRzrjEs2v9UonpF.png)

![image-20210629183300068](https://i.loli.net/2021/06/29/lLJqhYjmraoKcA8.png)

- 然后在 `Dashboard` 中找到 `API Token`，生成 `Token` 填入`Picgo`即可。

![image-20210629183554302](https://i.loli.net/2021/06/29/3zNeDcu2UMgPhKO.png)

- 在主页可以看到，一个账户是有5个G白嫖的啊，N个账户就是 `N*5个G` 白嫖的啊，还可以找到自己的历史照片。

![image-20210629183816561](https://i.loli.net/2021/06/29/QZXuGeI9VzRD2WK.png)


### 更新日志

- **20210630**

SM.MS图床 貌似并不是很稳定，早上发现有部分图片加载不出来，还以为是免费的所以会被删图，但是下午又加载出来了，实属弄不懂，所以还是推荐用github存图吧，比较稳定可靠，下次再出github设置教程。

## Typora 联动 PicGo

之前总是手动在 `PicGo`上传图片，然后用 MarkDown 格式来引用图片，大量使用图片时效率很低，无意中发现 `Typora` 是可以与 `PicGo`联动的，实现起来也比较简单。

- 设置

文件  -->  设置  -->  图像

![image-20210630145846775](https://i.loli.net/2021/06/30/DN3MFnAI6zkpiyR.png)

按照图片红框进行设置，然后点击验证图片上传选项就可以玩耍了。

**为了防止图片失效，大致讲解设置内容：**

```python
# 插入图片时...
上传图片  --  对本地位置的图片应用上述规则
// 这样设置就是只为了可以截图直接上传

# 上传服务
PicGo(app)  --  找到PicGo.exe所在路径
// 然后验证图片看是否可用
```

- 缓存

这样设置的话会在 `Typora` 内进行缓存，缓存文件夹：`C:\Users\useID\AppData\Roaming\Typora\typora-user-images`

# Math

