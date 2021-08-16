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

# 库环境配置

## OpenCV

- 我的VS是2019版，其他版本仅供参考。

### 下载

- 官网一般是最新版的，如果想下载老版的可以在国内镜像资源库找找，反正我感觉官网下载时快时慢。

  [OpenCV官网](https://opencv.org/)

### 安装

- 由于存在换电脑的可能性，我喜欢将cpp库安装在D盘根目录，这个因人而异。

  ![image-20210816161406043](https://i.loli.net/2021/08/16/PwLfIAhMFTByvJj.png)

  ![image-20210816161441929](https://i.loli.net/2021/08/16/mfT5Svr91sNoWFO.png)

- 下载后的样子

  ![image-20210816161537371](https://i.loli.net/2021/08/16/8lgwx7a3fkGtVnM.png)

### 配置

配置分为两个步骤，都很重要，极其重要。

1. 配置Windows环境

   我的环境是win10，不是win10的可供参考。

   - 配置系统变量

     是否有一股熟悉的味道；`此电脑 -- 右键 -- 属性 -- 高级系统属性 -- 环境变量 -- 系统变量 -- Path -- 双击进去 -- 新建`

     输入opencv的bin路径：`D:\cpplib\opencv\build\x64\vc15\bin`（我用的是vc15，你用啥就添加啥的bin路径）（记得点确定关闭）

   - 配置文件

     很多时候配置好系统变量、配置好IDE还是会报错说找不到 ***.dll，这是因为关键启动文件需要放到系统目录中。（可能电脑只会在这里面找文件吧~）

     将上述的bin目录下的`opencv_world453.dll`、`opencv_world453d.dll`、`opencv_videoio_ffmpeg453_64.dll`（文件名会跟着版本走，请自行对号入座）放入`C:\Windows\System32`路径下。

2. 配置VS2019环境

   目前VS2019环境属性是针对项目的，因此一个项目要这样来一次，所以保存着比较好，我自己也总是忘。

   进入：`项目 -- 属性`

   ![image-20210816164833819](https://i.loli.net/2021/08/16/O2Th3Gl8AXLJKNg.png)

   首先注意两个问题：配置是`Debug`还是`Release`，这里不要选所有配置要分开配置，因为两个需要用到的解析器是不一样的；平台这里其实无所谓，opencv只能在x64上面运行，选x64即可。

   以下操作注意是 **"添加、添加、还是···添加！"** ；多个就起新行。

   - VC++目录

     可执行文件目录：`D:\cppLib\opencv\build\x64\vc15\bin`

     包含目录：`D:\cppLib\opencv\build\include`；`D:\cppLib\opencv\build\include\opencv2`

     库目录：`D:\cppLib\opencv\build\x64\vc15\lib`

     ![image-20210816165403955](https://i.loli.net/2021/08/16/n9VGd6j4FOz1foM.png)

   - 链接器 -- 输入

     附加依赖项：如果是Debug：`opencv_world453d.lib`；如果是Release：`opencv_world453.lib`

     很好区分，最后面多个d的就是Debug文件。	

     ![image-20210816165950633](https://i.loli.net/2021/08/16/JPzLUWidMcpqFx7.png)

配置完毕。

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