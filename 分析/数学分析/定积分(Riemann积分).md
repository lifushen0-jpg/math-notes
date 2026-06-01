
## 定义

> [!note]
> 如果一个函数Riemann可积，当存在一个实数J，满足$\forall \epsilon \gt 0, \exists \delta \gt0, 当区间[a,b]上的划分长度||T||\lt\delta时，|\sum_{k=1}^{n}f(\xi_i)\Delta x_i -J|\lt \epsilon$

可以证明：如果函数Riemann可积，则其积分值唯一

> [!tip] 函数在闭区间上Riemann可积的推论 
> 推论1：闭区间上Riemann可积  $\Rightarrow$  闭区间上函数有界
> 推论2：Dirichlet函数不Riemann可积

***
## 可积性判别——Darboux理论

由于Riemann和中 $\xi$ 取值的任意性，一个任意的函数是否可积是难以判断的。于是我们考虑使用区间上的最大最小值对取值进行控制，然后通过对区间上极值的界定来研究可积性
我们定义：  
1. 所有分割上最大值之和为Darboux上和，最小值之和为Darboux下和，分别记为$S(T,f)=\sum_{i=1}^nM_i\Delta x_i$，$s(T,f)=\sum_{i=1}^nm_i\Delta x_i$
2. 单个区间上最大最小值之差为函数振幅
可以证明，Riemann可积 $\iff$ 振幅和趋于零

> [!note] Darboux和的特点
> 1. 当分割细分时，Darboux和的上和不增，下和不减
> 2. 当增加了 p 个分点时，上和的减少与下和的增加都不超过$p(M-m)||T||$(M,m分别为函数在整个区间上的最大、最小值)

> [!tip] Darboux定理
> $$\lim_{||T||\rightarrow 0}S(T,f)=inf(S(T,f))$$
> $$\lim_{||T||\rightarrow 0}s(T,f)=sup(s(T,f))$$
> 这里，我们称$inf_T(S(T,f))$、$sup_T(s(T,f))$分别为 $f$ 的上下积分

> 利用下确界和分割的合并进行估计

> [!tip] 可积性的判定：
> $$Riemann可积 \iff 上下积分相等 \iff 振幅和为0$$
> 第一充要条件：$$lim_{||T||\rightarrow0}\sum_T\omega_i\Delta_i=0$$
> 第二充要条件：$$\forall \epsilon \gt0,\exists 划分T: \sum_T\omega_i\Delta_i\lt\epsilon$$
> 第三充要条件：$$\forall \epsilon, \eta，\exists 分化T:\sum_{\omega_A\geq\eta}|A|\lt\epsilon$$（A是划分后的区间，|A|表示区间长度）

第一充要条件要求划分$T$的任意性，故而常作为已知可积的推论
反观第二充要条件，它只要求存在$T$即可，故而常用于证明可积
第三充要条件常用于证明有着无限个简短点的函数的可积性


> [!example] 可积函数实例
> - 闭区间连续函数Riemann可积
> - 闭区间单调函数Riemann可积
> - 函数在可积区间的子区间上可积
> - 函数在间断点有限的闭区间上可积
> - 函数在间断点零测度的闭区间(几乎处处连续)上可积

