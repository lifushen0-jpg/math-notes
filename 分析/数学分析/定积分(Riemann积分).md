
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

> 对于第一中值定理，我们只需要使用连续函数的介值性和积分的保序性即可证明
> 对于第二中值定理，我们需要使用$f(x)$有界、$f(x)$的变上限积分$F(x)=\int_a^xf(x)dx$ 连续、g(x)的振幅和无限小、$f(x)g(x)$的积分可拆分证明。

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
  



