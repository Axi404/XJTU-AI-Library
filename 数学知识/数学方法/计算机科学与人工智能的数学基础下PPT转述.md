本教程可用于 PPT 的复习，包括 PPT 中提及的全部知识点，另精简版教程见 [[计算机科学与人工智能的数学基础下复习大纲]]。
# 引言

## 数值算法概论

某些数学问题在理论上没有解决的方法，解决此类问题必须用数值计算。

某些数学问题在理论上有解决的方法，但是计算量过大，必须寻找新的行之有效的方法。

## 向量和矩阵范数

#### 定义 1.1 

称 $n$ 维实空间 $x \in \mathbf{R}^{n}$ 上的一个函数 $\|\cdot\|$ 为范数，若满足：

1) 非负性: $\|x\| \geq 0,\|x\|=0$ 当且仅当 $x=0$,
2) 齐次性: $\|\alpha x\|=|\alpha|\|x\|, \alpha \in \mathbf{R}$,
3) 三角不等式: $\|x+y\| \leq\|x\|+\|y\|, \forall x, y$ 

$$\|x\|_{p}=\left (\sum_{i=1}^{n}\left|x_{i}\right|^{p}\right)^{\frac{1}{p}}, x=\left (x_{1}, x_{2}, \ldots, x_{n}\right)^{\mathrm{T}} \in \mathbf{R}^{n}$$

几种最简单的情形：

- $1$ -范数: $\|x\|_{1}=\left|x_{1}\right|+\left|x_{2}\right|+\cdots+\left|x_{n}\right|$ 
- $2$ -范数: $\|x\|_{2}=\left (\left|x_{1}\right|^{2}+\left|x_{2}\right|^{2}+\cdots+\left|x_{n}\right|^{2}\right)^{1 / 2}$
- $\infty$ -范数: $\|x\|_{\infty}=\max \left (\left|x_{1}\right|,\left|x_{2}\right|, \cdots,\left|x_{n}\right|\right)$

### 定理 1.1：

在 $n$ 维实向量 $x \in \mathbf{R}^{n}$ 的一切范数都是等价的，即对 $\mathbf{R}^{n}$ 中的任何两种范数 $\|x\|_{\alpha}$ 与 $\|x\|_{\beta}$ 存在两个正数 $c_{1}, c_{2}>0$，使得对任意的向量 $x$，不等式：

$$c_{1}\|x\|_{\beta} \leq\|x\|_{\alpha} \leq c_{2}\|x\|_{\beta}$$


成立。

对于向量的三种常用的范数，有如下的等价关系：

$$\begin{array}{c}
\|x\|_{2} \leq\|x\|_{1} \leq \sqrt{n}\|x\|_{2} \\
\|x\|_{\infty} \leq\|x\|_{1} \leq n\|x\|_{\infty} \\
\|x\|_{\infty} \leq\|x\|_{2} \leq \sqrt{n}\|x\|_{\infty}
\end{array}$$

### 定义 1.2：

设有向量序列 $\left\{x^{(k)} \in R^{n} \mid x^{(k)}=\left (x_{1}^{(k)}, x_{2}^{(k)}, \cdots, x_{n}^{(k)}\right)^{T}\right\}$，若

$$\lim _{k \rightarrow \infty} x_{i}{ }^{(k)}=x_{i}, \quad i=1,2, \cdots, n$$

则称序列 $\left\{x^{(k)}\right\}$ 收玫于向量 $x=\left (x_{1}, x_{2}, \cdots x_{n}\right)^{T}$。

### 定理 1.2：

在空间 $R^{n}$ 中，序列 $\left\{x^{(k)}\right\}$ 收玫于向量 $x$ 的充要条件是存在范数 $\|\cdot\|$ 使得 $\lim _{k \rightarrow \infty}\left\|x^{(k)}-x\right\|=0$。

### 向量范数的其他性质

设有映射 $\emptyset: D \subset \mathbf{R}^{n} \rightarrow \mathbf{R}^{n}$。在后面的章节，我们常常需要判断非线性方程 :

$$X=\emptyset (x), x \in D \subset \mathbf{R}^{n}$$

的解存在唯一性。为此，作为向量范数的一个应用，我们引入不动点原理。方程中的解也称为映射 $\emptyset$ 的不动点，其存在性往往可通过压缩性保障。

### 定义 1.3

设存在向量空间 $\mathbf{R}^{n}$ 中的范数 $\|\cdot\|$ 及常数 $q \in[0,1)$，使得映射 $\emptyset: D \subset \mathbf{R}^{n} \rightarrow \mathbf{R}^{n}$ 在集 $D_{0} \subset D$ 上满足：

$$\|\emptyset (x)-\emptyset (y)\| \leq q\|x-y\|, \forall x, y \in D_{0}$$

则称 $\emptyset$ 为集 $D_{0} \subset D$ 上的具有压缩系数 $q$ 的压缩映射。

### 定理 1.3 

Banach (巴拿赫)压缩映射原理

设 $\emptyset: D \subset \mathbf{R}^{n} \rightarrow \mathbf{R}^{n}$ 是闭集 $D_{0} \subset \mathrm{D}$ 上的压缩映射，且 $\varnothing\left (D_{0}\right) \subset D_{0}$，则 $\emptyset$ 于 $D_{0}$ 上有唯一不动点 $x^{*}$。

### 定义 1.4

称 $n$ 维实空间 $A \in \mathrm{R}^{n \times n}$ 上的一个函数 $\|\cdot\|$ 为范数，若满足：

1) 非负性: $\|\boldsymbol{A}\| \geq 0,\|\boldsymbol{A}\|=0$ 当且仅当 $\boldsymbol{A}=0$，
2) 齐次性: $\|\alpha \boldsymbol{A}\|=|\alpha|\|\boldsymbol{A}\|, \alpha \in \mathbf{R}$，
3) 三角不等式: $\|\boldsymbol{A}+\boldsymbol{B}\| \leq\|\boldsymbol{A}\|+\|\boldsymbol{B}\|, \forall \boldsymbol{A}, \boldsymbol{B} \in \mathrm{R}^{n \times n}$，
4) 矩阵乘法不等式: $\|\boldsymbol{A} \cdot \boldsymbol{B}\| \leq\|\boldsymbol{A}\| \cdot\|\boldsymbol{B}\|, \forall \boldsymbol{A}, \boldsymbol{B} \in \mathrm{R}^{n \times n}$。

$$\|\boldsymbol{A}\|=\sum_{i=1}^{n} \sum_{j=1}^{n}\left|a_{i j}\right|, \boldsymbol{A}=\left (a_{i j}\right) \in \mathbf{R}^{n \times n}$$

几种最简单的情形 :

矩阵 $\boldsymbol{A}$ 的行范数: $\|\boldsymbol{A}\|_{\infty}=\max _{1 \leq i \leq n} \sum_{j=1}^{n}\left|a_{i j}\right|$
矩阵 $\boldsymbol{A}$ 的列范数: $\|\boldsymbol{A}\|_{1}=\max _{1 \leq j \leq n} \sum_{i=1}^{n}\left|a_{i j}\right|$
矩阵 $\boldsymbol{A}$ 的欧几里得范数: $\|\boldsymbol{A}\|_{2}=\sqrt{\lambda_{\text {max }}\left (\boldsymbol{A}^{\mathrm{T}} \boldsymbol{A}\right)}$

$\|\boldsymbol{A} x\|_{p} \leq\|\boldsymbol{A}\|_{p} \cdot\|x\|_{p}$ 或 $\frac{\|\boldsymbol{A} x\|_{p}}{\|x\|_{p}} \leq\|\boldsymbol{A}\|_{p} \quad (p=1,2, \infty)$

### 定义 1.5

给定一种向量范数 $\|x\|_{p}(p=1,2, \infty)$，相应的定义了矩阵的一个非负函数 $f (A)=\|\boldsymbol{A}\|_{p}$，若有

$$\|\boldsymbol{A}\|_{p}=\max _{x \neq 0} \frac{\|\boldsymbol{A} x\|_{p}}{\|x\|_{p}}=\max _{\|x\|_{p}=1}\|\boldsymbol{A} x\|_{p}$$

则称 $\|\boldsymbol{A}\|_{p}$ 为向量范数导出的矩阵范数，也称 $\|\boldsymbol{A}\|_{p}$ 为算子范数。

## 误差

误差是人们用来描述数值计算中近似解的精确程度，是科学计算中的一个十分重要的概念。

### 分类

- 截断误差（truncation error）：在数值运算中运用近似方法表示准确数值运算或数量而引起的，也叫方法误差。
- 舍入误差（round-off error）：由于计算机字长的限制而产生的误差。
- 不与数值方法本身直接相关的误差
	- 模型误差：数学模型的解与实际问题的解之间出现的误差。 
	- 测量误差：在测量具体数据时产生的误差。

### 定义 1.6 

设 $x^{*}$ 为某测量的精确值， $\tilde{x}$ 是它的一个近似值，则称 $E (\tilde{x})=x^{*}-\tilde{x}$ 为近似值 $\tilde{x}$ 的绝对误差，简称误差。

若存在一个正数 $\delta$，使得 $E (\tilde{x})=\left|x^{*}-\tilde{x}\right| \leq \delta$，则称 $\delta$ 为近似值 $\tilde{x}$ 的绝对误差极限。

- 绝对误差可能取正，也可能取负
- 绝对误差的绝对值越小越具有参考价值
- 绝对误差并不能很好地表示近似值的精确度

### 定义 1.7

设 $x^{*}$ 为某测量的精确值， $\tilde{x}$ 是它的一个近似值，则称 $E_{r}(\tilde{x})=\frac{x^{*}-\tilde{x}}{x^{*}} \times 100 \%\left (x^{*} \neq 0\right)$ 为 $\tilde{x}$  的相对误差。

若存在一个正数 $\delta_{r}$，使得 $\left|E_{r}(\tilde{x})\right|=\left|\frac{x^{*}-\tilde{x}}{x^{*}}\right| \leq \delta_{r}$，则称 $\delta_{r}$ 为 $\tilde{x}$ 的相对误差极限。

- 相对误差是一个无名数，没有量纲。
- 相对误差比绝对误差更能反映出误差的特性。

### 定义 1.8

如果近似值 $\tilde{x}$ 的误差不超过某位的半个单位，若该位数字到 $\tilde{x}$ 的第一位非零数字共有 $n$ 位，那么这 $n$ 位数字称为 $\tilde{x}$ 的有效数字。

### 定义 1.9

设 $\tilde{x}$ 是 $x^*$ 的一个近似值，写成规格化形式：

$$\tilde{x}= \pm 10^{k} \times 0 . a_{1} a_{2} \cdots a_{n} \cdots$$

式中 $a_{i}(i=1,2, \cdots)$  是 $0 \sim 9$ 之间的整数，且 $a_{1} \neq 0$，$k$ 为整数。如果 $\left|x^{*}-\tilde{x}\right| \leq \frac{1}{2} \times 10^{k-n}$，则称 $\tilde{x}$ 是 $x^{*}$ 具有 $n$ 位有效数字的近似值。

### 定理 1.5

1) 若 $\tilde{x}$ 有 $n$ 位有效数字，则  $\left|\frac{x^{*}-\tilde{x}}{\tilde{x}}\right| \leq \frac{1}{2 a_{1}} \times 10^{1-n}$ .
2) 若 $\left|\frac{x^{*}-\tilde{x}}{\tilde{x}}\right| \leq \frac{1}{2\left (a_{1}+1\right)} \times 10^{1-n}$，则 $\tilde{x}$ 至少具有 $n$ 位有效数字。

$f\left (x^{*}\right)$ 的近似函数 $f (\tilde{x})$ 的误差限和相对误差限分别有如下估计式：

