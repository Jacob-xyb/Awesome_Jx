# 遇到的问题

## VisualStudio 产生的.ipch文件可以删除吗？
最近初学C++的过程中发现，我好像写了写`hello world`结果项目文档就占用了我`200+M`内存，太可怕了吧，这让写python的我很是费解，结果发现`ipch`文件夹是罪恶之源，想删却不敢删，毕竟是小白，请教了下百度，记录一下解决办法。
### ipch是个啥？
其实后续编写代码过程中还会出现一个占用大内存的毒瘤，`*.sdf`文件。
这些文件是Visual Studio用来保存预编译的头文件 和Intellisense 用的，删除这些文件对于工程的开发完全没有影响。

### 解决方案
如果既想使用预编译的头文件和Intellisense，又不想看到这些无聊的文件应该这样办：
在Visual Studio里进入如下设置：进入`Tools > Options`，选择`Text Editor > C/C++ > Advanced`，然后找到`Fallback Location`。然后把`Always use Fallback Location`和`Do Not Warn if Fallback Location Used`设置成`True`就可以了。

英文不好的就直接看图吧：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210719172852146.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210719172923229.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDU2MDY5OA==,size_16,color_FFFFFF,t_70)

设置好后就可以将那些文件删除了，删除后运行暂时没有发现任何问题。