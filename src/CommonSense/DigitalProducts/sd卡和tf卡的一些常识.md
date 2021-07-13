# sd卡和tf卡的一些常识
SD卡即Secure Digital Memory Card，中文翻译为安全数码卡。

TF卡即T-Flash又称MicroSD，是一种记忆卡。后改称为TransFlash；而重新命名为MicroSD的原因是因为被SD协会（SDA）采立。另一些被SDA采立的记忆卡包括miniSD和SD卡。

# sd卡和tf卡的区别
## 百科
- 主体不同
sd卡：是一种基于半导体快闪记忆器的新一代记忆设备，由日本松下、东芝及美国SanDisk公司于1999年8月共同开发研制。
tf卡：是一种极细小的快闪储存器卡，由SanDisk公司发明创立。

- 技术不同
sd卡：内嵌的数字版权保护方案是按4C提出的可记录介质内容保护标准（CPRM）所制定。其核心是使用了Cryptomeria密码。
tf卡：采用SanDisk最新 NAND MLC 技术及控制器技术。

- 应用不同
sd卡：广泛地于便携式装置上使用，例如数码相机、平板电脑和多媒体播放器等。
tf卡：主要于手机使用，但因它拥有体积极小的优点，随着不断提升的容量，它慢慢开始于GPS设备、便携式音乐播放器和一些快闪存储器盘中使用。

## 转换关系
TF卡插入适配器（adapter）可以转换成SD卡，但SD卡一般无法转换成TF卡。

SD卡有写保护开关！

TF卡没有，但是TF卡可以通过卡套，转换成SD卡！

# 参数详解
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210713152416355.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDU2MDY5OA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210713160620929.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDU2MDY5OA==,size_16,color_FFFFFF,t_70)

- UHS
UHS的意思是“超高速（Ultra High Speed）”，“UHS速度等级”以最低写入速度区分MicroSD卡，例如UHS-I速度等级1具有最低10MB/s的写入速度，而UHS-I速度等级3具有最低30MB/s的写入速度。

- A1
A1是2016年11月份SD卡协会公布的一个新的体系标准——A1（APP Performance A1）。要获得App Performance Class 1（简称A1）的扩展卡要符合这些要求：
1500次随机读取IOPS，500次随机写入IOPS
10MB/s的顺序写入性能

- Class
Class是传输速度的意思(写入速度及读取速度)，有[Class2(2MB/sec)、Class4(4MB/sec)、Class6(6MB/sec)、Class10(10MB/sec)][最低速度]

> 内存卡Class表示含义     
> Class 0：包括低于Class 2和未标注Speed Class的情况；    
> Class 2：能满足观看普通MPEG4 MPEG2 的电影、SDTV、数码摄像机拍摄；   
> Class 4：可以流畅播放高清电视（HDTV），数码相机连拍等需求；   
> Class 6：满足单反相机连拍和专业设备的使用要求；    
>  class 10：满足更高速率要求的存储需要。
>  Class等级是按8KB每秒的换算    Class4 即8KB文件写入为4MB每秒，Class10 是8KB写入为10MB每秒，所以，一般Class几，8K文件的写入速度就是几MB每秒.