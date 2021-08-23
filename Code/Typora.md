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

## 基本语法

### 展现形式

- 在正文中的`LaTeX`公式用`$...$`定义行内公式，`$$...$$`单独居中显示

### 希腊字母

| 显示 |   命令   | 显示 |  命令  |
| :--: | :------: | :--: | :----: |
|  α   |  \alpha  |  β   | \beta  |
|  γ   |  \gamma  |  δ   | \delta |
|  ε   | \epsilon |  ζ   | \zeta  |
|  η   |   \eta   |  θ   | \theta |
|  ι   |  \iota   |  κ   | \kappa |
|  λ   | \lambda  |  μ   |  \mu   |
|  ν   |   \nu    |  ξ   |  \xi   |
|  π   |   \pi    |  ρ   |  \rho  |
|  σ   |  \sigma  |  τ   |  \tau  |
|  υ   | \upsilon |  φ   |  \phi  |
|  χ   |   \chi   |  ψ   |  \psi  |
|  ω   |  \omega  |      |        |

- 示例：

  `$\alpha$`： $\alpha$

- 需要大写希腊字母时，首字母大写即可

  `$\Alpha$`：$\Alpha$

### 常见符号

| 显示 | 命令 | 显示 | 命令 |
| :--: | :-----: | :--: | :--: |
| ${x}\cdot{y}$  | {x}\cdot{y} |    ${x}*{y}$    |    {x}*{y}    |
| ${x}\colon{y}$ | {x}\colon{y} | ${x}\times{y}$  | {x}\times{y}  |
|     ${x}.{y}$     |     {x}.{y}     |    ${x},{y}$    |    {x},{y}    |
| ${x}\pm{y}$ | {x}\pm{y} | ${x}\over{y}$ | {x}\over{y} |
|     $\vdots$      |     \vdots      |    $\ddots$     |    \ddots     |
| $\dot{x}$ | \dot{x} | $\ddot{x}$ | \ddot{x} |
| $\breve{x}$ | \breve{x} | $\widehat{xxx}$ | \widehat{xxx} |
| $\acute{x}$ | \acute{x} | $\check{x}$ | \check{x} |
|  $\grave{x}$   |  \grave{x}   |   $\tilde{x}$   |   \tilde{x}   |
| $\neq$ | \neq | $\bar{x}$ | \bar{x} |
| $\hat{x}$ | \hat{x} | $\dotsm$ | \dotsm |
| $\vec{x}$ | \vec{x} |    $\dotso$     |    \dotso     |
| $\widetilde{xxx}$ | \widetilde{xxx} | $\dddot{x}$ | \dddot{x} |
| $\backslash$ | \backslash | $\bracevert$ | \bracevert |
| $\smallsetminus$ | \smallsetminus |  $\arrowvert$   |  \arrowvert   |
| $\lbrace$ | \lbrace |    $\lVert$     |    \lVert     |
| $\rbrace$ | \rbrace | $\rVert$ | \rVert |
| $\lgroup$ | \lgroup | $\lvert$ | \lvert |
| $\rgroup$ | \rgroup |    $\rvert$     |    \rvert     |
| $\langle$ | \langle | $\lfloor$ | \lfloor |
| $\rangle$ | \rangle | $\rfloor$ | \rfloor |
| $\lmoustache$ | \lmoustache | $\lceil$ | \lceil |
| $\rmoustache$ | \rmoustache | $\rceil$ | \rcei |
| ${x}\quad{y}$ | {x}\quad{y} |  |  |

### 集合

