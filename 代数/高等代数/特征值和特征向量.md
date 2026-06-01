# 研究特征值的目的

## 思路一：

> [!note] 给出算子(operator)的定义
> 我们将映射到自身的线性映射成为算子

为了研究算子，我们希望将其拆解为更加简单的子空间进行研究，并希望并希望这些子空间在线性映射下保持不变(称其为不变子空间)

例如，${0}，V(自己)，ker(T)，Im(T)$ 都是线性空间 V 在变换 T 下的不变子空间(invariant subspace)

以上四个例子是平凡的（trival），下面我们希望研究简单但不平凡（nontrival）的例子

> [!note] 特征值、特征向量
> 如果向量$v\in V$满足：$\exists \lambda \in \mathbb{F}:Tv=\lambda v$，称 $v$ 是线性变换 $T$ 的一个特征向量，$\lambda$ 是其一个特征值

> [!note] 特征子空间
> 集合 $E_{\lambda}=\{v|v\in V 并且 T(v)=\lambda v \}=ker(T-\lambda I_n)$

## 思路二

取定 V 的一组基，对任意一个 V 上的线性算子$\phi \in \mathcal{L}(V)$，可以得到 V 的一个矩阵表示$T(V)$
可以证明，同一个线性变换在不同基下的矩阵表示是相似的

为了研究的方便，我们希望去一组合适的基，使得矩阵表示有尽可能简单的形式，例如对角阵
这样，原来的线性变换的性质就很好研究了

综合以上思路，研究特征值的目的和方法就是研究**矩阵的可对角化**

# 特征值的性质

## 1. 求法
> [!note] 特征多项式
> 记$P(\lambda)=|A-\lambda I_n|$为特征多项式，其根即为矩阵 $A$ 的特征值
> 线性方程组 $(A-\lambda I_n)\alpha =0$ 的解空间即为 $A$ 关于 $\lambda$ 的特征子空间

## 2. 性质

> [!tip] 性质一
> 相似矩阵有相同的特征值（记重数）

> tips1: 
> 这个性质从我们的第二个思路不难看出
> tips2: 
> 严格的证明只需要使用相似矩阵A，B满足$\exists P \in M_{n\times n}且P可逆:B=P^{-1}AP$并带入特征多项式即可得到

> [!tip] 性质二
> 不同的特征值对应的特征向量线性无关

> tip: 将线性变换 $A-\lambda_tI_n$ 作用于特征向量的线性组合可得

> [!note] 推论1
> $$一个n阶方阵可以相似于一个对角阵\iff 这个方阵有n个不同的特征向量$$

> 推论1等价于：
> 矩阵可对角化 $\iff$ 
> 在 $\mathbb{F}^n$ 中有 n 个线性无关向量 $\alpha_1 \cdots \alpha_n$ 和 $\mathbb{F}$ 上的 $n$ 个数 $\lambda_1\cdots\lambda_n$，满足 $A\alpha_1 = \lambda_1\alpha_1\cdots A\alpha_n= \lambda_n\alpha_n$


> [!note] 推论2
> 各特征值对应的特征子空间的和为 V 的直和

> [!tip] 性质三
> 对$\forall f \in F[\mathbb{K}]和T\in\mathcal{L}(V):f(T) 的核空间与像空间在 T 下保持不变$

> tip: 由多项式乘法的可交换性易证

> [!tip] 性质四
> 复数上的有限维线性算子必有特征值

> tips1: 
> 由代数基本定理可得特征方程必有根
> tips2: 
> 记$dimV=n$，那么对于 $V$ 上的一个非零向量 $v$，$v,Tv\ldots T^nv$线性相关，于是可以得到一个非常数n次多项式 $f(x)$，使得$f(T)v=0$，这里 $f(x)$ 的根即为 $T$ 的特征值

> [!tip] 性质五
> 设 n 阶矩阵 $A$ 的全部特征值为 $\lambda_1 \cdots \lambda_n$，$f(x)\in \mathbb{F}[X]$，则 $f(A)$ 的全部特征值为 $f(\lambda_1)\cdots f(\lambda)$

