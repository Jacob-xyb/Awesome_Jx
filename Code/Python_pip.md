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

## Pytorch

- Mac安装教程

  打开 pytorch.org 官网，可以选择安装器，Python版本，CUDA 版本。

  例如 Mac Conda Python3.6 CUDA 9.0 的安装命令为：

  ```python
  conda install pytorch torchvision -c pytorch
  ```

  ![PyTorch  Mac 安装教程](http://pytorchchina.com/wp-content/uploads/2018/12/WechatIMG1313.jpeg)

  如果是更加常见的 pip 安装的命令则是：

  ```
  pip3 install torch torchvision
  ```