$$\left\{\begin{array}{c}
\delta f (\tilde{x}) \leq\left|f^{\prime}(\tilde{x})\right| \cdot \delta (\tilde{x}) \\
\delta_{r} f (\tilde{x})=\left|\frac{\delta f (\tilde{x})}{f (\tilde{x})}\right| \leq\left|\frac{f^{\prime}(\tilde{x})}{f (\tilde{x})}\right| \cdot \delta (\tilde{x})
\end{array}\right.$$

式中，假设 $\delta (\tilde{x})$ 为 $\tilde{x}$ 的误差限。

$f\left (x^{*}, y^{*}\right)$ 的近似函数 $f (x, y)$ 的误差限和相对误差限有如下估计式：

$$\left\{\begin{array}{c}
\delta f (\tilde{x}, \tilde{y}) \leq\left|\frac{\partial f (\tilde{x}, \tilde{y})}{\partial x}\right| \cdot \delta (\tilde{x})+\left|\frac{\partial f (\tilde{x}, \tilde{y})}{\partial y}\right| \cdot \delta (\tilde{y}) \\
\delta_{r}|f (\tilde{x}, \tilde{y})|=\left|\frac{\delta f (\tilde{x}, \tilde{y})}{f (\tilde{x}, \tilde{y})}\right|
\end{array}\right.$$

式中，假设 $\delta (\tilde{x})$ 和 $\delta (\tilde{y})$ 为 $\tilde{x}$ 和 $\tilde{y}$ 的误差限。

### 算术运算的传播

$$\begin{array}{c}
\left\{\begin{array}{c}
\delta (\tilde{x} \pm \tilde{y}) \leq \delta (\tilde{x})+\delta (\tilde{y}) \\
\delta_{r}(\tilde{x} \pm \tilde{y}) \leq \frac{\delta (\tilde{x})+\delta (\tilde{y})}{|\tilde{x} \pm \tilde{y}|}
\end{array}\right. \\
\left\{\begin{array}{c}
\delta (\tilde{x} \tilde{y}) \leq|\tilde{y}| \delta (\tilde{x})+|\tilde{x}| \delta (\tilde{y}) \\
\delta_{r}(\tilde{x} \tilde{y}) \leq \frac{\delta (\tilde{x})}{|\tilde{x}|}+\frac{\delta (\tilde{y})}{|\tilde{y}|}=\delta_{r}(\tilde{x})+\delta_{r}(\tilde{y})
\end{array}\right. \\
\left\{\begin{array}{c}
\delta\left (\frac{\tilde{x}}{\tilde{y}}\right) \leq \frac{1}{|\tilde{y}|} \delta (\tilde{x})+\left|\frac{\tilde{x}}{\tilde{y}^{2}}\right| \delta (\tilde{y}) \\
\delta_{r}\left (\frac{\tilde{x}}{\tilde{y}}\right) \leq \frac{\delta (\tilde{x})}{|\tilde{x}|}+\frac{\delta (\tilde{y})}{|\tilde{y}|}=\delta_{r}(\tilde{x})+\delta_{r}(\tilde{y})
\end{array}\right.
\end{array}$$

对于某个数值算法，如果输入数据的误差，在计算过程中不断扩大而难以得到控制，则称该算法是数值不稳定的，否则是数值稳定的。如果某算法在一定条件下才是数值稳定的，则称该算法是条件稳定（相对稳定）的。若在任何条件下，某算法都是数值稳定的，则称该算法是无条件稳定（绝对稳定）的。

数值计算原则：

- 避免两个相近数相减
- 避免用绝对值过小的数做除数
- 要防止大数“吃掉”小数
- 简化计算步骤，提高计算效率
- 使用数值稳定的算法

# 非线性方程的数值解

## 二分法

首先把区间 $\left[a_{0}, b_{0}\right]$ 二等分，取区间 $\left[a_{0}, b_{0}\right]$ 的中点 $x_{0}=   \frac{1}{2}\left (a_{0}+b_{0}\right)$，计算函数值 $f\left (x_{o}\right)$。如果 $f\left (x_{o}\right)=0$，则求得实根 $x^{*}=\frac{1}{2}\left (a_{0}+b_{0}\right)$；否则 $f\left (x_{o}\right)$ 或者与 $f\left (a_{0}\right)$ 异号，或者与 $f\left (b_{0}\right)$ 异号。

若 $f\left (a_{0}\right) \cdot f\left (x_{o}\right)<0$，则说明根在区间 $\left[a_{0}, x_{0}\right]$ 内，这时取 $a_{1}=a_{0}$，$B_{1}=x_{0}=\frac{a_{0}+b_{0}}{2}$，若 $f\left (x_{o}\right) \cdot f\left (b_{0}\right)<0$，则说明根在区间 $\left[x_{0}, b_{0}\right]$ 内，这时取 $a_{1}=x_{o}=   \frac{a_{0}+b_{0}}{2}, b_{1}=b_{0}$。

由于

$$\left|x^{*}-x_{k}\right| \leq \frac{1}{2}\left (b_{k}-a_{k}\right)=\frac{1}{2^{k+1}}(b-a)$$


对于预先给定的精度 $\varepsilon>0$，只要

$$\begin{array}{c}
\left|\frac{1}{2^{k+1}}(b-a)\right|<\varepsilon \\
\left|\frac{1}{2^{k}}\right|<\frac{2 \varepsilon}{b-a}, \quad 2^{k}>\frac{b-a}{2 \varepsilon}
\end{array}$$

即当 $k>\frac{\ln (b-a)-\ln 2 \varepsilon}{\ln 2}$ 时，则有

$$\left|x^{*}-x_{k}\right|<\varepsilon$$

此时，$x_{k}$ 就是满足精度要求的近似值。

## 牛顿法

设函数 $f (x)$ 连续可导，$x^{*}$ 是方程 $f (x)=0$ 的实根，$x_{k}$ 是方程根的第 $k$ 次迭代近似值，将函数 $f (x)$ 在点 $x_{k}$ 进行一阶泰勒展开，则有

$$f\left (x^{*}\right) \approx f\left (x_{k}\right)+f^{\prime}\left (x_{k}\right)\left (x^{*}-x_{k}\right)$$


于是，有 $0=f\left (x^{*}\right) \approx f\left (x_{k}\right)+f^{\prime}\left (x_{k}\right)\left (x^{*}-x_{k}\right)$。

可通过切线方程来得到:

$$y=f^{\prime}\left (x_{0}\right)\left (x-x_{0}\right)+y_{0}$$

当 $f^{\prime}\left (x_{k}\right) \neq 0$，有 $x^{*} \approx x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)}$，右端是方程根的又一次近似，记为 $x_{k+1}$，便得到迭代公式

$$x_{k+1}=x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)} \quad (k=0,1,2, \cdots)$$

该公式称为牛顿 (Newton) 迭代公式

相应的迭代函数 $\varphi (x)=x-\frac{f (x)}{f^{\prime}(x)}$。显然，迭代方程 $\varphi (x)=   x-\frac{f (x)}{f^{\prime}(x)}$ 与原方程 $f (x)=0$ 等价。

### 定理 2.2

对方程 $f (x)=0$，若存在区间 $[a, b]$ 使：

- $f (a) f (b)<0$；
- $f^{\prime \prime}(x)$ 在 $[a, b]$ 上不变号；
- 对任意 $x \in[a, b]$，都有 $f^{\prime}(x) \neq 0$；
- 初值 $x_{0} \in[a, b]$，$f\left (x_{0}\right) f^{\prime \prime}\left (x_{0}\right)>0$。

则牛顿迭代公式产生的迭代序列 $\left\{x_{k}\right\}$ 收敛于 $f (x)=0$ 在 $[a, b]$ 上的唯一实根 $x^{*}$。

证明：$\varphi (x)=x-\frac{f (x)}{f^{\prime}(x)}, \quad \varphi^{\prime}(x)=1-\frac{\left[f^{\prime}(x)\right]^{2}-f (x) f^{\prime \prime}(x)}{\left[f^{\prime}(x)\right]^{2}}=\frac{f (x) f^{\prime \prime}(x)}{\left[f^{\prime}(x)\right]^{2}}$。 

1) 因为 $f^{\prime \prime}(x)$ 在 $[a, b]$ 上不变号，$f^{\prime}(x) \neq 0$，所以 $f^{\prime}(x)$ 不变号，$f (x)$ 单调，因为 $f (a) f (b)<0$，所以存在唯一实根 $x^{*}$。
2) 下面证明 $\varphi (x)$ 必收敛于唯一实根 $x^{*}$。

不失一般性，$f\left (x_{0}\right)>0$，则 $f^{\prime \prime}\left (x_{0}\right)>0$。

$$\begin{aligned}
x_{k+1}-x^{*} & =\varphi\left (x_{k}\right)-x^{*}=x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)}-x^{*} \\
& =\left (x_{k}-x^{*}\right)-\frac{f^{\prime}\left (\xi_{k}\right)}{f^{\prime}\left (x_{k}\right)}\left (x_{k}-x^{*}\right) \\
& =\left (x_{k}-x^{*}\right)\left (1-\frac{f^{\prime}\left (\xi_{k}\right)}{f^{\prime}\left (x_{k}\right)}\right)
\end{aligned}$$

其中 $\xi_{k}$ 在 $x_{k}$ 和 $x^{*}$ 之间。

因为 $f^{\prime}(x)$ 不变号，可知 $\frac{f^{\prime}(\xi)}{f^{\prime}\left (x_{k}\right)}>0$  ，下面将证明其小于 1 。
设 $f^{\prime}(x)>0$，因为 $f\left (x_{0}\right)>0=f\left (x^{*}\right)$，则 $x_{0}>x^{*}$，故 $x_{0}>\xi_{0}$。因 $f^{\prime \prime}(x)>  0$，故 $f^{\prime}\left (x_{0}\right)>f^{\prime}\left (\xi_{0}\right)$，$\frac{f^{\prime}\left (\xi_{0}\right)}{f^{\prime}\left (x_{0}\right)}<1$，故 $x_{1}-x^{*}$ 和 $x_{0}-x^{*}$ 同号且前者的绝对值更小，可知 $x_{0}>x_{1}>x^{*}$。由递推可得 $x_{k}>x_{k+1}>x^{*}$。
同理可证明 $f^{\prime}(x)<0$ 的情况。
因为单调有界数列必收敛，假设迭代收敛于 $x^{\prime}$，则 $x^{\prime}=\varphi\left (x^{\prime}\right)$，可得 $f\left (x^{\prime}\right)=0$，由唯一性可知 $x^{\prime}=x^{*}$。

## 弦截法

### 单点弦截法

$$f^{\prime}\left (x_{k}\right) \approx \frac{f\left (x_{k}\right)-f\left (x_{0}\right)}{x_{k}-x_{0}}$$

得到如下公式:

$$x_{k+1}=x_{k}-\frac{\left (x_{k}-x_{0}\right)}{f\left (x_{k}\right)-f\left (x_{0}\right)} f\left (x_{k}\right)$$

### 双点弦截法

$$\begin{array}{c}
x_{k+1}=x_{k}-\frac{x_{k}-x_{k-1}}{f\left (x_{k}\right)-f\left (x_{k-1}\right)} f\left (x_{k}\right), \\
k=1,2, \cdots
\end{array}$$

## 迭代法

为了求一元非线性方程 $f (x)=0$ 的根，可将其转换为如下等价形式 $x=\varphi (x)$ 式中连续函数 $\varphi (x)$ 为迭代函数，并使两个方程具有相同的解，然后构造迭代公式

$$x_{k+1}=\varphi\left (x_{k}\right), \mathrm{k}=0,1,2 \cdots$$

对于给定的初值 $x_{0}$，由上式可产生一个迭代序列 $\left\{x_{k}\right\}_{k=0}^{\infty}$。如果有 $\lim _{k \rightarrow \infty} x_{k+1}=x^{*}$，由于 $\varphi (x)$ 连续，则

$$x^{*}=\lim _{k \rightarrow \infty} x_{k+1}=\lim _{k \rightarrow \infty} \varphi\left (x_{k}\right)=\varphi\left (\lim _{k \rightarrow \infty} x_{k}\right)=\varphi\left (x^{*}\right)$$

因此，$x^{*}$ 是式 $x=\varphi (x)$ 的解，由等价性可知，$x^{*}$ 也是式 $f (x)=  0$ 的解。

此时，称 $x^{*}$ 为 $\varphi (x)$ 的不动点，迭代公式 $x_{k+1}=\varphi\left (x_{k}\right)$，$k=   0,1,2 \cdots$ 称为收敛的，即不动点迭代法。

由于在上式中， $x_{k+1}$ 仅由 $x_{k}$ 决定，因此式 $x_{k+1}=   \varphi\left (x_{k}\right), k=0,1,2 \cdots$ 又称为单步迭代法，$x_{k}$ 称为方程根的第 $k$ 次近似值。

如果迭代序列 $\left\{x_{k}\right\}$ 的极限不存在，则称迭代公式 $x_{k+1}=   \varphi\left (x_{k}\right), k=0,1,2 \cdots$ 是发散的。

在使用迭代法求方程的近似值时，首先要考虑的问题是：

如何选取迭代函数 $\varphi (x)$，使迭代公式 $x_{k+1}=\varphi\left (x_{k}\right)$ 收敛。

### 定理 2.2

设迭代函数 $\varphi (x)$ 满足如下条件：

- $\varphi (x)$ 在 $[a, b]$ 内连续，在 $(a, b)$ 内可导；
- 映内性，对任意的 $x \in[a, b]$，有 $\varphi (x) \in[a, b]$；
- 压缩性，存在一个常数 $L (0<L<1)$ 使得在 $[a, b]$ 内，$\left|\varphi^{\prime}(x)\right| \leq   L<1$。

则：

- 函数 $\varphi (x)$ 在 $[a, b]$ 内存在唯一的不动点 $x^{*}$；
- 对于任意的初始值 $x_{0} \in[a, b]$，由式 $x_{k+1}=\varphi\left (x_{k}\right)$ 产生的近似值序列 $\left\{x_{k}\right\}_{k=1}^{\infty} \in[a, b]$，并且 $\lim _{k \rightarrow \infty} x_{k}=x^{*}$；
- 有以下误差不等式 $$\begin{array}{c}
\left|x_{k}-x^{*}\right| \leq \frac{L}{1-L}\left|x_{k}-x_{k-1}\right| \\
\left|x_{k}-x^{*}\right| \leq \frac{L^{k}}{1-L}\left|x_{1}-x_{0}\right|
\end{array}$$

证明：

先证 $x=\varphi (x)  在  [a, b]$ 内存在实根。由于 $\varphi (x)$ 在 $[a, b]$ 内连续，设 $\varphi_{1}(x)=x-\varphi (x)$ 在 $[a, b]$ 内连续；因为 $\varphi (x) \in[a, b]$，故 $\varphi_{1}(a)=a-\varphi (a) \leq 0, \varphi_{1}(b)=b-\varphi (b) \geq 0$，故存在 $x^{*} \in   [a, b]$，使：

$$\varphi_{1}\left (x^{*}\right)=0$$

即 $x^{*}=\varphi\left (x^{*}\right)$。 

再证实根的唯一性。若方程 $x=\varphi (x)$ 在 $[\mathrm{a}, \mathrm{b}]$ 内有两个实根 $x^{*}$ 和 $x^{* *}$，则由微分中值定理及条件 $\left| \varphi^{\prime}(x) \leq L<1\right|$ 可知：

$$\begin{array}{c}
\left|x^{*}-x^{* *}\right|=\left|\varphi\left (x^{*}\right)-\varphi\left (x^{* *}\right)\right|=\left|\varphi^{\prime}(\xi)\right|\left|x^{*}-x^{* *}\right| \leq 
L\left|x^{*}-x^{* *}\right|
\end{array}$$

其中，$\xi$ 在 $x^{*}$ 和 $x^{* *}$ 之间。
显然，上式在 $x^{*}=x^{* *}$ 时成立，唯一性得证。

---

当 $x_{0} \in[a, b]$ 时，由映内性知 $x_{k} \in[a, b]$，由微分中值定理得：

$$x^{*}-x_{k+1}=\varphi\left (x^{*}\right)-\varphi\left (x_{k}\right)=\varphi^{\prime}(\xi)\left (x^{*}-x_{k}\right)$$

其中，$\xi$ 在 $x^{*}$ 和 $x_{k}$ 之间。

于是：

$$\left|x^{*}-x_{k+1}\right| \leq L\left|x^{*}-x_{k}\right|(k=0,1,2 \cdots)$$

故

$$0 \leq\left|x^{*}-x_{k+1}\right| \leq L^{k}\left|x^{*}-x_{0}\right|$$

注意，$0<L<1$，当 $k \rightarrow \infty  时，  L^{k} \rightarrow 0$，从而得