> 先来证明一个引理
> [!note] 任意的复方阵可三角化
> 设 $A \in M_{n \times n}(\mathbb{C})$，它的一个特征值为 $\lambda_1$，对应特征向量为 $\alpha_1$
> 将 $\alpha_1$ 扩充为 $\mathbb{C}_n$ 的一组基 $\{\alpha_1 \cdots  \alpha_n\}$，并由此得到一个可逆矩阵 $P=(\alpha_1 \cdots  \alpha_n)$
> $AP = (A\alpha_1 \cdots  A\alpha_n) = (\alpha_1 \cdots  \alpha_n)\begin{pmatrix}\lambda_1 & * \\ 0 & A_1\end{pmatrix}$
> 有数学归纳法不难证明该引理成立
> 有这个引理知道，如果一个矩阵的全部特征值在数域 $\mathbb{F}$ 上，则它在这个域上可对角化且对角元记为全部特征值
> 由于对角矩阵的乘积仍然是对角矩阵，且对角元为对应位置上的元素相乘
> 那么命题成立。 

有关矩阵三角化的知识，这里有一个定理

> [!note] 三角化的充要条件
> $$数域 F 上的矩阵可上三角化 \iff 其最小多项式的根全部在 F 上$$

> $\Rightarrow$ 显然
> $\Leftarrow$ :
> 使用数学归纳法，假设n-1时成立
> 由于最小多项式的根都在 F 上，设其中一个是 $\lambda$，它对应的特征向量是 $v_1$
> 考虑 $W=V/span(v_1)$，这是 n-1 维的
> 由归纳假设知它可以对角化，对应的基为 $\bar{v_2},\cdots,\bar{v_n}$
> 对应原空间的代表元 $v_2, \cdots,v_n$ 是线性无关的
> 我们知道 $Tv_1=\lambda v_1$，在商空间中 $\bar{T}\bar{v_i}$ 是 $\bar{v_2},\cdots,\bar{v_i}$ 的线性组合，则 $Tv_i$ 是 $v_2,\cdots,v_i$ 的线性组合
> 这说明 $T$ 在这组向量构成的基上是上三角的 


> [!tip] 性质六
> $g(x) \in \mathbb{F}[x],A\in \mathbb{F}_{n\times n}$，则有：$$g(A) = O \Rightarrow g(\lambda) = 0$$
> 其中，$\lambda$ 是 $A$ 的特征值

## 3.特征值的几何重数与代数重数

为了判读一个矩阵是否可对角化，我们引入特征值的几何重数和代数重数的概念

> [!note] 几何重数与代数重数
> 记 $\lambda$ 是线性变换 $T$ 的特征值，$V_{\lambda}$ 是其对应的特征子空间，那么：
> - $dim\{V_{\lambda}\}$ 是 $\lambda$ 的 **几何重数**
> - $\lambda$ 作为特征方程 $|T-\lambda I_V|$ 的根的重根数为其 **代数重数**

> [!tip] 引理
> 几何重数不大于代数重数

> 证明：将特征子空间 $V_{\lambda_0}$ 的基扩张为 $T$ 的一组基，则 $T$ 在这一组基下有如下矩阵表
> 示：
> $$\begin{pmatrix} \lambda I_{dim\,V_{\lambda_0}} & O \\ O & B\end{pmatrix}$$
> 于是，由性质一：$|T-\lambda I_n|=(\lambda-\lambda_0)^{dim\,V_{\lambda_0}}|B-\lambda I_B|$

于是我们可以得到矩阵相似于对角阵的另一个充要条件：

> [!note] 
> $$矩阵相似于对角阵 \iff 所有特征值的几何重数等于代数重数$$

## 4. 特征值与不变子空间

首先，我们很容易证明，每一个特征值对应的特征向量张成的空间使不变子空间
每一个特征值对应的特征子空间是不变子空间