|       显示       |      命令      |      显示       |     命令      |
| :--------------: | :------------: | :-------------: | :-----------: |
|      $\in$       |      \in       |    $\notin$     |    \notin     |
|  $\nsubseteqq$   |  \nsubseteqq   |    $\subset$    |    \subset    |
|   $\emptyset$    |   \emptyset    |    $\supset$    |    \supset    |
|     $\nabla$     |     \nabla     |   $\subseteq$   |   \subseteq   |
|  $\nsubseteqq$   |  \nsubseteqq   |  $\nsubseteq$   |  \nsubseteq   |
|  $\nsupseteqq$   |  \nsupseteqq   |  $\nsupseteq$   |  \nsupseteq   |
|  $\subsetneqq$   |  \subsetneqq   |  $\subsetneq$   |  \subsetneq   |
|  $\supsetneqq$   |  \supsetneqq   |  $\supsetneq$   |  \supsetneq   |
| $\varsubsetneqq$ | \varsubsetneqq | $\varsubsetneq$ | \varsubsetneq |
| $\varsupsetneqq$ | \varsupsetneqq | $\varsupsetneq$ | \varsupsetneq |
|    $\bigcap$     |    \bigcap     |    $\bigvee$    |    \bigvee    |
|    $\bigcup$     |    \bigcup     |   $\bigwedge$   |   \bigwedge   |
|   $\biguplus$    |   \biguplus    |   $\bigsqcup$   |   \bigsqcup   |
|    $\Subset$     |    \Subset     |    $\Supset$    |    \Supset    |
|   $\subseteqq$   |   \subseteqq   |  $\supseteqq$   |  \supseteqq   |
|   $\sqsubset$    |   \sqsubset    |   $\sqsupset$   |   \sqsupset   |
|    $\forall$     |    \forall     |    $\exists$    |    \exists    |

### 函数公式表

- 没有列举的函数可以类推

|  显示  | 命令 |    显示     |   命令    |
| :----: | :--: | :---------: | :-------: |
| $\sin$ | \sin | $\sin^{-1}$ | \sin^{-1} |
| $\cos$ | \cos​ | $\cos^{-1}$ | \cos^{-1} |
| $\tan$ | \tan | $\tan^{-1}$ | \tan^{-1} |
| $\det$ | \det |   $\dim$    |   \dim    |
| $\inf$ | \inf |   $\arg$    |   \arg    |
| $\log$ | \log |    $\ln$    |    \ln    |

### 箭头

- 太多了。。不定期更新常用的吧

|       显示        |      命令       |        显示        |       命令       |
| :---------------: | :-------------: | :----------------: | :--------------: |
| $\Leftrightarrow$ | \Leftrightarrow | $\nLeftrightarrow$ | \nLeftrightarrow |
|   $\Rightarrow$   |   \Rightarrow   |    $\Leftarrow$    |    \Leftarrow    |
| $\leftrightarrow$ | \leftrightarrow | $\nleftrightarrow$ | \nleftrightarrow |

## 修饰

### 上下标

上标：`^` 	下标：`_`

举例：`$C_n^2$`：$C_n^2$

### 矢量

- 单个字母矢量：`\vec`即可（vector）

  `$\vec{i}$` or `$\vec i$` ：$\vec{i}$ 

- 多个字母就不要用空格了

  `$\vec{ij}$` : $\vec{ij}$ 		`$\vec ij$` ： $\vec ij$

- 比较复杂的左右箭头

  `$\overrightarrow x$ ` : $\overrightarrow x$ 	`$\overrightarrow {x}$` : $\overrightarrow {x}$

  `$\overleftarrow x$` : $\overleftarrow x$  `$\overleftarrow {x}$  ` : $\overleftarrow {x}$  

### 字体

- Jacob

|       显示       |      命令      | 字体 |
| :--------------: | :------------: | :--: |
| $\mathbf{Jacob}$ | \mathbf{Jacob} | 加粗 |
| $\mathit{Jacob}$ | \mathit{Jacob} | 斜体 |

## 数学公式表

|             显示              |            命令             | 类型 |
| :---------------------------: | :-------------------------: | :--: |
|        $\frac{n}{n-1}$        |        \frac{n}{n-1}        | 分式 |
|        $\sqrt[n]{ab}$         |        \sqrt[n]{ab}         | 根式 |
|          $\sqrt{ab}$          |          \sqrt{ab}​          | 根式 |
|         $\log_{a}{b}$         |         \log_{a}{b}         | 对数 |
|           $\lg{ab}$           |           \lg{ab}           | 对数 |
|            $\int$             |            \int             | 积分 |
|        $\int_{a}^{b}$         |        \int_{a}^{b}         | 积分 |
| $\frac{\text{d}x}{\text{d}y}$ | \frac{\text{d}x}{\text{d}y} | 微分 |
|   $\lim_{a \rightarrow b}$    |   \lim_{a \rightarrow b}    | 极限 |