$$\lim _{k \rightarrow \infty}\left|x^{*}-x_{k}\right|=0$$

即

$$\lim _{k \rightarrow \infty} x_{k}=x^{*}$$

---

由压缩性和微分中值定理

$$\begin{array}{l}
\left|x^{*}-x_{k+1}\right| \leq L\left|x^{*}-x_{k}\right|(k=0,1,2 \cdots) \\
\left|x_{k+1}-x_{k}\right| \leq L\left|x_{k}-x_{k-1}\right|(k=0,1,2 \cdots)
\end{array}$$

从而

$$\begin{aligned}
\left|x_{k+1}-x_{k}\right| & =\left|\left (x^{*}-x_{k}\right)-\left (x^{*}-x_{k+1}\right)\right| \\
& \geq\left|x^{*}-x_{k}\right|-\left|x^{*}-x_{k+1}\right| \\
& \geq\left|x^{*}-x_{k}\right|-L\left|x^{*}-x_{k}\right|=(1-L)\left|x^{*}-x_{k}\right|
\end{aligned}$$


即 $\left|x^{*}-x_{k}\right| \leq \frac{1}{1-L}\left|x_{k+1}-x_{k}\right| \leq \frac{1}{1-L}\left|x_{k}-x_{k-1}\right|$。 

同时：

$$\begin{aligned}\quad\left|x^{*}-x_{k}\right| \leq \frac{1}{1-L}\left|x_{k+1}-x_{k}\right| \leq \frac{L}{1-L}\left|x_{k}-x_{k-1}\right| \\\leq \frac{L^{2}}{1-L} \mid x_{k-1}- x_{k-2}\left|\leq \cdots \leq \frac{L^{k}}{1-L}\right| x_{1}-x_{0} \mid\end{aligned}$$

### 定义 2.1

设 $x^{*}$ 是迭代函数 $\varphi (x)$ 的不动点，若存在 $x^{*}$ 的某个邻域 $N\left (x^{*}, \delta\right):\left|x-x^{*}\right| \leq \delta$，使得对任意初值 $x_{0} \in   N\left (x^{*}, \delta\right)$，由迭代公式 $x_{k+1}=\varphi\left (x_{k}\right), k=0,1,2 \cdots$ 生成的序列 $\left\{x_{k}\right\}_{k=0}^{\infty} \subset N\left (x^{*}, \delta\right)$，且有 $\lim _{k \rightarrow \infty} x_{k}=x^{*}$，则称迭代公式 $x_{k+1}=   \varphi\left (x_{k}\right), k=0,1,2 \cdots$ 局部收敛。

### 定理 2.3

设 $x^{*}$ 是迭代函数 $\varphi (x)$ 的不动点，若 $\varphi^{\prime}(x)$ 在 $x^{*}$ 的某个邻域内连续，并且有 $\left|\varphi^{\prime}(x)\right|<1$，则称迭代公式 $x_{k+1}=\varphi\left (x_{k}\right), k=0,1,2 \cdots$ 局部收敛。

证明：

由于 $\varphi^{\prime}(x)$ 在 $x^{*}$ 的某个邻域内连续，且 $\left|\varphi^{\prime}\left (x^{*}\right)\right|<1$，则必存在 $x^{*}$ 的一个邻域 $N\left (x^{*}, \delta\right)$ 和常数 $L (0 \leq L<1)$ 使得对 $\forall x \in N\left (x^{*}, \delta\right)$，必有 $\left|\varphi^{\prime}(x)\right| \leq L$。

由微分中值定理可知，对任意 $x \in N\left (x^{*}, \delta\right)$，都有：

$$\left|\varphi (x)-x^{*}\right|=\left|\varphi (x)-\varphi\left (x^{*}\right)\right|=\left|\varphi^{\prime}(\xi)\right|\left|x-x^{*}\right| \leq L\left|x-x^{*}\right|<\delta$$

其中，$\xi$ 在 $x$ 和 $x^{*}$ 之间。

这说明 $\varphi (x) \in N\left (x^{*}, \delta\right)$，可证明迭代公式局部收敛。

### 定义 2.2

设序列 $\left\{x_{k}\right\}_{k=0}^{\infty}$ 收敛到 $x^{*}$，并记误差 $e_{k}=\mid x_{k}-   x^{*} \mid$，若存在常数 $p \geq 1$ 和 $c \neq 0$，使得

$$\lim _{k \rightarrow \infty} \frac{e_{k+1}}{e_{k}^{p}}=c$$

则称序列 $\left\{x_{k}\right\}_{k=0}^{\infty}$ 是 $p$ 阶收玫的。当 $p=1$ 时，称为线性收敛；当 $p>1$，称为超线性收玫；当 $p=2$ 时，称为二次收敛或平方收敛。

由上式可知，当 $k \rightarrow \infty$ 时，$e_{k+1}$ 是 $e_{k}$ 的 $p$ 阶无穷小量，因此，阶数 $p$ 越大，收敛就越快。当然，线性收敛时，必有 $0<|c| \leq 1$。

### 定理 2.4

设 $x^{*}$ 是迭代函数 $\varphi (x)$ 的不动点，若有正整数 $p \geq 2$，使得 $\varphi^{(p)}(x)$ 在 $x^{*}$ 的邻域连续，并且满足

$$\varphi^{(n)}\left (x^{*}\right)=0 ， n=1,2, \cdots, p-1 \text { ，但 } \varphi^{(p)}(x) \neq 0$$

则 $x_{k+1}=\varphi\left (x_{k}\right), k=0,1,2 \cdots$ 局部收敛，并且是 $p$ 阶收敛的。

### 定理 2.5

设 $x^{*}$ 是方程 $f (x)=0$ 的单根，并且 $f^{\prime \prime}(x)$ 在 $x^{*}$ 的邻域上连续，则牛顿迭代公式 $x_{k+1}=x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)}$ 至少平方局部收敛。

证明：

将式 $x_{k+1}=x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)}$ 写成不动点迭代形式 $x_{k+1}=\varphi\left (x_{k}\right)$，式中 $\varphi (x)=   x-\frac{f (x)}{f^{\prime}(x)}$，称其为牛顿迭代函数。

因为 $x^{*}$ 为 $f (x)=0$ 的单根，所以 $f^{\prime}\left (x^{*}\right) \neq 0$，从而 $x^{*}=\varphi\left (x^{*}\right)$，即 $x^{*}$ 是 $\varphi (x)$ 的不动点。对迭代函数 $\varphi (x)$ 求倒数，得：

$$\varphi^{\prime}(x)=1-\frac{\left[f^{\prime}(x)\right]^{2}-f (x) f^{\prime \prime}(x)}{\left[f^{\prime}(x)\right]^{2}}=\frac{f (x) f^{\prime \prime}(x)}{\left[f^{\prime}(x)\right]^{2}}$$

因为 $f^{\prime}\left (x^{*}\right) \neq 0$，所以 $\varphi^{\prime}\left (x^{*}\right)=0$，根据定理 2.2 可知牛顿迭代公式 $x_{k+1}=   x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)}$ 局部收敛。将 $f\left (x^{*}\right)$ 在 $x$ 处泰勒展开，得：

$$0=f\left (x^{*}\right)=f\left (x_{k}\right)+f^{\prime}\left (x_{k}\right)\left (x^{*}-x_{k}\right)+\frac{f^{\prime \prime}\left (\xi_{k}\right)}{2}\left (x^{*}-x_{k}\right)^{2}$$

（其中 $\xi_{k}$ 在 $x_{k}$ 与 $x^{*}$ 之间），将式 $x_{k+1}=x_{k}-\frac{f\left (x_{k}\right)}{f^{\prime}\left (x_{k}\right)}$ 改写为 $f\left (x_{k}\right)-f^{\prime}\left (x_{k}\right) x_{k}=-f^{\prime}\left (x_{k}\right) x_{k+1}$，代入上式得：

$$0=f^{\prime}\left (x_{k}\right)\left (x^{*}-x_{k+1}\right)+\frac{f^{\prime \prime}\left (\xi_{k}\right)}{2}\left (x^{*}-x_{k}\right)^{2}$$

即：

$$\frac{e_{k+1}}{e_{k}^{2}}=\frac{f_{\prime \prime}\left (\xi_{k}\right)}{2 f^{\prime}\left (x_{k}\right)} \quad\left (e_{k}=\left|x_{k}-x^{*}\right|\right)$$

令 $k \rightarrow \infty$，由局部收玫性可知 $x_{k} \rightarrow x^{*}$，从而 $\xi_{k} \rightarrow x^{*}$，所以有

$$\lim _{k \rightarrow \infty} \frac{e_{k+1}}{e_{k}^{2}}=\frac{f^{\prime \prime}\left (x^{*}\right)}{2 f^{\prime}\left (x^{*}\right)}=\mathrm{c}$$

因此，当 $c \neq 0$ 时，牛顿迭代公式平方局部收敛，如果 $c=0$ 时，牛顿迭代公式至少平方局部收敛。

# 线性方程组的数值解

## 高斯消元法

### 高斯消元法

消去对角线下方得元素，使系数矩阵变为上三角矩阵。

一般地，设  n  阶线性方程组为

