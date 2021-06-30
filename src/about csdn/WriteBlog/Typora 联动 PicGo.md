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