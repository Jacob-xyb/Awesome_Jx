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

__tips:__目录功能没有同步标题名称。

---

- __为了与已有主题区分，也可以：__

新建立主题(copy 已有主题文件夹和css)  ->  并加入上面的css。  // 主题名称不能包含 `大写字母`，可以包含中文。

[Typora添加主题](https://www.cnblogs.com/superdrew/p/12821051.html)

[Typora主题下载](https://theme.typora.io/)

# Typora 联动 Picgo

## Picgo SM床图设置

### 纯吐槽

![image-20210629181515844](https://i.loli.net/2021/06/29/5BIDRk7Gxm8pKq1.png)

[Node.js下载地址[坑啊！！千万不要下载，摆上来就是为了吐槽吐槽]](https://nodejs.org/en/) 

- 万恶之源的开始！

![image-20210629181841699](C:\Users\94978\AppData\Roaming\Typora\typora-user-images\image-20210629181841699.png)

- 就很离谱的调用我的权限开始乱嗨？

![20210629180943.png](https://i.loli.net/2021/06/29/n4vQKipCyjl7sSr.png)

- 我要被这个 `Node.js` 搞疯了，我处女座！

![image-20210629181656712](https://i.loli.net/2021/06/29/AXkSo6cwfJp4eZF.png)

- 全部 say byebye !

![image-20210629182249216](https://i.loli.net/2021/06/29/xMtJb5pTljvB9cY.png)

![image-20210629182138166](https://i.loli.net/2021/06/29/S2mKXulV1LY6rza.png)

![image-20210629182507035](https://i.loli.net/2021/06/29/J73hcgXSMTLRpdq.png)

### 正儿八经的解决方案

- 用自己的账户上传图片会稳定非常多，可以看到SM.MS需要一个Token，直接去SM的官网注册一下就好了，直接上链接：[SM.MS](https://sm.ms/)

![image-20210629183029477](https://i.loli.net/2021/06/29/NRzrjEs2v9UonpF.png)

![image-20210629183300068](https://i.loli.net/2021/06/29/lLJqhYjmraoKcA8.png)

- 然后在 `Dashboard` 中找到 `API Token`，生成 `Token` 填入`Picgo`即可。

![image-20210629183554302](https://i.loli.net/2021/06/29/3zNeDcu2UMgPhKO.png)

- 在主页可以看到啊，一个账户是有5个G白嫖的啊，N个账户就是 `N*5个G` 白嫖的啊，还可以找到自己的历史照片，是不是很赞呢，那就点个赞吧。  ! \ ^.^ / !

![image-20210629183816561](https://i.loli.net/2021/06/29/QZXuGeI9VzRD2WK.png)