> 连续函数的可积性由函数的一致连续性可得
> 几乎处处连续函数的可积性可用[[有限覆盖定理#加强形式]]和积分第三充要条件证明
> 单调函数的可积性由与其区间上的极值在端点处故而振幅求和可消去中间项

> [!tip] Lebesgue 定理
> $$函数在闭区间上Riemann可积\iff函数在该区间上几乎处处连续 $$

> [!note] 零测集
> 集合A称为零测集，如果A满足存在一个开集簇 $I_i$，其元素个数至多可列，且$\forall \epsilon \gt 0: \sum_i |I_i| \lt \epsilon$（$|I_i|$为集合长度）

***
## Riemann积分的性质

### 基本性质

> [!tip] 
> 1. 线性性
> 2. 保号性：$f(x)\geq 0 \Rightarrow \int_a^bf(x)dx \geq 0$
> 3. 保序性：$f(x) \geq g(x) \Rightarrow \int_a^bf(x)dx \geq \int_a^bg(x)dx$
> 4. 可拆分：$\int_a^bf(x)dx=\int_a^cf(x)dx+\int_c^bf(x)dx$

### 积分中值定理

> [!tip] 
> - 第一中值定理：
> 对在$[a,b]$上连续的$f(x)$,
> $$\exists \xi \in [a,b]:f(\xi)=\frac{1}{b-a}\int_a^bf(x)dx$$
> 我们称这个$f(\xi)$为函数在$[a,b]$上的均值
> 推广：
> $f(x),g(x)$在区间$[a,b]$上连续，$g(x)\not=0$，则
> $$\exists \xi \in [a,b]:\int_a^bf(x)g(x)dx=g(\xi)\int_a^bf(x)dx$$
> - 第二中值定理
> f(x)可积，g(x)单调递减且$g(x)\gt0$
> $$\exists \xi \in [a,b]:\int_a^bf(x)g(x)dx=g(a)\int_a^{\xi}f(x)dx$$
> 若g(x)单调增则
> $$\exists \xi \in [a,b]:\int_a^bf(x)g(x)dx=g(b)\int_{\xi}^bf(x)dx $$
> （注意，此处并不假定$f(x),g(x)$的连续性）
> 一般的，有
> $$\exists \xi \in [a,b]:\int_a^bf(x)g(x)dx=g(a)\int_a^{\xi}f(x)dx+g(b)\int_{\xi}^bf(x)dx$$

对于第一中值定理，我们只需要使用连续函数的介值性和积分的保序性即可证明
对于第二中值定理，我给出下面两个证明
### 证明一：古典微元分拆与黎曼和放缩法

针对区间 $[a, b]$ 作任一分割 $P: a = x_0 < x_1 < \dots < x_n = b$。记 $\Delta x_i = x_i - x_{i-1}$，取介点 $\xi_i \in [x_{i-1}, x_i]$。

**1. 变换恒等式（阿贝尔变换的思想）：**
将积分的黎曼和写出，并将 $g(\xi_i)$ 进行增量拆分：
$$
\begin{aligned}
\text{左边} &\approx \sum_{i=1}^n f(\xi_i)g(\xi_i)\Delta x_i \\[1ex]
&= \sum_{i=1}^{n-1} \left( \sum_{k=1}^i f(\xi_k)\Delta x_k \right) [g(\xi_i) - g(\xi_{i+1})] + g(\xi_n) \sum_{k=1}^n f(\xi_k)\Delta x_k
\end{aligned}
$$
由于 $f \in \mathcal{R}[a, b]$，其变上限积分有界，令 $m = \inf \int f$，$M = \sup \int f$。

**2. 单调性放大与夹逼：**
利用 $g(x)$ 的单调递增性（$g(\xi_i) - g(\xi_{i+1}) \le 0$），将中间的累加和放大和缩小：
$$
\begin{aligned}
\sum_{i=1}^n f(\xi_i)g(\xi_i)\Delta x_i 
&\le M \sum_{i=1}^{n-1} [g(\xi_i) - g(\xi_{i+1})] + g(b) M(b-a) \\[1ex]
&= M \cdot g(a) + \text{尾项误差控项}
\end{aligned}
$$
因为 $g(x)$ 单调必可积，令分割的模 $\|P\| \to 0$，则误差项 $\le \varepsilon$。
同理可得下界放缩。令 $\varepsilon \to 0$，由介值定理可得：
$$
g(a) \cdot \inf \int f \le \int_{a}^{b} f(x)g(x)\,dx \le g(b) \cdot \sup \int f
$$
由此即证存在中值点 $\xi \in [a, b]$ 满足定理要求。

---
### 证明二：分段线性逼近与稠密性推广法

[[积分拓展提高#Rerimann 引理 (Riemann Lemma)#稠密子集]]

#### Step 1: 在 $f \in \mathcal{C}[a, b]$ 条件下的证明
对区间 $[a, b]$ 进行 $n$ 等分，通过连接 $g(x)$ 在各分点处的取值，构造一条分段线性（Piecewise Linear）的连续函数序列 $g_n(x)$。

**1. 导数的阶梯化与分部积分：**
由构造知，当 $n \to \infty$ 时，$g_n(x)$ 一致收敛到 $g(x)$，即 $\displaystyle\lim_{n\to\infty} \int_{a}^{b} |g_n(x) - g(x)|\,dx = 0$。
记 $F(x) = \int_{a}^{x} f(t)\,dt$。由于 $g_n(x)$ 分段线性，其导数 $g_n'(x)$ 为阶梯函数（在分点处补足定义为 0），记为 $\tilde{g}_n'$。对各子区间使用分部积分：
$$
\begin{aligned}
\int_{a}^{b} f(x)g_n(x)\,dx 
&= \sum_{k=1}^n \int_{x_{k-1}}^{x_k} F'(x)g_n(x)\,dx \\[1ex]
&= \sum_{k=1}^n \left( \left. F(x)g_n(x) \right|_{x_{k-1}}^{x_k} - \int_{x_{k-1}}^{x_k} F(x)\tilde{g}_n'(x)\,dx \right) \\[1ex]
&= F(b)g(b) - F(a)g(a) - \int_{a}^{b} F(x)\tilde{g}_n'(x)\,dx
\end{aligned}
$$

**2. 积分第一中值定理与子列收敛（致密性）：**
由于 $\tilde{g}_n'(x) \ge 0$，由积分第一中值定理，对每个 $n$ 存在 $\xi_n \in [a, b]$ 使得：
$$
\int_{a}^{b} F(x)\tilde{g}_n'(x)\,dx = F(\xi_n) \int_{a}^{b} \tilde{g}_n'(x)\,dx = F(\xi_n) [g(b) - g(a)]
$$
代入得恒等式：$\int_{a}^{b} f \cdot g_n = F(b)g(b) - F(\xi_n)[g(b) - g(a)]$。
虽然序列 $\{\xi_n\}$ 不一定收敛，但由于其被绑定在紧集 $[a, b]$ 内，根据 **Bolzano-Weierstrass 定理**，必存在收敛子列 $\{\xi_{n_k}\}$，设其极限为 $\xi \in [a, b]$。
因为 $F(x)$ 连续，故 $\displaystyle\lim_{k\to\infty} F(\xi_{n_k}) = F(\xi)$。令 $k \to \infty$ 取极限可得：
$$
\begin{aligned}
\int_{a}^{b} f(x)g(x)\,dx 
&= F(b)g(b) - F(\xi)[g(b) - g(a)] \\[1ex]
&= g(b) [F(b) - F(\xi)] + g(a) F(\xi) \\[1ex]
&= g(a)\int_{a}^{\xi} f(x)\,dx + g(b)\int_{\xi}^{b} f(x)\,dx
\end{aligned}
$$

#### Step 2: 推广至一般的 $f \in \mathcal{R}[a, b]$
由于连续函数空间 $\mathcal{C}[a, b]$ 在黎曼可积空间 $\mathcal{R}[a, b]$ 中关于 $L^1$ 范数稠密，我们能找到连续函数序列 $f_n \in \mathcal{C}[a, b]$ 满足：
$$
\lim_{n\to\infty} \int_{a}^{b} |f_n(x) - f(x)|\,dx = 0 \quad \text{且} \quad \sup_{n} \|f_n\|_\infty \le \|f\|_\infty
$$

利用强有力的 $L^1$ 残差控制链条，可以将一般可积函数与连续序列的误差压制为 0：
$$
\begin{aligned}
\left| \int_{a}^{b} fg - \left( g(a)\int_{a}^{\xi_n} f + g(b)\int_{\xi_n}^{b} f \right) \right|
&\le \left| \int_{a}^{b} fg - \int_{a}^{b} f_n g \right| + \left| \int_{a}^{b} f_n g - \left( g(a)\int_{a}^{\xi_n} f_n + g(b)\int_{\xi_n}^{b} f_n \right) \right| \\
&\quad + \left| g(a)\int_{a}^{\xi_n} (f_n - f) + g(b)\int_{\xi_n}^{b} (f_n - f) \right| \\[1ex]
&\le \|g\|_\infty \int_{a}^{b} |f_n - f| + 0 + (|g(a)| + |g(b)|) \int_{a}^{b} |f_n - f| \xrightarrow{n\to\infty} 0
\end{aligned}
$$
由致密性原理再次对中值点序列取收敛子列，即证对一切黎曼可积函数 $f$ 定理依然成立。

***
### 微积分基本定理

> [!note] 变上限积分
> 将积分上限改为参变量 $x$：$$\phi(x)=\int_a^xf(x)dx$$
> 如此，$\phi(x)$称为变上限积分

> [!tip] 变上限积分有以下性质
> 1. 满足Lipschitz条件
> 由闭区间上的连续函数有界性与积分的可拆性可证
> 2. 一致连续（满足Lipschitz条件的推论）

> [!tip] 微积分基本定理
> 1. $\phi'(x)=f(x)$（微积分基本定理）
> 由一致连续性和定义可证
> 
> 2. $\int_a^b f(x)\,dx = \int_a^b F'(x)\,dx = F(b) - F(a) = F(x)\Big|_a^b$（微积分基本公式）
> 由一致连续性和定义可证
> 亦可由Lagrange中值定理证明
> 
> 3. 若只在有限个点上不满足$F'(x)=f(x)$，则基本公式也成立
> 只需让所有的分割点包括全部的不成立点

***
#### Taylor 公式的积分型余项

先证明一个引理：
> [!note] 
> $$\int_a^bf(x)g^{n+1}(x)\,dx=\sum_{i=0}^n(-1)^{i}f(x)^{i}g^{n-i}(x)\Big|_a^b +(-1)^{n+1}\int_a^bf^{n+1}(x)g(x)dx$$

由此，可以得到：
> [!tip]
> $$R_n(x)=\frac{\int_{x_0}^x(x-t)^{n}f^{(n+1)}(t)\,dt}{n!}$$

> 对 $\int_{x_0}^x(x-t)^{n}f^{(n+1)}(t)$ 运用引理即得

***
## 广义积分

上面的研究只针对于闭区间上有界函数，下面我们考虑将这个理论拓展到更一般的函数，这就是广义积分
广义积分分为两类，一类是无穷积分，另一类是无界函数的积分（也叫瑕积分）

### 无穷积分

我们考虑使用极限的理论将闭区间上的积分拓展定义到无穷

> [!note] 无穷积分
> 积分 $\int_a^{\infty}f(x)\,dx$ 定义为：$\lim_{t\to\infty}\int_a^tf(x)\,dx$

#### 无穷积分收敛性的判别

无穷积分收敛性判别与数项级数收敛判别有许多相似之处，因为无穷积分就像是数项级数的连续形式
[[级数#级数的收敛性]]
两者都可以通过与一致收敛性积分或级数比较进行判别
无穷积分中可以定义绝对收敛 (|f(x)|的收敛性)，其性质与数项级数相同
都有 Cauchy 收敛准则
同样，我们也有积分的 Dirichlet 判别法和 Abel 判别法

> [!tip] 积分的 A-D 判别法
> 对积分 $\int_a^{\infty}f(x)g(x)\,dx$，满足一下情况则收敛
> 1. Dirichlet 判别法：
> - $g(x)$ 单调，$\lim_{x\to\infty}g(x)=0$
> - $F(x)=\lim_a^xf(t)$ 有界
> 2. Abel 判别法
> - $g(x)$ 单调有界
> - $\int_a^{\infty}f(x)\,dx$ 收敛

我们还可以给出以下的必要条件辅助判断

> [!tip] 无穷积分收敛的函数在无穷远处的性质
> 假定 $\int_a^{\infty}$ 收敛
> - 若 $\lim_{x\to\infty}f(x)=A$ 存在，则 $A=0$
> - 若 f(x) 一致连续，则 $\lim_{x\to\infty}f(x)=0$ 

### 瑕积分

对于有界的开区间，我们可以说在同边界的闭区间上几乎处处连续
我们考虑无界开区间
> [!note] 瑕积分
> 设 $f(x)$ 在区间 $[a,b)$ 上连续且在 $a$ 处无界
> $\int_a^bf(x)\,dx=\lim_{x\to b^-}\int_a^xf(t)\,dt$

对于瑕积分的收敛性，我们依然有 Cauchy 收敛准则和比较判别法
技巧性地，我么可以通过倒数换元换元将瑕积分变为无穷积分

 ***
# 习题

> [!question] 
> 证明下面的函数在区间$[0,1]$可积
> $$f(x) = \begin{cases} \frac{1}{x} - \left\lfloor \frac{1}{x} \right\rfloor, & x \in (0,1], \\ 0, & x = 0 \end{cases}$$

> tips1: 有理数为零测集
> tips2: 间断点在0附近高度集中

> [!question]
> 求: $\int_0^{\infty}e^{-x^2}\,dx$

> tips1: $1-x^2\lt e^{-x^2}\lt \frac{1}{1+x^2}$
> tips2: 做积分换元，可得：$\int_0^{\infty}e^{-x^2}\,dx=\frac{1}{\sqrt{n}}\int_0^{\infty}e^{-nx^2}\,dx$

> [!question] 
> 计算：计算$\int_0^{\pi} \frac{1}{a^2\sin^2 x + b^2 \cos^2 x}dx$

> 不难算出: $\int \frac{1}{a^2\sin^2 x + b^2 \cos^2 x}dx=\frac{1}{ab}\arctan (\frac{a}{b}\tan x)$
> 我们注意到，等式的右边在 $x=\frac{\pi}{2}$ 处间断，不能直接带入 0 和 $\pi$ 处的函数值做差
> 应该分段为 $[0,\frac{\pi}{2})$ 和 $(\frac{\pi}{2},\pi]$ 分别做瑕积分然后相加
> 结果为 $\frac{\pi}{ab}$
  