> [!success]
> 特征子空间的每一个子空间都是不变子空间
> 如果有维数不小于2的特征子空间，则矩阵有无限个特征子空间

> 由于线性空间不可能被有限个子空间覆盖，而特征子空间的每个子空间都是不变子空间，于是得证
## 5. 矩阵的特征分解

> [!tip] 特征分解
> 求解矩阵 $P$，使可对角化的矩阵 $A$实现 $P^{-1}AP$ 为对角阵
> 只需要将各个特征值对应的特征向量按序排列，即：
> $$P=\begin{pmatrix} \alpha_1 & \alpha_2 & \cdots & \alpha_n\end{pmatrix}$$
> $$\Lambda=diag\{\lambda_1,\lambda_2\cdots\lambda_n\}=P^{-1}AP $$
> 反过来，$A=P\Lambda P^{-1}$ 成为矩阵 $A$ 的特征分解

# 极小多项式

> [!note] 定义
> 我们称满足 $f(T)=0$ 的次数最低的首一的 $f(x) \in F[x]$ 为线性变换 $T$ 的极小多项式

> 数域 $\mathbb{K}$ 上的全体 n 阶方阵构成一个 n 维线性空间，那么 $A^{n^2},A^{n^2-1}\cdots A,I_n$ 线性相关
> 于是这样的多项式是存在的


在接下来的讨论中，我们假设 $\lambda$ 是矩阵 $A$ 的特征值，$T$ 代表线性映射 $m_T(x)$ 表示极小多项式，$f_T(x)$ 代表 $T$ 的特征多项式
下面我们来研究极小多项式的唯一性

> [!tip] 
> 极小多项式是唯一的

> 首先，使用多项式的带余除法不难发现 $m_T(x) | f(x)$ 如果 $f(T) = 0$
> 于是，如果有两个极小多项式，则它们互相整除，又因为它们首一，故而相等

> [!tip] 极小多项式与特征多项式的联系
> 在数域 $\mathbb{F}$上，矩阵的极小多项式的任意一个素因子都是特征多项式的素因子，其次数不大于特征多项式该素因子的次数

> 证明
> 容易证明，矩阵的每一个特征值都是极小多项式和特征多项式的根，特征多项式的所有根就是矩阵的全部特征值，于是成立

> [!tip] 极小多项式与矩阵的秩
> 矩阵的极小多项式的维数不大于矩阵的秩+1
> $$dim(m(x)) \leq rank(A)+1$$

> 证明
> 我们考虑矩阵在像空间的限制 $A_1 = A|_{Im(A)}$，记 $r = rank(A)$
> 假设矩阵 $A_1$ 的极小多项式为 $m_1(x)$，则 $dim(m_1(x)) \leq r$
> 我们知道：$\forall \alpha \in V，A\alpha \in A_1$
> 那么 $m_1(A)A\alpha=0$
> $m(A)|m_1(A)A$
> 命题得证

## 使用极小多项式研究矩阵的可对角化

为了接下来的研究，我们先给出以下两个定理

> [!note] Cayley-Hamilton 定理
> $$f_T(T)=0$$

