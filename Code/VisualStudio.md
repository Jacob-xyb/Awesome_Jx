# 个人设置

## 简单设置

### 调试停止时自动关闭控制台

- `shift +F5` 调试停止了，但是控制台并没有自动退出

- 设置： `工具 -- 选项 -- 调试 -- 常规 -- 调试停止时自动关闭控制台`；设置后一定要点`确定`！

  ![image-20210727105426703](https://i.loli.net/2021/07/27/tBRhG52mVx6oXs9.png)

### 关掉单击预览文件

- 设置：`工具 -- 选项 -- 环境 -- 选项卡和窗口 `

![image-20210807141554793](https://i.loli.net/2021/08/07/ImgysAaxw1MVG7r.png)

### 新开选项卡排序

- 设置：`工具 -- 选项 -- 环境 -- 选项卡和窗口 --  文档选项卡 -- 将新选项卡插入右侧`

![image-20210807142018932](https://i.loli.net/2021/08/07/N4AB89lTinStOUz.png)

### 略缩图滚动条

- 设置：`工具 -- 选项 -- 所有语言 -- 滚动条 -- 开启略缩图模式`

![image-20210807142509576](https://i.loli.net/2021/08/07/b89gRFJ1fkvEpOw.png)

### 独立显示固定选项卡

- 设置：`工具 -- 选项 -- 环境 -- 选项卡和窗口 -- 独立显示固定选项卡`

# 插件

## 编辑器外观插件

### Viasfora

- 彩虹括号插件

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

## 默认编码为utf-8

### 单个编码 -- 高级选项卡

 Visual Studio 设置默认编码格式在“高级保存选项”窗口中，可通过“文件”菜单打开；但有时“文件”菜单没有显示“高级保存选项”，需要把它显示出来。

`工具 -- 自定义 -- 命令 -- 菜单栏（下拉选择文件） -- 添加命令 `；跳出的方框中`文件 -- 高级保存选项 -- 确定并保存`。

![](https://img-blog.csdnimg.cn/20200425151309403.png)

![](https://img-blog.csdnimg.cn/2020042515255887.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxODY4MTA4,size_16,color_FFFFFF,t_70)

然后在`文件`中就可以通过`高级保存选项`进行保存了。

## 全局默认 -- Format On Save

- 下载

  `扩展 -- 管理扩展 -- 联机 -- 下载插件：Format On Save`；安装好后可能要重启一下。

- 检查

  `扩展 -- 管理扩展 -- 已安装 `出现了这个插件代表安装好了。

- 使用

  `工具 -- 选项 -- Format On Save`

  我啥都没有改，但是网上很多大佬都说把`Line Break`改为`Windows`；不明白改了有什么改变，因为我是多系统，就感觉没有改的必要。

- 注意

  VS只能保存为 `UTF-8 with BOM` 所以用QT之类的报错的话记得留意一下。