$$\left\{\begin{array}{c}
a_{11}^{(0)} x_{1}+a_{12}^{(0)} x_{2}+\cdots+a_{1 n}^{(0)} x_{n}=b_{1}^{(0)} \\
a_{21}^{(0)} x_{1}+a_{22}^{(0)} x_{2}+\cdots+a_{2 n}^{(0)} x_{n}=b_{1}^{(0)} \\
\vdots \\
a_{n 1}^{(0)} x_{1}+a_{n 2}^{(0)} x_{2}+\cdots+a_{n n}^{(0)} x_{n}=b_{n}^{(0)}
\end{array}\right.$$

其矩阵形式为

$$\boldsymbol{A}^{(0)} \boldsymbol{x}=\boldsymbol{b}^{(0)}$$

记方程组 (3.1) 的增广矩阵为

$$\left (\boldsymbol{A}^{(0)} \mid \boldsymbol{b}^{(0)}\right)=\left (\begin{array}{cccc}
a_{11}^{(0)} & \cdots & a_{1 n}^{(0)} & b_{1}^{(0)} \\
\vdots & \ddots & \vdots & \vdots \\
a_{n 1}^{(0)} & \cdots & a_{n n}^{(0)} & b_{n}^{(0)}
\end{array}\right)$$

#### 消元过程

对 $k=1,2, \cdots, n-1$ 逐次计算

$$\left\{\begin{array}{c}
l_{i k}=a_{i k}^{(k-1)} / a_{k k}^{(k-1)}(i=k+1, \cdots, n) \\
a_{i j}^{(k)}=a_{i j}^{(k-1)}-l_{i k} a_{k j}^{(k-1)}(i, j=k+1, \cdots, n) \\
b_{i}^{(k)}=b_{i}^{(k-1)}-l_{i k} b_{k}^{k-1}(i=k+1, \cdots, n)
\end{array}\right.$$

#### 回代过程

逐步回代求得原方程组的解：

$$\left\{\begin{array}{c}
x_{n}=b_{n}^{(n-1)} / a_{n n}^{(n-1)} \\
x_{k}=\left (b_{k}^{(k-1)}-\sum_{j=k+1}^{n} a_{k j}^{(k-1)} x_{j}\right) / a_{k k}^{(k-1)}(k=n-1, n-2, \cdots, 1)
\end{array}\right.$$

### 定理 3.1

如果 $n$ 阶矩阵 $A$ 的顺序主序式均不为零，即

$$a_{11} \neq 0,\left|\begin{array}{ll}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{array}\right| \neq 0, \cdots, \operatorname{det}(\boldsymbol{A}) \neq 0$$

则用高斯消元法求解方程组 $\boldsymbol{A} x=b$ 时的主元素为

$$a_{k k}^{(k-1)} \neq 0 (k=1,2, \cdots, n)$$

#### 高斯消元法计算量

##### 消元过程

* 第 $k$ 次消元 $l_{i k}$ 需进行 $n-k$ 次除法
* 求 $a_{i j}^{(k)}$ 需要进行 $(n-k)^{2}$ 次乘法
- 求 $b_{i}^{(k)}$ 需进行 $n-k$ 次乘法

所以，消元过程中乘除法总计算量为

$$\begin{array}{l}
\sum_{k=1}^{n-1}\left[(n-k)+(n-k)^{2}+(n-k)\right]=2 \sum_{k=1}^{n-1}(n-k)+\sum_{k=1}^{n-1}(n-k)^{2} \\
=2[(n-1)+(n-2)+\cdots+2+1]+\left[(n-1)^{2}+(n-2)^{2}+\cdots+2^{2}+1^{2}\right] \\
=2 \times \frac{1}{2} n (n-1)+\frac{1}{6} n (n-1)(2 n-1) \\
=\frac{1}{3} n^{3}+\frac{1}{2} n^{2}-\frac{5}{6} n
\end{array}$$

##### 回代过程

* 求 $x_{k}$ 需要 $1$ 次除法和 $n-k$ 次乘法

所以回代过程的乘除计算量为：

$$\sum_{k=1}^{n}(n-k)+n=\frac{1}{2} n (n-1)+n=\frac{1}{2} n^{2}+\frac{1}{2} n$$

高斯消去法的乘除总计算量为

$$\frac{1}{3} n^{3}+\frac{1}{2} n^{2}-\frac{5}{6} n+\frac{1}{2} n^{2}+\frac{1}{2} n=\frac{1}{3} n^{3}+n^{2}-\frac{1}{3} n$$

和克莱姆法则需要的计算量 $(n+1) n! (n-1)+n$ 相比，计算量大大减少。

### 列主元素消元法

事实上，从顺序高斯消元法可以看出，当 $\left|\frac{a_{i k}^{(k-1)}}{a_{k k}^{(k-1)}}\right|>1$ 时，

若 $a_{k j}^{(k-1)}$ 有舍入误差 $e_{\mathrm{k}-1}$，则经过计算 $a_{i k}^{(k)}=a_{i k}^{(k-1)}-l_{i k} a_{k j}^{(k-1)}$，$a_{i k}^{(k)}$ 就会有比 $e_{\mathrm{k}-1}$ 更大的舍入误差 $e_{\mathrm{k}}=\left|l_{i k}\right| e_{\mathrm{k}-1}$ 产生；

同样，$b_{i}^{(k)}$ 的误差也会比 $b_{i}^{(k-1)}$ 的舍入误差大；

为了达到减小舍入误差的目的，必须保证 $\left|l_{i k}\right|<1$ ，即 $\left|a_{k k}^{(k-1)}\right|   >\left|a_{i k}^{(k-1)}\right|(i=k+1, k+2, \ldots, n)$，于是可以对顺序消元法进行改进。

### 高斯约旦（Gauss-Jordan）消元法

消去对角线下方和上方的元素，使系数矩阵变为单位矩阵，它不需要回代过程。

## 矩阵分解法

第 $k$ 次消元相当于用初等矩阵 $\boldsymbol{L}_{k}$ 左乘增广矩阵 $\left (\boldsymbol{A}^{(k-1)}, \boldsymbol{b}^{(k-1)}\right)$，记为：

$$\boldsymbol{L}_{k}\left (\boldsymbol{A}^{(k-1)}, \boldsymbol{b}^{(k-1)}\right)=\left (\boldsymbol{A}^{(k)}, \boldsymbol{b}^{(k)}\right)$$

重复这一过程，进过 $n  - 1$ 步消元后，最后得到

$$\boldsymbol{L}_{n-1} \boldsymbol{L}_{n-2} \cdots\left (\boldsymbol{A}^{(0)}, \boldsymbol{b}^{(0)}\right)=\left (\boldsymbol{A}^{(n-1)}, \boldsymbol{b}^{(n-1)}\right)$$

可以得到：

$$\left (\boldsymbol{A}^{(0)}, \boldsymbol{b}^{(0)}\right)=\boldsymbol{L}_{1}^{-1} \boldsymbol{L}_{2}^{-1} \cdots \boldsymbol{L}_{n-1}^{-1}\left (\boldsymbol{A}^{(n-1)}, \boldsymbol{b}^{(n-1)}\right)$$

可求得 $\boldsymbol{L}=\boldsymbol{L}_{1}^{-1} \boldsymbol{L}_{2}^{-1} \cdots \boldsymbol{L}_{n-1}^{-1}=\left (\begin{array}{ccccc}1 & & & & \\ l_{21} & 1 & & & \\ l_{31} & l_{32} & 1 & & \\ \vdots & \vdots & \ddots & \ddots & \\ l_{n 1} & l_{n 2} & \cdots & l_{n (n-1)} & 1\end{array}\right)$ 

记

$$\boldsymbol{U}=\boldsymbol{A}^{(n-1)}, \boldsymbol{Y}=\boldsymbol{b}^{(n-1)}$$

于是有

$$\left (\boldsymbol{A}^{(0)}, \boldsymbol{b}^{(0)}\right)=\boldsymbol{L}\left (\boldsymbol{A}^{(n-1)}, \boldsymbol{b}^{(n-1)}\right)=(\boldsymbol{L} \boldsymbol{U}, \boldsymbol{L Y})$$

这说明，在 $a_{k k}^{(k-1)} \neq 0 (k=1,2, \cdots, n-1)$ 的条件下，高斯消去法的消元过程实质上是把系数矩阵 $A$ 分解成一个单位下三角矩阵 $L$ 与上三角矩阵 $U$ 的乘积过程。

### 定理 3.2

设 $A$ 为 $n$ 阶矩阵，如果 $A$ 的顺序主子式 $D_{i} \neq 0 (i=   1,2, \cdots, n)$，则 $A$ 可分解为一个单位下三角矩阵 $L$ 和一个上三角矩阵 $U$ 的乘积，且这种分解是唯一的。

当系数矩阵完成三角分解后，对于求解方程组 $A x=\boldsymbol{b}$，就有

$$A x=b \underset{A=L U}{\longleftrightarrow} L U x=b \underset{\text { 令 } y=U x}{\longrightarrow}\left\{\begin{array}{l}
L y=b \\
U x=y
\end{array}\right.$$

高斯消元法的消元过程相当于分解 $\boldsymbol{A}=\boldsymbol{L} \boldsymbol{U}$ 及求解三角形方程式 $L \boldsymbol{y}=\boldsymbol{b}$ 

高斯消元法的回代过程则是求解另一个三角形方程 $U x=y$，因此，解方程组的问题可转化为矩阵的三角分解问题

### 直接三角分解法

设

$$\begin{array}{l}
\boldsymbol{A}&=\left (\begin{array}{ccccc}
a_{11} & a_{12} & a_{13} & \cdots & a_{1 n} \\
a_{21} & a_{22} & a_{23} & \cdots & a_{2 n} \\
a_{31} & a_{32} & a_{33} & \cdots & a_{3 n} \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
a_{n 1} & a_{n 2} & a_{n 3} & \cdots & a_{n n}
\end{array}\right)\\&= 
\left (\begin{array}{ccccccc}
1 & & & & \\
l_{21} & 1 & & & \\
l_{31} & l_{32} & 1 & & \\
\vdots & \vdots & \vdots & \ddots & \\
l_{n 1} & l_{n 2} & l_{n 3} & \cdots & 1
\end{array}\right)\left (\begin{array}{lllll}
u_{11} & u_{12} & u_{13} & \cdots & u_{1 n} \\
& u_{22} & a_{23} & \cdots & u_{2 n} \\
& & u_{33} & \cdots & u_{3 n} \\
& & & \ddots & \vdots \\
& & & & u_{n n}
\end{array}\right)=\boldsymbol{L} \boldsymbol{U}
\end{array}$$

上式为 Doolittle 分解。

之后使用 $Ly=b$ 以及 $Ux=y$，求出 $x$。

### Cholesky 分解法

#### 定理 3.2

若矩阵 $A$ 为对称正定矩阵，则存在一个对角元均为正数的下三角形矩阵 $\boldsymbol{L} \in \mathrm{R}^{n \times n}$ 使得

$$\boldsymbol{A}=\boldsymbol{L L}^{T}$$

其中 $L$ 称为 $A$ 的 Cholesky 因子。

### 解三对角方程组的追赶法

在三次样条插值问题和常微分方程边值问题的数值计算方法中，都要求解对角占优的三对角线性方程组

$$A x=d$$

式中

$$\boldsymbol{A}=\left[\begin{array}{ccccc}
b_{1} & c_{1} & & & \\
a_{2} & b_{2} & c_{2} & & \\
& \ddots & \ddots & \ddots & \\
& & a_{n-1} & b_{n-1} & c_{n-1} \\
& & & a_{n} & b_{n}
\end{array}\right], \boldsymbol{d}=\left[\begin{array}{c}
d_{1} \\
d_{2} \\
\vdots \\
d_{n}
\end{array}\right]$$

并且  A  满足条件

$$\left\{\begin{array}{l}
\left|b_{1}\right|>\left|c_{1}\right|>0 \\
\left|b_{i}\right| \geq\left|a_{i}\right|+\left|c_{i}\right| \\
\left|b_{n}\right|>\left|a_{n}\right|>0
\end{array} \quad\left (a_{i} c_{i} \neq 0\right)\right.$$

称 $A$ 为对角占优的三对角线矩阵。

以下对  A  进行 Crout 分解:

$$\boldsymbol{L}=\left[\begin{array}{ccccc}
l_{1} & & & & \\
a_{2} & l_{2} & & & \\
& a_{3} & l_{3} & & \\
& & \ddots & \ddots & \\
& & & a_{n} & l_{n}
\end{array}\right], \boldsymbol{U}=\left[\begin{array}{ccccc}
1 & u_{1} & & & \\
& 1 & u_{2} & & \\
& & 1 & \ddots & \\
& & & \ddots & u_{n-1} \\
& & & & 1
\end{array}\right]$$

利用矩阵的乘法可得

$$\left\{\begin{array}{c}
b_{1}=l_{1} \\
c_{i}=l_{i} u_{i} \\
b_{i+1}=a_{i+1} u_{i}+l_{i+1}
\end{array} \quad (i=1,2,3, \cdots, n-1)\right.$$

由上式解出：

$$\left\{\begin{array}{c}
l_{1}=b_{1} \\
u_{i}=c_{i} / l_{i} \\
l_{i+1}=b_{i+1}-a_{i+1} u_{i}
\end{array} \quad (i=1,2,3, \cdots, n-1)\right.$$

对 $A$ 的分解只需求 $l_{i}, u_{i}$，且按 $l_{1} \rightarrow u_{1} \rightarrow l_{2} \rightarrow u_{2} \rightarrow \cdots \rightarrow l_{n-1} \rightarrow   u_{n-1} \rightarrow l_{n}$  的递推过程进行，形象地称为 “追” 的过程。

解方程组就化为求 $L U x=d$，令 $U x=y$，则 $L y=d$。
解方程组 $L y=d$，即

$$\left\{\begin{array}{c}
l_{1} y_{1}=d_{1} \\
a_{i} y_{i-1}+l_{i} y_{i}=d_{i}
\end{array} \quad (i=2, \cdots, n)\right.$$

得

$$\left\{\begin{array}{c}
y_{1}=d_{1} / l_{1} \\
y_{i}=\left (d_{i}-a_{i} y_{i-1}\right) / l_{i}
\end{array} \quad (i=2, \cdots, n)\right.$$

解方程组 $U x=y$，即

$$\left\{\begin{array}{c}
x_{i}+u_{i} x_{i+1}=y_{i} \\
x_{n}=y_{n}
\end{array} \quad (i=2, \cdots, n)\right.$$

得

$$\left\{\begin{array}{c}
x_{i}=y_{i}-u_{i} x_{i+1} \\
x_{n}=y_{n}
\end{array} \quad (i=n-1, \cdots, 2,1)\right.$$


形象地称回代求解的过程为 “赶” 的过程，故此求解方程组的方法称为追赶法。

## 误差分析

### 定义 3.1

求解线性方程组 $A x=b$ 时，若 $A$ 或 $b$ 有微小扰动 $\|\delta \boldsymbol{A}\|  或  \|\delta \boldsymbol{b}\|$ 时，解 $x$ 的扰动 $\|\delta \boldsymbol{x}\|$ 很大，则称此方程组为病态方程组，相应的系数矩阵 $A$ 称为病态矩阵。反之，若此时 $\|\delta x\|$ 很小，则称方程组为良态方程组，矩阵  A  称为良态矩阵。

### 定义 3.2

称 $\frac{\|\delta x\|}{\|x\|}$、$\frac{\|\delta A\|}{\|A\|}$ 和 $\frac{\|\delta b\|}{\|b\|}$ 分别为解向量 $x$、矩阵 $A$ 和右端向量 $\boldsymbol{b}$ 的相对扰动。

设线性方程组

$$A x=b$$

的扰动方程组为

$$(\boldsymbol{A}+\delta \boldsymbol{A})(\boldsymbol{x}+\delta \boldsymbol{x})=\boldsymbol{b}+\delta \boldsymbol{b}$$

式中，$\delta A$ 是 $A$ 的扰动矩阵，$\delta x$ 和 $\delta b$ 分别是 $x$ 和 $b$ 的扰动向量，并总假设 $A+\delta A$ 非奇异。

当 $\delta \boldsymbol{A}=0, \delta \boldsymbol{b} \neq 0, \boldsymbol{b} \neq 0$ 时

此时扰动方程组为

$$\boldsymbol{A}(\boldsymbol{x}+\delta \boldsymbol{x})=\boldsymbol{b}+\delta \boldsymbol{b}$$

$$\boldsymbol{A} \delta \boldsymbol{x}=\delta \boldsymbol{b}$$

所以 $\delta \boldsymbol{x}=\boldsymbol{A}^{-1} \delta \boldsymbol{b}$，由范数的定义得

$$\|\delta x\| \leq\left\|A^{-1}\right\| \cdot\|\delta b\|$$

再由 $A x=b$ 得

$$\|b\| \leq\|A\| \cdot\|x\|$$
从而有

$$\|\delta x\| \cdot\|b\| \leq\|A\| \cdot\left\|A^{-1}\right\| \cdot\|x\| \cdot\|\delta b\|$$

因为 $b \neq 0, x \neq 0$，所以 $\|b\|>0,\|x\|>0$，于是有

$$\frac{\|\delta x\|}{\|x\|} \leq\|\boldsymbol{A}\| \cdot\left\|\boldsymbol{A}^{-1}\right\| \cdot \frac{\|\delta \boldsymbol{b}\|}{\|\boldsymbol{b}\|}$$

病态式说明当右端项 $b$ 有扰动 $\|\delta \boldsymbol{b}\|$ 时，解 $\boldsymbol{x}$ 相对扰动不超过 $b$ 的相对扰动的 $\|A\| \cdot\left\|A^{-1}\right\|$  倍。

当 $\delta \boldsymbol{A} \neq 0, \delta \boldsymbol{b}=0, \boldsymbol{A} \neq 0$ 时

此时扰动方程组为

$$(\boldsymbol{A}+\delta \boldsymbol{A})(\boldsymbol{x}+\delta \boldsymbol{x})=\boldsymbol{b}$$

$$\delta\boldsymbol A (x+\delta x)+\boldsymbol A \delta x=0$$

$$\delta x=-\boldsymbol A^{-1} \delta\boldsymbol A (x+\delta x)$$

由范数的定义得

$$\|\delta x\| \leq\left\|A^{-1}\right\| \cdot\|\delta A\| \cdot\|x+\delta x\|$$

于是有

$$\frac{\|\delta x\|}{\|x+\delta x\|} \leq\|A\| \cdot\left\|A^{-1}\right\| \cdot \frac{\|\delta A\|}{\|A\|}$$

说明，当 $A$ 有扰动 $\|\delta A\|$ 时，解 $x+\delta x$ 的相对扰动，不超过 $A$ 的相对扰动的 $\|A\| \cdot\left\|A^{-1}\right\|$ 倍。


对于扰动，经过推理可以得出：

$$
\frac{\|\delta x\|}{\|x\|} \leq \frac{\|A\| \cdot\left\|A^{-1}\right\|}{1-\|A\| \cdot\left\|A^{-1}\right\| \cdot \frac{\|\delta A\|}{\|A\|}}\left (\frac{\|\delta b\|}{\|b\|}+\frac{\|\delta A\|}{\|A\|}\right)
$$

$\|A\| \cdot\left\|A^{-1}\right\|$ 描述了方程组的病态程度。

### 定义 3.3

设 $A$ 为 $n$ 阶可逆矩阵，称 $\operatorname{cond}(\boldsymbol{A})=\left\|\boldsymbol{A}^{-1}\right\| \cdot\|\boldsymbol{A}\|$ 为矩阵 $A$ 的条件数，式中 $\|A\|$ 是矩阵 $A$ 的算子范数。

常用的条件数为

$$\begin{array}{l}
\operatorname{cond}_{\infty}(\boldsymbol{A})=\|\boldsymbol{A}\|_{\infty} \cdot\left\|\boldsymbol{A}^{-1}\right\|_{\infty} \\
\operatorname{cond}_{1}(\boldsymbol{A})=\|\boldsymbol{A}\|_{1} \cdot\left\|\boldsymbol{A}^{-1}\right\|_{1} \\
\operatorname{cond}_{2}(\boldsymbol{A})=\|\boldsymbol{A}\|_{2} \cdot\left\|\boldsymbol{A}^{-1}\right\|_{2}
\end{array}$$

分别称为 $A$ 的 $\infty$ -条件数、$1$ -条件数和 $2$ -条件数。

#### 条件数的性质

1) 对任意非奇异矩阵 $\boldsymbol{A}$，都有 $\operatorname{cond}(\boldsymbol{A}) \geq 1, \operatorname{cond}(\boldsymbol{A})=   \operatorname{cond}\left (\boldsymbol{A}^{-1}\right)$ 
2) 若 $\boldsymbol{A}$ 为非奇异阵，且 $k \neq 0$ (常数)，则 $\operatorname{cond}(k \boldsymbol{A})=   \operatorname{cond}(\boldsymbol{A})$ 
3) 如果 $A$ 为非奇异阵，$U$ 为正交阵，则 $$\operatorname{cond}_{2}(\boldsymbol{A})=\operatorname{cond}_{2}(\boldsymbol{U} \boldsymbol{A})=\operatorname{cond}_{2}(\boldsymbol{A} \boldsymbol{U}), \operatorname{cond}_{2}(\boldsymbol{U})=1$$
4) 若 $\lambda_{1} , \lambda_{2}$ 为 $A$ 的按模最大和最小的特征值，则 $$\operatorname{cond}_{2}(\boldsymbol{A})=\frac{\left|\lambda_{1}\right|}{\left|\lambda_{2}\right|}$$

在实际中，可通过求解过程直观的判断方程组的病态特征

1) 若在主元素消元过程中出现小主元，则 $A$ 可能是病态阵，但病态阵未必一定有这种小主元。
2) 系数矩阵的行列式的值相对来说很小，则 $A$ 有可能是病态阵。
3) 从矩阵本身来看，若元素间数量级很大且无一定规律，或者矩阵的某些行 (列) 近似线性相关，这样的矩阵有可能是病态的。
4) 如果 $A$ 的最大特征值和最小特征值之比（按绝对值）较大，则 $A$ 有可能是病态的。

用选主元的消去法不能解决病态问题，对于病态方程组可采用以下措施:

- 采用高精度的运算，减轻病态影响
- 采用预处理方法改善 $A$ 的条件数，例如，可选择非奇异的对角阵或三角阵 $P, Q$ 将 $A x=b$ 转化为以下等价形式

$$\left\{\begin{array}{c}
P A Q y=P b \\
y=Q^{-1} x
\end{array}\right.$$

使 $\operatorname{cond}(\boldsymbol{P A Q})<\operatorname{cond}(\boldsymbol{A})$ 

当矩阵 $A$ 的元素数量级较大时，对 $A$ 的行 (列) 乘以适当的比例因子，$A$ 使得所有行列按 $\infty$ -范数大体上有相同的长度，使 $A$ 的系数均衡，可使 $A$ 的条件数得到改善

## 迭代法

### 雅各比迭代法

设有线性方程组

$$\sum_{j=1}^{n} a_{i j} x_{j}=b_{i} \quad (i=1,2, \cdots, n)$$

其矩阵形式为 $\boldsymbol{A} \boldsymbol{x}=\boldsymbol{b}$，设系数矩阵 $\boldsymbol{A}$ 为非奇异矩阵，且 $a_{i i} \neq   0 (i=1,2, \cdots, n)$，从上式的第 $i$ 个方程中解出 $x_{i}$，等价形式

$$x_{i}=\frac{1}{a_{i i}}\left (b_{i}-\sum_{j=1, j \neq i}^{n} a_{i j} x_{j}\right) \quad (i=1,2, \cdots, n)$$

取初始向量 $x^{(0)}=\left (x_{1}^{(0)}, x_{2}^{(0)}, \cdots, x_{n}^{(0)}\right)^{T}$，应用迭代法可建立相应的迭代公式

$$x_{i}^{(k+1)}=\frac{1}{a_{i i}}\left (-\sum_{j=1, j \neq i}^{n} a_{i j} x_{j}^{(k)}+b_{i}\right)$$

也可记为矩阵形式

$$\boldsymbol{x}^{(k+1)}=\boldsymbol{B}_{\boldsymbol{J}} \boldsymbol{x}^{(k)}+\boldsymbol{f}_{\boldsymbol{J}}$$

记 $A=D-L-U$：

$$\boldsymbol{D}=\left (\begin{array}{llll}
a_{11} & & & \\
& a_{22} & & \\
& & \ddots & \\
& & & a_{n n}
\end{array}\right)$$

$$
-\boldsymbol{L}=\left (\begin{array}{ccccc}
0 & & & & \\
a_{21} & 0 & & & \\
a_{31} & a_{32} & 0 & & \\
\vdots & \vdots & \ddots & \ddots & \\
a_{n 1} & a_{n 2} & \ldots & a_{n n-1} & 0
\end{array}\right)
$$

$$
-\boldsymbol{U}=\left (\begin{array}{ccccc}
0 &a_{12} &a_{13} &\cdots &a_{1 n} \\
 & 0 &a_{23} &\cdots &a_{2 n} \\
 &  & 0 &\ddots &\vdots \\
 &  &  & \ddots &a_{n-1 n} \\
 &  &  &  & 0
\end{array}\right)
$$

则方程组 $A x=b$ 变为

$$(D-L-U) x=b$$

得

$$D x=(L+U) x+b$$

于是

$$\begin{aligned}
x & =D^{-1}(L+U) X+D^{-1} b=D^{-1}(D-A) x+D^{-1} b \\
& =\left (I-D^{-1} A\right) x+D^{-1} b=B_{J} x+f_{J}
\end{aligned}$$

于是 $B_{J}=I-D^{-\mathbf{1}} A, f_{J}=D^{-\mathbf{1}} b$。

- 雅可比迭代法的分量形式用于编程计算
- 雅可比迭代法的矩阵形式用于讨论迭代法的收玫性

这一过程可以被表述为（下述一例）：

$$
\left\{\begin{array}{c}
x_{1}^{(k+1)}=\frac{1}{3}\left (8-x_{2}^{(k)}-x_{3}^{(k)}\right) \\
x_{2}^{(k+1)}=\frac{1}{2}\left (8-x_{1}^{(k)}-x_{3}^{(k)}\right) \\
x_{3}^{(k+1)}=6-x_{1}^{(k)}-x_{2}^{(k)}
\end{array}\right.
$$

### 高斯-赛德尔（Gauss-Seidel）迭代法

其迭代公式为

$$x_{i}^{(k+1)}=\frac{1}{a_{i i}}\left (-\sum_{j=1}^{i-1} a_{i j} x_{j}^{(k+1)}-\sum_{j=i+1}^{n} a_{i j} x_{j}^{(k)}+b_{i}\right)(i=1,2 \cdots, n)$$

也可以写成矩阵形式

$$\boldsymbol{x}^{(k+1)}=\boldsymbol{B}_{G-S} \boldsymbol{x}^{(k)}+\boldsymbol{f}_{G-S}$$

仍将系数矩阵 $A$ 分解为 $A=D-L-U$ ($D, L, U$ 的含义与前面相同)，则方程组变为

$$(\boldsymbol{D}-\boldsymbol{L}-\boldsymbol{U}) \boldsymbol{x}=\boldsymbol{b}$$

得

$$D x=L x+U x+b$$

将最新分量代替旧分量，得

$$\boldsymbol{D} \boldsymbol{x}^{(k+1)}=\boldsymbol{L} \boldsymbol{x}^{(k+1)}+\boldsymbol{U} \boldsymbol{x}^{(k)}+\boldsymbol{b}$$

即 $(\boldsymbol{D}-\boldsymbol{L}) \boldsymbol{x}^{(k+1)}=\boldsymbol{U} \boldsymbol{x}^{(k)}+\boldsymbol{b}$，于是有

$$\boldsymbol{x}^{(k+1)}=(\boldsymbol{D}-\boldsymbol{L})^{-1} \boldsymbol{U} \boldsymbol{x}^{(k)}+(\boldsymbol{D}-\boldsymbol{L})^{-1} \boldsymbol{b}=\boldsymbol{B}_{G-S} \boldsymbol{x}^{(k)}+\boldsymbol{f}_{G-S}$$


所以 $$\boldsymbol{B}_{G-S}=(\boldsymbol{D}-\boldsymbol{L})^{-1} \boldsymbol{U}, \boldsymbol{f}_{G-S}=(\boldsymbol{D}-\boldsymbol{L})^{-1} \boldsymbol{b}$$

这一过程可以被表述为（下述一例）：

$$
\left\{\begin{array}{c}
x_{1}^{(k+1)}=\frac{1}{3}\left (8-x_{2}^{(k)}-x_{3}^{(k)}\right) \\
x_{2}^{(k+1)}=\frac{1}{2}\left (8-x_{1}^{(k+1)}-x_{3}^{(k)}\right) \\
x_{3}^{(k+1)}=6-x_{1}^{(k+1)}-x_{2}^{(k+1)}
\end{array}\right.
$$

### 定理 3.3

设有 $n$ 阶方程组 $x=B x+f$，对于任意初始向量 $x^{(0)}$ 和右端项 $f$ 迭代法收玫的充分必要条件是迭代矩阵的谱半径 $\rho (B)<1$。

证明:

因为 $\rho (B)<1$，即 B 的特征值 $\left|\lambda_{i}\right|<1 (i=1,2, \cdots n)$，矩阵 $I-B$ 的特征值为

$$u_{i}=1-\lambda_{i} \quad (\lambda=1,2, \cdots n)$$

所以:

$$\operatorname{det}(I-B)=\prod_{i=1}^{n}\left (1-\lambda_{i}\right) \neq 0$$

即 $I-B$ 非奇异，因此，方程组 $(I-B) x=f$，即

$$x=B x+f$$

有唯一的解 $x^{*}$。

逐次递归可得

$$x^{(k)}-x^{*}=B^{k}\left (x^{(0)}-x^{*}\right)$$

对任意的初值 $x^{(0)}$，有

$$\lim _{k \rightarrow \infty} B^{k}\left (x^{(0)}-x^{*}\right)=0$$

可推出

$$\lim _{k \rightarrow \infty} B^{k}=0$$

即

$$\rho (B)<1$$

迭代法的收玫性取决于迭代矩阵 $B$ 的谱半径，$B$ 又依赖于方程组的系数矩阵 $A$，而与初始向量的选取和方程组的右端项无关。

$\rho (B)$ 越小，序列 $\left\{x^{(k)}\right\}$ 收敛也越快，由此可给出收敛速度的定义。

### 定义 3.4

称：

$$R (B)=-\ln \rho (B)$$

为迭代法的收玫速度。

### 定理 3.4

设雅可比迭代矩阵 $B_{J}=I-D^{-1} A$ 为非负矩阵，则下列关系有且仅有一个成立。

1) $\rho\left (B_{J}\right)=\rho\left (B_{G-S}\right)=0$ 
2) $0<\rho\left (B_{G-S}\right)<\rho\left (B_{J}\right)<1$ 
3) $\rho\left (B_{J}\right)=\rho\left (B_{G-S}\right)=1$ 
4) $1<\rho\left (B_{J}\right)<\rho\left (B_{G-S}\right)$ 

定理说明雅可比迭代矩阵 $B_{J}=I-D^{-1} A$ 为非负矩阵时，雅可比方法和高斯-赛德尔方法同时收玫，或者同时发散。

若同时收敛，则高斯-赛德尔方法收敛得快。

### 定理 3.5

若 $\|B\|<1$，则由迭代公式 $\boldsymbol{x}^{(k+1)}=\boldsymbol{B} \boldsymbol{x}^{(k)}+\boldsymbol{f}$ 所产生的相连序列 $\left\{x^{(k)}\right\}$ 收敛于方程组 $x=B x+f$ 的精确解 $x^{*}$，且有误差公式

$$\begin{array}{l}
\left\|x^{(k)}-x^{*}\right\| \leq \frac{\|B\|}{1-\|B\|}\left\|x^{(k)}-x^{(k-1)}\right\| \\
\left\|x^{(k)}-x^{*}\right\| \leq \frac{\|B\|^{k}}{1-\|B\|}\left\|x^{(1)}-x^{(0)}\right\|
\end{array}$$

证明:

因为 $\|B\|<1$，根据 $\rho (B) \leq\|B\|$，由定理 3.3 ，迭代公式 $x^{(k+1)}=   \boldsymbol{B} \boldsymbol{x}^{(k)}+\boldsymbol{f}$ 是收敛的，即

$$\lim _{k \rightarrow \infty} x^{(k)}=x^{*}$$

且 $\boldsymbol{x}^{*}=\boldsymbol{B} \boldsymbol{x}^{*}+\boldsymbol{f}$

由式 $\boldsymbol{x}^{(k+1)}=\boldsymbol{B} \boldsymbol{x}^{(k)}+\boldsymbol{f}$ 和上式得，

$$\begin{array}{c}
x^{(k+1)}-x^{(k)}=B\left (x^{(k)}-x^{(k-1)}\right) \\
x^{(k+1)}-x^{*}=B\left (x^{(k)}-x^{*}\right)
\end{array}$$

利用向量和矩阵范数的性质得，

$$\begin{array}{c}
\left\|x^{(k+1)}-x^{*}\right\| \leq\|B\| \cdot\left\|x^{(k)}-x^{*}\right\| \\
\left\|x^{(k+1)}-x^{(k)}\right\| \leq\|B\| \cdot\left\|x^{(k)}-x^{(k-1)}\right\|
\end{array}$$


反复利用，得

$$\left\|x^{(k+1)}-x^{(k)}\right\| \leq\|B\|^{k-1} \cdot\left\|x^{(1)}-x^{(0)}\right\|
$$

有

$$\begin{aligned}
\left\|x^{(k)}-x^{*}\right\| & =\left\|x^{(k)}-x^{(k+1)}+x^{(k+1)}-x^{*}\right\| \\
& \leq\left\|x^{(k+1)}-x^{(k)}\right\|+\left\|x^{(k+1)}-x^{*}\right\| \\
& \leq\|B\| \cdot\left\|x^{(k)}-x^{(k-1)}\right\|+\|B\| \cdot\left\|x^{(k)}-x^{*}\right\|
\end{aligned}$$

因为 $\|B\|<1,1-\|B\|>0$，所以

$$\left\|x^{(k)}-x^{*}\right\| \leq \frac{\|B\|}{1-\|B\|}\left\|x^{(k)}-x^{(k-1)}\right\|$$

在实际计算时，可将 $\left\|x^{(k)}-x^{(k-1)}\right\|<\varepsilon$ 作为终止计算得条件。

### 定理 3.6

若线性方程组 $A x=b$ 的系数矩阵为严格对角占优或不可约对角占优矩阵，则雅可比迭代法和高斯-塞德尔迭代法收敛。

### 定理 3.7

若线性方程组 $A x=b$ 的系数矩阵 $A$ 对称正定，则高斯-塞德尔迭代法收敛，若 $A$ 对称正定，$2 D-A$ 也对称正定 ($D$ 为 $A$ 的对角元组成的对角阵，$2 D-A$ 与 $A$ 只是非对角元的符号不同) 则雅可比迭代法收敛；若 $A$ 对称正定，而 $2 D-A$ 非正定，则雅可比迭代法不收敛。

# 函数插值与函数逼近

## 拉格朗日插值

### $n$ 阶拉格朗日插值

已知 $n+1$ 个点 $\left (x_{i}, y_{i}\right), i=0,1, \cdots, n$，构造 $n$ 次插值多项式 $L_{n}(x)$ 使

$$L_{n}\left (x_{i}\right)=y_{i} \quad (i=0,1,2, \cdots, n)$$

用插值基函数的方法，可设

$$L_{n}(x)=\sum_{i=0}^{n} y_{i} l_{i}(x)$$

式中，$l_{i}(x)$ 称为关于 $x_{0}, x_{1}, \cdots, x_{n}$ 的插值基函数，它满足条件

$$l_{i}\left (x_{j}\right)=\left\{\begin{array}{ll}
1 & j=i \\
0 & j \neq i
\end{array}\right.$$

这表明，除 $x_{i}$ 外的所有节点都是 $l_{i}(x)$ 的零点，故

$$l_{i}(x)=c \prod_{\substack{j=0 \\ j \neq i}}^{n}\left (x-x_{j}\right)$$

再由条件 $l_{i}\left (x_{i}\right)=1$ 确定其系数 $c$，结果为：

$$l_{i}(x)=\frac{\left (x-x_{0}\right) \cdots\left (x-x_{i-1}\right)\left (x-x_{i+1}\right) \cdots\left (x-x_{n}\right)}{\left (x_{i}-x_{0}\right) \cdots\left (x_{i}-x_{i-1}\right)\left (x_{i}-x_{i+1}\right) \cdots\left (x_{i}-x_{n}\right)}=\prod_{\substack{j=0 \\ j \neq i}}^{n} \frac{x-x_{j}}{x_{i}-x_{j}}$$

$n$ 次插值多项式 $L_{n}(x)$ 为

$$L_{n}(x)=\sum_{i=0}^{n}\left (\prod_{\substack{j=0 \\
j \neq i}}^{n} \frac{x-x_{j}}{x_{i}-x_{j}}\right) y_{i}$$

每个插值基函数 $l_{i}(x)$ 都是 $n$ 次的，$L_{n}(x)$ 的次数不会超过 $n$，且

$$L_{n}\left (x_{k}\right)=\sum_{i=0}^{n} l_{i}\left (x_{k}\right) y_{i}=y_{k}$$

所以 $L_{n}(x)$ 满足插值条件。

### 插值余项与误差估计

若 $f (x)$ 在 $[a, b]$ 内的插值多项式为 $L_{n}(x)$，则称 $R_{n}(x)=f (x)-   L_{n}(x)$ 为 $L_{n}(x)$ 的插值余项，也称误差。

### 定理 4.1

设 $f (x)$ 在 $[a, b]$ 内的 $n+1$ 阶导数连续，记为 $f (x) \in C^{n+1}[a, b]$，且 $f (x)$ 在互异节点 $a \leq x_{0}<x_{1}<\cdots<   x_{n} \leq b$ 的函数值为 $y_{0}, y_{1}, \cdots, y_{n}$ 若满足插值条件 $L_{n}\left (x_{i}\right)=   y_{i}(i=0,1,2, \cdots, n)$ 的插值多项式为 $L_{n}(x)$，则对 $\forall x \in[a, b]$ 有

$$\begin{array}{l}
R_{n}(x)=f (x)-L_{n}(x) \\
=\frac{f^{(n+1)}(\xi)}{(n+1) !} \prod_{j=0}^{n}\left (x-x_{j}\right)=\frac{f^{(n+1)}(\xi)}{(n+1) !} \omega_{n+1}(x)
\end{array}$$

式中 $a<\xi<b, \omega_{n+1}=\prod_{j=0}^{n}\left (x-x_{j}\right)$。 

设 $\left|f^{(n+1)}(\xi)\right| \leq \max _{a \leq x \leq b}\left|f^{(n+1)}(x)\right| \triangleq M_{n+1}$，于是得到

$$
\left|R_{n}(x)\right| \leq \frac{M_{n+1}}{(n+1) !}\left|\prod_{j=0}^{n}\left (x-x_{j}\right)\right|$$ 
- $n=1$ 时，$\left|R_{1}(x)\right| \leq \frac{M_{2}}{2 !}\left|\prod_{j=0}^{1}\left (x-x_{j}\right)\right| \leq \frac{M_{2}}{8}\left (x_{1}-x_{0}\right)^{2}$。
- $n=2$ 时，$\left|R_{2}(x)\right| \leq \frac{M_{3}}{3 !}\left|\prod_{j=0}^{2}\left (x-x_{j}\right)\right|$。

---

若令 $w_{n+1}(x)=\left (x-x_{0}\right)\left (x-x_{1}\right) \cdots\left (x-x_{n}\right)$，则

$$\widetilde{w}_{n+1}\left (x_{i}\right)=\left (x_{i}-x_{0}\right)\left (x_{i}-x_{1}\right) \cdots\left (x_{i}-x_{n-1}\right)\left (x_{i}-x_{n-2}\right) \cdots\left (x_{i}-x_{n}\right)$$

基函数 $l_{i}(x)$ 可写为

$$l_{i}(x)=\frac{w_{n+1}(x)}{\left (x-x_{i}\right) \widetilde{w}_{n+1}\left (x_{i}\right)}$$

拉格朗日插值多项式可写为

$$L_{n}(x)=\sum_{i=0}^{n} \frac{w_{n+1}(x)}{\left (x-x_{i}\right) \tilde{w}_{n+1}\left (x_{i}\right)} y_{i}$$

余项公式  R_{n}(x)  可写为

$$R_{n}(x)=\frac{f^{n+1}(\varepsilon)}{(n+1) !} w_{n+1}(x)$$

---

对于插值多项式 $L_{n}(x)$，它除了满足插值条件外，与 $f (x)$ 再没有任何联系；而对于余项 $R_{n}(x)$，它除了与 $f (x)$ 本身有联系外，它还与 $f (x)$ 的 $n+1$ 阶导数 $f^{n+1}(\varepsilon)$ 有联系，所以余项 $R_{n}(x)$ 与 $f (x)$ 的联系比插值函数 $L_{n}(x)$ 与 $f (x)$ 的联系紧密

---

由余项公式可知，当函数 $f (x)$ 是不超过 $n$ 次的多项式时，由于 $f^{n+1}(\varepsilon)=0$，从而 $R_{n}(x)=0$，因此 $f (x) \equiv L_{n}(x)$。这说明，如果 $f (x)$ 是不超过 $n$ 次的多项式，那么取 $n+1$ 个互异节点的 $n$ 次插值多项式就一定是它本身。特别的，当 $f (x) \equiv 1$ 时，得恒等式 $\sum_{i=0}^{n} l_{i}(x) \equiv 1$ 

---

满足插值条件式的插值多项式存在且唯一，因此，余项定理不仅对拉格朗日插值多项式成立，而且对满足 $p_{n}\left (x_{i}\right)=y_{i}$ 的任何其他形式的插值多项式也恒成立

---

余项定理只有在 $f (x)$ 高阶导数存在时才能应用，$\left|R_{n}(x)\right|$ 的大小除了与 $M_{n+1}$ 有关外，还与因子 $\left|\prod_{j=0}^{n}\left (x-x_{j}\right)\right|$ 有关，为了使 $R_{n}(x)$ 尽量小，显然要尽可能地选取靠近插值点 $x$ 的若干个插值节点

---

如果函数 $f (x)$ 只是以函数表的形式给出的，而没有具体的解析式，则无法估计 $\left|f^{n+1}(x)\right|$ 的上界 $M_{\mathrm{n}+1}$，从而不能直接应用最大值估计。这时就必须用事后误差估计的方法来估计误差，所谓事后误差估计，就是直接用计算结果来估计误差的方法

例如：有 3 个插值节点 $x_{0} ， x_{1} ， x_{2}$，可首先用 $x_{0} , x_{1}$ 进行线性插值，可求出 $f (x)$ 的一个插值函数 $L_{1}(x)$，再用 $x_{0} , x_{2}$ 进行线性插值，求出 $f (x)$ 的另一个插值函数 $\overline{L_{1}}(x)$，由余项式得

$$\begin{array}{l}
f (x)-L_{1}(x)=\frac{f^{\prime \prime}\left (\varepsilon_{1}\right)}{2}\left (x-x_{0}\right)\left (x-x_{1}\right) \\
f (x)-\overline{L_{1}}(x)=\frac{f^{\prime \prime}\left (\varepsilon_{2}\right)}{2}\left (x-x_{0}\right)\left (x-x_{2}\right)
\end{array}$$

若 $f^{\prime \prime}(x)$ 在插值区间 $[a, b]$ 内变化不大，可认为 $f^{\prime \prime}\left (\varepsilon_{1}\right) \approx   f^{\prime \prime}\left (\varepsilon_{2}\right)$，于是将上述两式相除得

$$\frac{f (x)-L_{1}(x)}{f (x)-\overline{L_{1}}(x)} \approx \frac{x-x_{1}}{x-x_{2}}$$

简化整理后得

$$\begin{array}{l}
\left|f (x)-L_{1}(x)\right| \approx\left|\frac{x-x_{1}}{x-x_{2}}\left (L_{1}(x)-\overline{L_{1}}(x)\right)\right| \\
\leq\left|\frac{x-x_{1}}{x-x_{2}}\right|\left|L_{1}(x)-\overline{L_{1}}(x)\right|
\end{array}$$

---

尽管抛物插值的精度比线性插值好，但并不是插值多项式的次数越高越好，当次数过大时会存在数值不稳定现象，当 $n \rightarrow \infty$ 时，插值函数 $L_{n}(x)$ 不一定收敛到被插函数 $f (x)$

高次插值不收敛的现象称作龙格现象

### 定义 4.2

设 $f (x)$ 在给定的 $n+1$ 个互异节点上的函数值为: $f\left (x_{i}\right)=y_{i}(i=   0,1,2, \cdots, n)$，$S_{1}(x)$ 为区间 $[a, b]$ 内的函数，如果 $S_{1}(x)$ 满足下列条件:
* *$S_{1}(x)$ 是在区间 $[a, b]$ 内的每个小区间 $\left[x_{i}, x_{i+1}\right](i=0,1,2, \cdots, n)$ 内的线性函数
* $S_{1}\left (x_{i}\right)=y_{i}(i=0,1,2, \cdots, n)$ 
* $S_{1}(x)$ 是插值区间 $[a, b]$ 内的连续函数

则称 $S_{1}(x)$ 是插值区间 $[a, b]$ 内的分段线性插值函数

分段线性插值的几何意义: 在每个小区间 $\left[x_{i}, x_{i+1}\right](i=   0,1,2, \cdots, n)$ 内作连续插值点 $\left (x_{i}, y_{i}\right)$ 与 $\left (x_{i+1}, y_{i+1}\right)$ 的直线

函数 $S_{1}(x)$ 在区间 $\left[x_{i-1}, x_{i}\right](i=1,2, \cdots, n)$ 内的表达式为

$$
\begin{array}{l}
S_{1}(x)&=\frac{x-x_{i}}{x_{i-1}-x_{i}} y_{i-1}+\frac{x-x_{i-1}}{x_{i}-x_{i-1}} y_{i}\\
&=l_{i-1}(x) y_{i-1}+l_{i}(x) y_{i} \quad\left (x_{i-1} \leq x \leq x_{i}\right)
\end{array}
$$

函数 $S_{1}(x)$ 在区间 $\left[x_{i}, x_{i+1}\right](i=0,1,2, \cdots, n-1)$ 内的表达式为

$$S_{1}(x)=\frac{x-x_{i+1}}{x_{i}-x_{i+1}} y_{i}+\frac{x-x_{i}}{x_{i+1}-x_{i}} y_{i+1}=l_{i}(x) y_{i}+l_{i+1}(x) y_{i+1}\left (x_{i} \leq x \leq x_{i+1}\right)$$

如果用基函数表示，则 $S_{1}(x)$ 在插值区间 $[a, b]$ 内的表达式可统一表示为

$$
S_{1}(x)=\sum_{i=0}^{n} l_{i}(x) y_{i}$$

$$
l_{i}(x)=\left\{\begin{array}{cl}
\frac{x-x_{i-1}}{x_{i}-x_{i-1}} & x_{i-1} \leq x \leq x_{i}(i=0 \text { 略去 }) \\
\frac{x-x_{i+1}}{x_{i}-x_{i+1}} & x_{i}<x \leq x_{i+1}(i=n \text { 略去 }, i=0 \text { 加等号 }) \\
0 & x \in[a, b]-\left[x_{i-1}, x_{i+1}\right]
\end{array}\right.$$

## 牛顿插值

### 定义 4.3

设 $f (x)$ 在互异节点 $x_{0}, x_{1}, \cdots, x_{n}$ 上的函数值为 $f\left (x_{0}\right), f\left (x_{1}\right), \cdots, f\left (x_{n}\right)$，

$f\left (x_{0}, x_{1}\right)=\frac{f\left (x_{1}\right)-f\left (x_{0}\right)}{x_{1}-x_{0}}$ 为 $f (x)$ 关于 $x_{0}, x_{1}$ 的一阶差商

$f\left (x_{0}, x_{1}, x_{2}\right)=\frac{f\left (x_{1}, x_{2}\right)-f\left (x_{0}, x_{1}\right)}{x_{2}-x_{0}}$ 为 $f (x)$ 关于 $x_{0}, x_{1}$，$x_{2}$ 的二阶差商

$f\left (x_{0}, x_{1}, \ldots, x_{n}\right)=\frac{f\left (x_{1}, x_{2}, \ldots, x_{n}\right)-f\left (x_{0}, x_{1}, \ldots, x_{n-1}\right)}{x_{n}-x_{0}}$ 为 $f (x)$ 关于 $x_{0}$，$x_{1}, \ldots, x_{n}$ 的 $n$ 阶差商

补充定义函数值 $f\left (x_{i}\right)$ 为 $f (x)$ 关于 $x_{i}$ 的零阶差商

差商的对称性: $k$ 阶差商可表示为函数值 $f\left (x_{0}\right), f\left (x_{1}\right), \ldots, f\left (x_{k}\right)$ 的线性组合

表明 $f\left (x_{0}, x_{1}, \ldots, x_{k}\right)$ 与节点排列次序无关

如果 $f\left (x, x_{0}, x_{1}, \ldots, x_{k}\right)$ 是 $x$ 的 $m$ 次多项式，则 $f\left (x, x_{0}, x_{1}, \ldots, x_{k}, x_{k+1}\right)$ 是 $x$ 的 $(m-1)$ 次多项式。由于

$$f\left (x, x_{0}, x_{1}, \ldots, x_{k}, x_{k+1}\right)=\frac{f\left (x, x_{0}, \ldots, x_{k}\right)-f\left (x_{0}, x_{1}, \ldots, x_{k+1}\right)}{x-x_{k+1}}$$

右端分子为 $x$ 的 $m$ 次多项式，且当 $x=x_{k+1}$ 时，分子为 $0$，所以分子含有 $\left (x-x_{k+1}\right)$ 的因子，与分母相约后得 $(m-1)$ 次多项式若 $f (x) \in C^{n}[a, b]$，且 $x_{i} \in[a, b], (i=0,1, \ldots, n)$ 互异，则有

$$f\left (x_{0}, x_{1}, \ldots, x_{n}\right)=\frac{f^{(n)}(\xi)}{n !} \quad (\xi \in (a, b))$$

此性质可由罗尔 (Rolle)定理证明

#### 牛顿插值多项式的推导

根据差商定义，把 $x$ 看成在 $[a, b]$ 内一点，可得

$$\begin{array}{c}
f (x)=f\left (x_{0}\right)+f\left (x, x_{0}\right)\left (x-x_{0}\right) \\
f\left (x, x_{0}\right)=f\left (x_{0}, x_{1}\right)+f\left (x, x_{0}, x_{1}\right)\left (x-x_{1}\right) \\
\cdots \\
f\left (x, x_{0}, \cdots, x_{n-1}\right)=f\left (x_{0}, x_{1}, \cdots, x_{n}\right)+f\left (x, x_{0}, \cdots, x_{n}\right)\left (x-x_{n}\right)
\end{array}$$

只要依次把后一式代入前一式，就得到

$$\begin{array}{l}
f (x)=f\left (x_{0}\right)+f\left (x_{0}, x_{1}\right)\left (x-x_{0}\right)+f\left (x_{0}, x_{1}, x_{2}\right)\left (x-x_{0}\right)\left (x-x_{1}\right)+\cdots+ \\
f\left (x_{0}, x_{1}, \cdots, x_{n}\right)\left (x-x_{0}\right)\left (x-x_{1}\right) \cdots\left (x-x_{n-1}\right)+f\left (x, x_{0}, \cdots, x_{n}\right) \omega_{n+1}(x) \\
\quad=N_{n}(x)+R_{n}(x)
\end{array}$$

式中

$$\begin{array}{c}
N_{n}(x)=f\left (x_{0}\right)+f\left (x_{0}, x_{1}\right)\left (x-x_{0}\right)+\cdots+f\left (x_{0}, x_{1}, \cdots, x_{n}\right)(x- \\
\left. x_{0}\right)\left (x-x_{1}\right) \cdots\left (x-x_{n-1}\right) \\
R_{n}(x)=f (x)-N_{n}(x)=f\left (x, x_{0}, \cdots, x_{n}\right) \omega_{n+1}(x) \\
\omega_{n+1}(x)=\left (x-x_{0}\right)\left (x-x_{1}\right) \cdots\left (x-x_{n}\right)
\end{array}$$

由于 $\omega_{n+1}\left (x_{i}\right)=0 (i=0,1,2, \cdots, n)$，因此 $R_{n}\left (x_{i}\right)=0$，于是 $N_{n}\left (x_{i}\right)=f\left (x_{i}\right)(i=0,1, \cdots, n)$，满足插值条件，且次数不超过 $n$ 插值余项对 $f (x)$ 是由离散点给出的或 $f (x)$ 导数不存在时均适用

牛顿插值公式中每增加一个插值节点，只需在原牛顿插值公式中增添一项就可形成高一次的插值公式，因此，它具有递推性质

$$\begin{array}{l}
N_{n+1}(x) 
=N_{n}(x)+\left (x-x_{0}\right)\left (x-x_{1}\right) \cdots\left (x-x_{n}\right) f\left (x_{0}, x_{1}, \cdots, x_{n+1}\right)
\end{array}$$

其中 $N_0(x)=f(x_0)$

牛顿插值公式中各项的系数就是函数 $f (x)$ 的各阶差商

$$f\left (x_{0}\right), f\left (x_{0}, x_{1}\right), \cdots, f\left (x_{0}, x_{1}, \cdots, x_{n}\right)
$$

因此，在构造牛顿插值公式时，先列差商表

## 埃尔米特插值

在节点上与原来的函数相等且节点上的各阶导数也相等的插值，称为埃尔米特 (Hermite) 插值

已知函数在两个互异节点 $x_{0}, x_{1}$  上的函数值

$$f\left (x_{0}\right)=y_{0}, f\left (x_{1}\right)=y_{1}$$

一阶导数值 $f^{\prime}\left (x_{0}\right)=m_{0}, f^{\prime}\left (x_{1}\right)=m_{1}$，求一个三次插值多项式 $H (x)$，使其满足下式

$$\left\{\begin{array}{c}
H\left (x_{0}\right)=y_{0}, H\left (x_{1}\right)=y_{1} \\
H^{\prime}\left (x_{0}\right)=m_{0}, H^{\prime}\left (x_{1}\right)=m_{1}
\end{array}\right.$$

这样的 $H (x)$ 称为两点三次埃尔米特插值多项式

采用构造差值基函数的方法，可设

$$H (x)=h_{0}(x) y_{0}+h_{1}(x) y_{1}+H_{0}(x) m_{0}+H_{1}(x) m_{1}$$

先求 $h_{0}(x)$，由于 $h_{0}\left (x_{1}\right)=h_{0}^{\prime}\left (x_{1}\right)=0$，所以 $h_{0}(x)$ 中必有 $\left (x-x_{1}\right)^{2}$，且 $h_{0}(x)$ 最多是一个三次多项式，因此可设

$$h_{0}(x)=\left (a+b\left (x-x_{0}\right)\right)\left (\frac{x-x_{1}}{x_{0}-x_{1}}\right)^{2}$$

利用 $h_{0}\left (x_{0}\right)=1$ 得 $a=1$，为确定 $b$，对 $h_{0}(x)$ 求导数，再利用 $h_{0}^{\prime}\left (x_{0}\right)=0$，得 $b=\frac{-2}{x_{0}-x_{1}}$，于是得

$$h_{0}(x)=\left (1+2 \frac{x-x_{0}}{x_{1}-x_{0}}\right)\left (\frac{x-x_{1}}{x_{0}-x_{1}}\right)^{2}$$

由对称性，将 $x_{0}, x_{1}$ 互换可得

$$h_{1}(x)=\left (1+2 \frac{x-x_{1}}{x_{0}-x_{1}}\right)\left (\frac{x-x_{0}}{x_{1}-x_{0}}\right)^{2}$$

接下来求 $H_{0}(x)$，由于 $H_{0}\left (x_{0}\right)=H_{0}\left (x_{1}\right)=0$ 且 $H_{0}^{\prime}\left (x_{1}\right)=0$，故 $H_{0}(x)$ 中必有因式 $\left (x-x_{0}\right)\left (x-x_{1}\right)^{2}$。由于 $H_{0}(x)$ 是一个不超过三次的多项式，于是可设

$$H_{0}(x)=a\left (x-x_{0}\right)\left (\frac{x-x_{1}}{x_{0}-x_{1}}\right)^{2}$$

式中，$a$ 是常数。为确定 $a$，利用 $H_{0}^{\prime}\left (x_{0}\right)=1$，可得 $a=1$

$$H_{0}(x)=\left (x-x_{0}\right)\left (\frac{x-x_{1}}{x_{0}-x_{1}}\right)^{2}$$

由对称性，将  x_{0}, x_{1}  互换可得

$$H_{1}(x)=\left (x-x_{1}\right)\left (\frac{x-x_{0}}{x_{1}-x_{0}}\right)^{2}$$

将上述 4 个基函数 $h_{0}(x)$，$h_{1}(x)$，$H_{0}(x)$，$H_{1}(x)$ 即可求出 $H (x)$ 

## 样条函数插值

### 定义 4.4

设在插值区间 $[a, b]$ 内给出一组互异节点 $a \leq x_{0}<   x_{1}<\cdots<x_{n} \leq b$，若函数 $\mathrm{S}(x)$ 满足以下条件:

1. $S (x) \in C^{2}[a, b]$ , 即 $S (x)$ 在 $[a, b]$ 内为二阶导数连续的函数

2. $S (x)$ 在每个小区间 $\left[x_{i}, x_{i+1}\right](i=0,1,2, \cdots, n)$ 内是三次多项式

3. 若  S (x)  在节点上还满足插值条件:$$S\left (x_{i}\right)=f\left (x_{i}\right) \quad (i=0,1,2, \cdots, n)$$

则称 $S (x)$ 是插值区间 $[a, b]$ 内的三次样条插值函数

在每个小区间 $\left[x_{i}, x_{i+1}\right]$ 内是三次多项式，有 4 个待定系数，由于在插值区间 $[a, b]$ 共有 $n$ 个小区间，故 $S (x)$ 有 $4 n$ 个待定系数。由条件 1可知，$S (x)$ 在 $(n-1)$ 个内节点上应该满足

$$\left\{\begin{array}{c}
S\left (x_{i}-0\right)=S\left (x_{i}+0\right) \\
S^{\prime}\left (x_{i}-0\right)=S^{\prime}\left (x_{i}+0\right) \\
S^{\prime \prime}\left (x_{i}-0\right)=S^{\prime \prime}\left (x_{i}+0\right)
\end{array}\right.$$

它给出了 $3 (n-1)$ 个条件，再加上条件 3 给出的 $(n+1)$ 个条件，共 $(4 n-2)$ 个条件，求解 $S (x)$ 仍缺两个条件，所以要补充两个边界条件。第一边界条件: $S^{\prime}\left (x_{0}\right)=f_{0}^{\prime}, S^{\prime}\left (x_{n}\right)=f^{\prime}{ }_{n}$ 

第二边界条件: $S^{\prime \prime}\left (x_{0}\right)=f^{\prime \prime}{ }_{0}, S^{\prime \prime}\left (x_{n}\right)=f^{\prime \prime}{ }_{n}$ , 特别地，当 $S^{\prime \prime}\left (x_{0}\right)=   S^{\prime \prime}\left (x_{n}\right)=0$ 时，称为自然边界条件

第三边界条件：当 $f (x)$ 为周期函数时，因为 $f\left (x_{0}\right)=f\left (x_{n}\right)$，此时 $S\left (x_{0}\right)=S\left (x_{n}\right)=f\left (x_{0}\right)$，并且 $S^{\prime}\left (x_{0}+0\right)=S^{\prime}\left (x_{n}-0\right)$, $S^{\prime \prime}\left (x_{0}+0\right)=   S^{\prime \prime}\left (x_{n}-0\right)$，这时，$S (x)$ 成为周期样条函数

三次样条插值函数的求法

设 $S (x)$ 在节点 $x_{i}$ 处的一阶导数为 $m_{i}$，即

$$S^{\prime}(x)=m_{i}(i=0,1,2, \cdots, n)$$

将 $S (x)$ 表示成整个区间内的分段两点三次埃尔米特插值多项式，当 $x \in\left[x_{i}, x_{i+1}\right]$，且 $h_{i}=x_{i+1}-x_{i}$ 时，有

$$\begin{array}{l}
S (x) \\
=\left (1+2 \frac{x-x_{i}}{h_{i}}\right)\left (\frac{x-x_{i+1}}{-h_{i}}\right)^{2} y_{i}+\left (1+2 \frac{x-x_{i+1}}{-h_{i}}\right)\left (\frac{x-x_{i}}{h_{i}}\right)^{2} y_{i+1}+(x \\
\left.-x_{i}\right)\left (\frac{x-x_{i+1}}{-h_{i}}\right)^{2} m_{i}+\left (x-x_{i+1}\right)\left (\frac{x-x_{i}}{h_{i}}\right)^{2} m_{i+1} \\
=\frac{\left[h_{i}+2\left (x-x_{i}\right)\right]\left (x-x_{i+1}\right)^{2}}{h_{i}{ }^{3}} y_{i}+\frac{\left[h_{i}-2\left (x-x_{i+1}\right)\right]\left (x-x_{i}\right)^{2}}{h_{i}{ }^{3}} y_{i+1} \\
+\frac{\left (x-x_{i}\right)\left (x-x_{i+1}\right)^{2}}{h_{i}{ }^{2}} m_{i}+\frac{\left (x-x_{i+1}\right)\left (x-x_{i}\right)^{2}}{h_{i}{ }^{2}} m_{i+1}
\end{array}$$

对 $S (x)$ 求二次导数，并整理得

$$\begin{array}{c}
S^{\prime \prime}(x)=\frac{6 x-2 x_{i}-4 x_{i+1}}{h_{i}{ }^{2}} m_{i}+\frac{6 x-4 x_{i}-2 x_{i+1}}{h_{i}{ }^{2}} m_{i+1} \\
+\frac{6\left (x_{i}+x_{i+1}-2 x\right)}{h_{i}{ }^{3}}\left (y_{i+1}-y_{i}\right) \quad\left (x \in\left[x_{i}, x_{i+1}\right]\right)
\end{array}$$

于是

$$\lim _{x \rightarrow x_{i}+0} S^{\prime \prime}(x)=-\frac{4}{h_{i}} m_{i}-\frac{2}{h_{i}} m_{i+1}+\frac{6}{h_{i}{ }^{2}}\left (y_{i+1}-y_{i}\right)$$

以 $i-1$ 取代 $i$，以 $i$ 取代 $i+1$，可得 $S (x)$ 在 $\left[x_{i-1}, x_{i}\right]$ 内的表达式

$$\lim _{x \rightarrow x_{i}-0} S^{\prime \prime}(x)=\frac{4}{h_{i-1}} m_{i-1}+\frac{2}{h_{i-1}} m_{i}-\frac{6}{h_{i-1}{ }^{2}}\left (y_{i}-y_{i-1}\right)$$

从而有 $2 m_{0}+m_{1}=3 \frac{y_{1}-y_{0}}{h_{0}}-\frac{h_{0}}{2} f_{0}^{\prime \prime}$

$$\lim _{x \rightarrow x_{i}+0} S^{\prime \prime}(x)=\lim _{x \rightarrow x_{i}-0} S^{\prime \prime}(x)$$

得

$$\begin{array}{c}
\frac{1}{h_{i-1}} m_{i-1}+2\left (\frac{1}{h_{i-1}}+\frac{1}{h_{i}}\right) m_{i}+\frac{1}{h_{i}} m_{i+1} \\
=3\left (\frac{y_{i+1}-y_{i}}{h_{i}{ }^{2}}+\frac{y_{i+1}-y_{i}}{h_{i-1}{ }^{2}}\right)(i=1,2, \cdots, n-1)
\end{array}$$

用 $\frac{1}{h_{i-1}}+\frac{1}{h_{i}}$ 即 $\frac{h_{i}+h_{i-1}}{h_{i-1} h_{i}}$ 除式两边，并化简所得方程，得式中:

$$\lambda_{i} m_{i-1}+2 m_{i}+\mu_{i} m_{i+1}=d_{i}(i=1,2, \cdots, n-1)$$

$$\begin{array}{c}
\lambda_{i}=\frac{h_{i}}{h_{i}+h_{i-1}} \quad \mu_{i}=\frac{h_{i-1}}{h_{i}+h_{i-1}} \\
d_{i}=3\left (\mu_{i} \frac{y_{i+1}-y_{i}}{h_{i}}+\lambda_{i} \frac{y_{i}-y_{i-1}}{h_{i-1}}\right)
\end{array}$$

当 $i$ 取遍 $1,2, \cdots, n-1$ 时，得到含有 $(n-1)$ 个方程及 $(n+1)$ 个未知数 $m_{0} ， m_{1} \cdots ， m_{n}$ 的方程组，其中每个方程都含有 $S (x)$ 在相邻三个节点上的一阶导数值节点 $x_{i}$ 处的一阶导数 $m_{i}$

为了确定末知数 $m_{i}(i=1,2, \cdots, n)$，还需要补充两个边界条件，即可以得到关于 $m_{i}$ 的三对角方程

如果问题要求 $S (x)$ 满足第一边界条件，此时, $m_{0}=   f_{0}^{\prime}, m_{n}=f_{n}^{\prime}$ ,于是，可将方程组化为 $\mathrm{n}-1$ 阶方程组

$$\left (\begin{array}{cccccc}
2 & \mu_{1} & & & & \\
\lambda_{2} & 2 & \mu_{2} & & & \\
& & 2 & \mu_{3} & & \\
& & \ddots & \ddots & \ddots & \\
& & & \lambda_{n-2} & 2 & \mu_{n-2}
\end{array}\right)\left (\begin{array}{c}
m_{1} \\
m_{2} \\
m_{3} \\
\vdots \\
m_{n-2} \\
m_{n-1}
\end{array}\right)=\left (\begin{array}{c}
d_{1}-\lambda_{1} f_{0}^{\prime} \\
d_{2} \\
d_{3} \\
\vdots \\
d_{n-2} \\
d_{n-1}-\mu_{n-1} f_{n}^{\prime}
\end{array}\right)$$

如果问题要求 $S (x)$ 满足第二边界条件，此时可以利用第二边界条件, $S^{\prime \prime}\left (x_{0}\right)=f_{0}^{\prime \prime}, S^{\prime \prime}\left (x_{n}\right)=f_{n}^{\prime \prime}$, 分别在 $\left[x_{0}, x_{1}\right]$ 和 $\left[x_{n-1}, x_{n}\right]$ 内建立关于 $m_{0} ， m_{1}$ 和 $m_{n-1}, m_{n}$ 的方程

令 $i=0, x=x_{0}$, 得

$$S^{\prime \prime}\left (x_{0}\right)=-\frac{4}{h_{0}} m_{0}-\frac{2}{h_{0}} m_{1}+\frac{6}{h_{0}^{2}}\left (y_{1}-y_{0}\right)=f_{0}^{\prime \prime}$$

令 $i=n-1, x=x_{n}$，得

$$S^{\prime \prime}\left (x_{n}\right)=\frac{2}{h_{n-1}} m_{n-1}+\frac{4}{h_{n-1}} m_{n}-\frac{6}{h_{n-1}^{2}}\left (y_{n}-y_{n-1}\right)=f_{n}^{\prime \prime}$$

从而有 $m_{n-1}+2 m_{n}=3 \frac{y_{n}-y_{n-1}}{h_{n-1}}-\frac{h_{n-1}}{2} f_{n}^{\prime \prime}$

联立求解可得 $n+1$ 阶方程组

$$\left (\begin{array}{cccccc}
2 & 1 & & & & \\
\lambda_{1} & 2 & \mu_{1} & & & \\
& \lambda_{2} & 2 & \mu_{2} & & \\
& & \ddots & \ddots & \ddots & \\
& & & \lambda_{n-1} & 2 & \mu_{n-1} \\
& & & & 1 & 2
\end{array}\right)\left (\begin{array}{c}
m_{0} \\
m_{1} \\
m_{2} \\
\vdots \\
m_{n-1} \\
m_{n}
\end{array}\right)=\left (\begin{array}{c}
d_{0} \\
d_{1} \\
d_{2} \\
\vdots \\
d_{n-1} \\
d_{n}
\end{array}\right)$$

其中 $d_{0}=3 \frac{y_{1}-y_{0}}{h_{0}}-\frac{h_{0}}{2} f_{0}^{\prime \prime} , d_{n}=3 \frac{y_{n}-y_{n-1}}{h_{n-1}}-\frac{h_{n-1}}{2} f_{n}^{\prime \prime}$

系数矩阵都是严格对角占优的三对角矩阵，可以用追赶法求其唯一的解

## 函数的内积与正交多项式

### 定义 4.5

设 $[a, b]$ 为有限或无限区间，$\rho (x)$ 是定义在 $[a, b]$ 内的非负函数，并且 $\int_{a}^{b} \rho (x) x^{k} d x$ 对 $k=1,2, \cdots$ 均存在。对非负的 $f (x) \in C[a, b]$，

$$\int_{a}^{b} \rho (x) f (x) d x=0$$

时可得 $f (x) \equiv 0$，则称 $\rho (x)$ 为 $[a, b]$ 内的权函数

##### 常见的权函数

- $\rho (x)=1 (-1 \leq x \leq 1)$ 
- $\rho (x)=\frac{1}{\sqrt{1-x^{2}}}(-1 \leq x \leq 1)$ 
- $\rho (x)=e^{-x}(0<x<+\infty)$ 
- $\rho (x)=e^{-x^{2}}(0<x<+\infty)$ 

### 定义 4.6

设 $f (x), g (x) \in C[a, b]$，$\rho (x)$ 为 $[a, b]$ 内的权函数，则称

$$(f, g)=\int_{a}^{b} \rho (x) f (x) g (x) d x$$
为 $f (x), g (x)$ 在区间 $[a, b]$ 内的内积

### 定义 4.7

给定点集 $\left\{x_{i}\right\}(i=0,1,2, \cdots, m)$，各点的权系数 $\left\{\omega_{i}\right\} \quad (i=   0,1,2, \cdots, m)$，称

$$(f, g)=\sum_{i=0}^{m} \omega_{i} f\left (x_{i}\right) g\left (x_{i}\right)$$

为函数 $f (x), g (x)$ 在离散节点 $\left\{x_{i}\right\}(i=0,1,2, \cdots, m)$ 上的内积

### 函数内积的性质

$$\begin{array}{l}
(f, g)=(g, f) \\
\left (c_{1} f+c_{2} g, h\right)=c_{1}(f, h)+c_{2}(g, h) \\
(f, f) \geq 0, \text { 当且仅当 } f \equiv 0 \text { 时， }(f, f)=0
\end{array}$$

### 定义 4.8

设 $f (x), g (x) \in C[a, b]$, $\rho (x)$ 为 $[a, b]$ 内的权函数，若函数的内积

$$(f, g)=\int_{a}^{b} \rho (x) f (x) g (x) d x=0$$

则称 $f (x), g (x)$ 是在 $[a, b]$ 内带权 $\rho (x)$ 的正交

### 定义 4.9

给定点集 $\left\{x_{i}\right\}(i=0,1,2, \cdots, m)$, 各点的权系数 $\left\{\omega_{i}\right\}(i=0,1,2, \cdots, m)$,则内积为

$$(f, g)=\sum_{i=0}^{m} \omega_{i} f\left (x_{i}\right) g\left (x_{i}\right)=0$$


称 $f (x), g (x)$ 是给定点集 $\left\{x_{i}\right\}(i=0,1,2, \cdots, m)$ 上带权 $\omega_{i}(i=0,1,2, \cdots, m)$ 的正交

### 定义 4.10

设函数系 $\left\{\varphi_{0}(x), \varphi_{1}(x), \cdots, \varphi_{k}(x), \cdots\right\}$ 是 $[a, b]$ 内的连续函数。若满足条件

$$\left (\varphi_{k}, \varphi_{j}\right)=\int_{a}^{b} \rho (x) \varphi_{k}(x) \varphi_{j}(x) d x=\left\{\begin{array}{lr}
0 & k \neq j \\
A_{j}>0 & k=j
\end{array}(j, k=0,1,2, \cdots)\right.$$

则称函数系 $\left\{\varphi_{k}(x)\right\}$ 是 $[a, b]$ 内带权 $\rho (x)$ 的正交函数系

### 定义 4.11

设函数系 $\left\{\varphi_{0}(x), \varphi_{1}(x), \cdots, \varphi_{k}(x), \cdots\right\}$ 是 $[a, b]$ 内的连续函数。给定点集 $\left\{x_{i}\right\}(i=0,1,2, \cdots, m)$，各点的权系数 $\left\{\omega_{i}\right\}(i=0,1,2, \cdots, m)$，若满足条件

$$\left (\varphi_{k}, \varphi_{j}\right)=\sum_{i=0}^{m} \omega_{i} \varphi_{k}\left (x_{i}\right) \varphi_{j}\left (x_{i}\right)=\left\{\begin{array}{lr}
0 & k \neq j \\
A_{j}>0 & k=j
\end{array}(j, k=0,1,2, \cdots)\right.$$

则称函数系 $\left\{\varphi_{k}(x)\right\}$ 是给定点集 $\left\{x_{i}\right\}(i=0,1,2, \cdots, m)$ 上带权 $\omega_{i}(i=0,1,2, \cdots, m)$ 的正交函数系

### 定义 4.12

设 $p_{n}(x)$ 是首项系数 $a_{n} \neq 0$ 的 $n$ 次多项式，若多项式序列 $\left\{p_{n}(x)\right\}_{0}^{\infty}$ 满足

$$\left (p_{k}, p_{j}\right)=\int_{a}^{b} \rho (x) p_{k}(x) p_{j}(x) d x=\left\{\begin{array}{lr}
0 & k \neq j \\
A_{j}>0 & k=j
\end{array}\right.$$

则称多项式序列 $\left\{p_{n}(x)\right\}_{0}^{\infty}$ 为 $[a, b]$ 上带权 $\rho (x)$ 的 $n$ 次正交多项式离散节点上的正交多项式系

### 定义 4.13

设 $p_{n}(x)$ 是首项系数 $a_{n} \neq 0$ 的 $n$ 次多项式，若多项式序列 $\left\{p_{n}(x)\right\}_{0}^{\infty}$ 满足

$$\left (p_{k}, p_{j}\right)=\sum_{i=0}^{m} \omega_{i} p_{k}\left (x_{i}\right) p_{j}\left (x_{i}\right)=\left\{\begin{array}{lr}
0 & k \neq j \\
A_{j}>0 & k=j
\end{array}(j, k=0,1,2, \cdots)\right.$$

则称多项式序列 $\left\{p_{n}(x)\right\}_{0}^{\infty}$ 为给定点集 $\left\{x_{i}\right\} \quad (i=0,1,2, \cdots, m)$ 上带权系数 $\omega_{i}   (i=0,1,2, \cdots, m)$ 的 $n$ 次正交多项式

## 最佳一致逼近



## 最佳平方逼近



# 最优化方法

## 凸集和凸函数

## 最优化问题

## 最优化方法