> 我们先证明 $T$ 是对角阵的情况$$A = \begin{pmatrix} \lambda_1 & a_{12} & \cdots & a_{1n} \\ & \lambda_2 & \cdots & a_{2n} \\ & & \ddots & \vdots \\ & & & \lambda_n \end{pmatrix},$$
> 主对角线上的元素 $\lambda_1, \lambda_2, \cdots, \lambda_n$ 正好是 $A$ 的全部特征值。将 $A$ 依次作用于标准单位列向量 $e_1, e_2, \cdots, e_n$，可得 $n$ 个等式：$$Ae_1 = \lambda_1 e_1,$$$$Ae_2 = a_{12}e_1 + \lambda_2 e_2,$$$$Ae_i = a_{1i}e_1 + \cdots + a_{i-1,i}e_{i-1} + \lambda_i e_i,$$$$Ae_n = a_{1n}e_1 + \cdots + a_{n-1,n}e_{n-1} + \lambda_n e_n.$$
> 作$$f(x) = (x - \lambda_1)(x - \lambda_2)\cdots(x - \lambda_n),$$注意到 $(A - \lambda_i I_n)(A - \lambda_j I_n) = (A - \lambda_j I_n)(A - \lambda_i I_n)$，只需将 $e_i$ 交换 $(A-\lambda_iI_n)$ 之后，不难算出：$$f(A)e_i = (A - \lambda_1 I_n)(A - \lambda_2 I_n)\cdots(A - \lambda_n I_n)e_i = 0$$对一切 $i = 1, 2, \cdots, n$ 成立，因此 $f(A) = 0$。注意到 $f(x)$ 是 $A$ 的特征多项式。
> 对于任意的矩阵 $A$，它总能复相似于一个对角阵 $B$，而 $f(B)=0$，则 $f(A)=0$.
>
> 证明2：使用伴随矩阵
> 我们知道，矩阵与其伴随矩阵的矩阵乘积为 $det(A)I$
> 那么有：$(\lambda I-A)(\lambda I-A)^* = det(\lambda I -A)I=f(\lambda)I$
> 由伴随阵的定义和 $\lambda$-矩阵的知识可知，$(\lambda I-A)^*$ 可以写成如下形式$$\lambda^{n-1}B_{n-1}+\cdots+\lambda B_1+ B_0$$
> 其中，$B_i$ 为数量矩阵。
> 对比两边，可得 
>  - $B_{n-1} = I$
>  - $B_{n-2}-B_{n-1}A = a_{n-1}$
>  - $\vdots$
>  - $-AB_0 = a_0$
> 将 $\lambda$ 替换为 $A$，则中间项会对应消去，例如 $A^{n-1}B_{n-1}-A^{n-1}B_{n-1}$
> 于是得到 $f(A)=0$


> [!note] 多项式的核分解定理
> 假设**线性变换** $A \in \mathcal{L}(V)$，多项式 $P(x)$ 满足 $P(A)=0$ 且可做以下素因式分解：$P(A)=P_1(A)P_2(A)\cdots P_k(A)$，则
> $$V=Ker(P_1(A))\oplus Ker(P_2(A))\cdots \oplus Ker(P_k(A))$$

> 我们只证明 $P(A) = P_1(A)P_2(A)$ 的情况
> 由裴蜀定理，存在多项式 $u(x),v(x)$，满足 $u(x)P_1(x)+v(x)P_2(x)=1.\tag{1}$
> 那么，由于多项式的可交换性，$\forall \alpha\in V:u(T)P_1(T)\alpha \in Ker(P_2(A))$
> 将裴蜀定理得到的方程中变量换位 $A$，再在两边左乘向量 $\alpha$，即得
> $$V=Ker(P_1(A))+ Ker(P_2(A))$$
> 再者，假设 $\beta \in Ker(P_1(A))\bigcap Ker(P_2(A))$
> 带入裴蜀定理所得方程，即得 $\beta = 0$
> 于是，直和成立

 
> [!success] 特征分解与可对角化
> 如果一个线性空间可以分解为几个线性变换的特征子空间的直和，那么它可以对角化

> 由线性变换的矩阵表示知道，只要取出各个特征子空间的基再组合起来即可

有了以上知识的铺垫，我们可以给出以下定理：

> [!tip] 使用极小多项式判别可对角化
> $$矩阵可对角化 \iff 极小多项式在复数域上无重根$$

> $\Rightarrow$：
> 设矩阵 $A$ 的全部特征值为 $\lambda_1\cdots \lambda_k$ 且 $A$ 可对角化
> 则矩阵 $A$ 相似于对角阵 $B$，$B$ 满足对角线上的元素必为 $A$ 的特征值
> 假设多项式 $P(x)=(x-\lambda_1)\cdots(x-\lambda_k)$
> 由于对角阵的矩阵乘积为对应元素相乘，那么 $P(A) = P(B) =0$
> $\Leftarrow$：
> 使用多项式的核分解定理易知。
 
