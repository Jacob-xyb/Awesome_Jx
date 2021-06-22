# Python大型库安装

## TensorFlow

一般安装：

`pip install tensorflow`

`pip install tensorflow-gpu`

> 一般方法很慢很慢，因为需要翻墙，因此换用国内源比较快。

`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ tensorflow `

TensorFlow 2.4.0 已经适配 python 3.8 

`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple/ tensorflow==2.4.0`

- 更多国内源：

```python
阿里云 
http://mirrors.aliyun.com/pypi/simple/

中国科技大学 
https://pypi.mirrors.ustc.edu.cn/simple/

豆瓣(douban) 
http://pypi.douban.com/simple/

清华大学 
https://pypi.tuna.tsinghua.edu.cn/simple/

中国科学技术大学 
http://pypi.mirrors.ustc.edu.cn/simple/
```

---

tips: TensorFlow 2.4.0 目前只有清华源才有镜像（但是容易卡住）