## 常见模板

### 二次方程求解

   ```cpp
\mathbf{a*x^2+b*x+c}\\
x=\frac{{-b}\pm{\sqrt{b^2-4ac}}}{2a}\\
x={{-b\pm\sqrt{b^2-4ac}}\over{2a}}
   ```


$$
\mathbf{a*x^2+b*x+c}\\
x=\frac{{-b}\pm{\sqrt{b^2-4ac}}}{2a}\\
x={{-b\pm\sqrt{b^2-4ac}}\over{2a}}
$$

### 矩阵

- 基本示例

```cpp
\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&1
\end{bmatrix}
```


$$
\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&1
\end{bmatrix}
$$

- 基本语法

  在起始和结束位置可以调整矩阵边框

```cpp
matrix  ：无边框
pmatrix ：小括号边框
bmatrix ：中括号边框
Bmatrix ：大括号边框
vmatrix ：单竖线边框
Vmatrix ：双竖线边框
```

- 省略元素矩阵示例

```cpp
\begin{bmatrix}
{a_{11}}&{a_{12}}&{\cdots}&{a_{1n}}\\
{a_{21}}&{a_{22}}&{\cdots}&{a_{2n}}\\
{\vdots}&{\vdots}&{\ddots}&{\vdots}\\
{a_{m1}}&{a_{m2}}&{\cdots}&{a_{mn}}\\
\end{bmatrix}
```

$$
\begin{bmatrix}
{a_{11}}&{a_{12}}&{\cdots}&{a_{1n}}\\
{a_{21}}&{a_{22}}&{\cdots}&{a_{2n}}\\
{\vdots}&{\vdots}&{\ddots}&{\vdots}\\
{a_{m1}}&{a_{m2}}&{\cdots}&{a_{mn}}\\
\end{bmatrix}
$$

### 方程组

- 比较复杂，记住模板即可
- equation环境

```cpp
\begin{equation}
% \begin{equation*} 加'*'去掉公式编号
\left\{
\begin{aligned}     %请使用'aligned'或'align*'
a_1x+b_1y+c_1z &= d_1 \\     %加'&'指定对齐位置
a_2x+b_2y+c_2z &= d_2 \\
a_3x+b_3y+c_3z &= d_3 \\
\end{aligned}
\right.
\end{equation}
% \end{equation*}   加'*'去掉公式编号

% 注意：在 markdown 环境下，某些特殊字符，如'\', '*'等，会首先被 markdown 语法转义，然后再被 Latex 转义。
% 因此有时候 '\{'需要写作'\\{'，'*'需要写作'\*'，'\\'需要写作'\\\\'等，视不同的解释环境而定
```


$$
\begin{equation}
% \begin{equation*} 加'*'去掉公式编号
\left\{
\begin{aligned}     %请使用'aligned'或'align*'
a_1x+b_1y+c_1z &= d_1 \\     %加'&'指定对齐位置
a_2x+b_2y+c_2z &= d_2 \\
a_3x+b_3y+c_3z &= d_3 \\
\end{aligned}
\right.
\end{equation}
% \end{equation*}   加'*'去掉公式编号
% 注意：在 markdown 环境下，某些特殊字符，如'\', '*'等，会首先被 markdown 语法转义，然后再被 Latex 转义。
% 因此有时候 '\{'需要写作'\\{'，'*'需要写作'\*'，'\\'需要写作'\\\\'等，视不同的解释环境而定
$$

- cases环境

```cpp
\begin{cases}
&a_1x+b_1y+c_1z&=&d_1\\
&a_2x+b_2y+c_2z&=&d_2\\
&a_3x+b_3y+c_3z&=&d_3\\
\end{cases}
```

$$
\begin{cases}
&a_1x+b_1y+c_1z&=&d_1\\
&a_2x+b_2y+c_2z&=&d_2\\
&a_3x+b_3y+c_3z&=&d_3\\
\end{cases}
$$