# 特征值范围的估计

> [!note] 定理 6.4.1
> 设 $A = (a_{ij})_{n \times n}$ 是 $n$ 阶复矩阵，则 $A$ 的特征值在复平面上的下列圆盘（又称戈氏圆盘）中：
> $$|z - a_{ii}| \leq R_i, \quad i = 1, 2, \cdots, n.$$
> 其中，$R_i = \sum_{j=1,j\not = i}^na_{ij}$

> 任取 $A$ 的一个特征值 $\lambda_0$，设 $\xi$ 为属于 $\lambda_0$ 的特征向量，则 $A\xi = \lambda_0\xi$。
> 记 $\xi$ 的第 $i$ 个坐标为 $x_i (i=1,2,\cdots,n)$，将 $A\xi = \lambda_0\xi$ 写成线性方程组：
> $$\begin{cases} a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = \lambda_0x_1, \\ a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = \lambda_0x_2, \\ \vdots \\ a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n = \lambda_0x_n. \end{cases}$$
> 设 $|x_1|, |x_2|, \cdots, |x_n|$ 中 $|x_r|$ 最大，从上式可得$$(\lambda_0 - a_{rr})x_r = a_{r1}x_1 + \cdots + a_{r,r-1}x_{r-1} + a_{r,r+1}x_{r+1} + \cdots + a_{rn}x_n.$$于是$$|\lambda_0 - a_{rr}||x_r| \leq |a_{r1}||x_1| + \cdots + |a_{r,r-1}||x_{r-1}| + |a_{r,r+1}||x_{r+1}| + \cdots + |a_{rn}||x_n|$$$$\leq (|a_{r1}| + \cdots + |a_{r,r-1}| + |a_{r,r+1}| + \cdots + |a_{rn}|)|x_r|,$$此即
> $$|\lambda_0 - a_{rr}||x_r| \leq R_r|x_r|.$$
> 由于 $|x_r| > 0$，故$$|\lambda_0 - a_{rr}| \leq R_r.$$

Practice 1:
$A^3-3A^2 +A= (A-2I)(A-I)A=0$，那么矩阵 A 的特征值只有可能为 0,1,2
再者，由极小多项式的定义知，极小多项式应该整除多项式 $f(x)=(x-2)(x-1)x$，而 $f(x)$ 的每一项都是 1 次的，那么极小多项式无重根

Practice 2:
M 的特征多项式为 $f(x)=(5-\lambda)(3-\lambda)(2-\lambda)^2(1-\lambda)$
如何计算 M 的极小多项式？

Practice 3：
显然，我们可以注意以下两个事实
1. 矩阵 A 适合多项式 $f(x)=x^2-1=(x-1)(x+1)$
2. 如果 $A =\pm I$，则它是对合阵
那么，我们可以知道 :
- A 的特征值只有 $\pm 1$
- 若 A 为纯量阵，那么A的极小多项式为 (x-1)(x+1)，这说明 A 可以对角化

Practice 4:
如果一个矩阵实矩阵 $A$ 的特征多项式在复数域上的全部根为实数，且 $AA^T=A^TA$，那么：$$A 是对称阵$$
Practice 5:
实数上对称矩阵的全部特征值都是实数；实数域上反对称矩阵(斜对称矩阵)的全部特征值是0或纯虚数
> 证明：
> 1. [[内积空间与正交变换#四、酉空间与 Hermite矩阵]]
> 2. 
> 假设 $\lambda$ 是反对称矩阵 $A$ 的特征值，$v$ 是属于 $\lambda$ 的特征向量，那么 $Av=\lambda v$
> 对上式取转置，右乘 $\bar{v}：$$v^TA^T\bar{v} = -v^TA\bar{v} =-\lambda v^T\bar{v}$
> 对上式取共轭，左乘 $v^T$：$v^TA\bar{v}=\bar{\lambda}v^Tv$
> 于是得到 $-\lambda=\bar{\lambda}$
> 于是 $\lambda$ 在虚数轴





