# Sylow 定理及其应用

## 1. 基本定义

设 $G$ 为有限群，$p$ 为素数，并写成 $$|G|=p^a m,\qquad p\nmid m.$$ 阶为 $p$ 的幂的子群称为 **$p$-子群**；阶恰好为 $p^a$ 的子群称为 **Sylow $p$-子群**。也就是说，Sylow $p$-子群的阶包含了 $|G|$ 中全部的 $p$ 因子。

## 2. 三个 Sylow 定理

1. **存在性：**$G$ 至少有一个 Sylow $p$-子群。
2. **包含与共轭：**设 $P$ 是 Sylow $p$-子群。对任意 $p$-子群 $K$，存在 $g\in G$，使得 $K\le gPg^{-1}$。特别地，任意两个 Sylow $p$-子群互相共轭。
3. **个数限制：**若 $n_p$ 是 Sylow $p$-子群的个数，则 $$n_p\mid m,\qquad n_p\equiv1\pmod p.$$

**第三定理的证明思路** 固定一个 Sylow $p$-子群 $P$。由第二定理，所有 Sylow $p$-子群构成 $P$ 的共轭类，因此 $$n_p=[G:N_G(P)],\qquad N_G(P)=\{g\in G:gPg^{-1}=P\}.$$ 因为 $P\le N_G(P)$ 且 $|P|=p^a$，由 Lagrange 定理得 $n_p\mid m$。

再让 $P$ 以共轭作用在所有 Sylow $p$-子群组成的集合上。每个轨道的大小都是 $p$ 的幂，故非单点轨道的大小都能被 $p$ 整除。唯一的单点轨道是 $\{P\}$：若 $Q$ 在 $P$ 的作用下不变，则 $P$ 规范化 $Q$，从而 $PQ$ 是 $p$-子群；由 $P,Q$ 均为 Sylow $p$-子群可知 $P=Q$。因此 $n_p\equiv1\pmod p$。

**注** Sylow 子群的“最大”指其阶等于 $|G|$ 中最大的 $p$ 的幂；它不一定是唯一的 Sylow $p$-子群。

## 3. 常用推论

### 3.1 Cauchy 定理

**推论** 若素数 $p\mid |G|$，则 $G$ 中存在阶为 $p$ 的元素。

**证明** 由第一 Sylow 定理，$G$ 有阶为 $p^a$ 的子群 $P$，其中 $a\ge1$。取 $b\in P\setminus\{e\}$，由 Lagrange 定理，$\operatorname{ord}(b)=p^k$，其中 $k\ge1$。于是 $b^{p^{k-1}}$ 的阶为 $p$。证毕。

### 3.2 唯一性与正规性

**推论** Sylow $p$-子群 $P$ 唯一，当且仅当 $P\trianglelefteq G$。

**证明** 若 $P$ 唯一，则任意共轭子群 $gPg^{-1}$ 也是 Sylow $p$-子群，故 $gPg^{-1}=P$，即 $P$ 正规。反之，若 $P$ 正规，由第二 Sylow 定理，所有 Sylow $p$-子群都与 $P$ 共轭，因此都等于 $P$。证毕。

特别地，若 $G$ 为交换群，则每个 Sylow $p$-子群都正规，因而唯一。

### 3.3 一个 $pq$ 阶群的判别

**推论** 设 $|G|=pq$，其中 $p,q$ 是不同素数。若 $$p\not\equiv1\pmod q,\qquad q\not\equiv1\pmod p,$$ 则 $G\cong\mathbb Z/(pq)\mathbb Z$。

**证明** 由第三 Sylow 定理，Sylow $p$-子群的个数 $n_p$ 满足 $n_p\mid q$ 且 $n_p\equiv1\pmod p$。题设排除了 $n_p=q$，故 $n_p=1$。同理，Sylow $q$-子群的个数 $n_q=1$。记这两个正规子群为 $P,Q$，则 $|P|=p,\ |Q|=q$，且 $P\cap Q=\{e\}$。由于 $P,Q$ 正规，对 $x\in P,y\in Q$，交换子 $xyx^{-1}y^{-1}$ 同时属于 $P$ 和 $Q$，故 $xy=yx$。又 $|PQ|=pq=|G|$，所以 $G=PQ$。取 $P,Q$ 的生成元 $x,y$，则 $xy$ 的阶为 $pq$，从而 $G$ 是 $pq$ 阶循环群。证毕。

## 4. 例子

### 4.1 循环群 $\mathbb Z/n\mathbb Z$

设 $n=p^a m$ 且 $p\nmid m$。则 $$P=\langle[m]_n\rangle$$ 的阶为 $p^a$，因此是 $\mathbb Z/n\mathbb Z$ 的 Sylow $p$-子群。

**理由** 在加法群 $\mathbb Z/n\mathbb Z$ 中，$[m]_n$ 的阶为 $$\frac{n}{\gcd(n,m)}=\frac{p^a m}{m}=p^a.$$

### 4.2 $\mathrm{GL}_n(\mathbb F_p)$

令 $U_n(\mathbb F_p)$ 为对角线元素全为 $1$、对角线下方元素全为 $0$ 的上三角矩阵组成的群。对角线上方共有 $n(n-1)/2$ 个位置，每个位置有 $p$ 种选择，故 $$|U_n(\mathbb F_p)|=p^{n(n-1)/2}.$$

另一方面，逐列选择线性无关的列向量，得到 $$|\mathrm{GL}_n(\mathbb F_p)|=\prod_{i=0}^{n-1}(p^n-p^i)=p^{n(n-1)/2}\prod_{j=1}^{n}(p^j-1).$$ 后面的乘积不被 $p$ 整除，所以 $U_n(\mathbb F_p)$ 是一个 Sylow $p$-子群。

### 4.3 $\mathrm{GL}_n(\mathbb Z/p^r\mathbb Z)$

考虑将矩阵元素模 $p$ 化的群同态 $$\rho:\mathrm{GL}_n(\mathbb Z/p^r\mathbb Z)\longrightarrow\mathrm{GL}_n(\mathbb F_p).$$ 它是满射：$\mathbb F_p$ 上的可逆矩阵任取一个模 $p^r$ 的提升，其行列式仍不被 $p$ 整除，因而模 $p^r$ 可逆。

核由模 $p$ 后成为单位矩阵的矩阵组成，即 $$\ker\rho=\{I_n+pB:B\in M_n(\mathbb Z/p^{r-1}\mathbb Z)\}.$$ 每个矩阵位置中的 $pB$ 有 $p^{r-1}$ 种取值，因此 $$|\ker\rho|=p^{n^2(r-1)}.$$

由此得到 $$|\mathrm{GL}_n(\mathbb Z/p^r\mathbb Z)|=p^{n^2(r-1)}|\mathrm{GL}_n(\mathbb F_p)|.$$ 特别地，$\rho^{-1}\bigl(U_n(\mathbb F_p)\bigr)$ 的阶为 $$p^{n^2(r-1)+n(n-1)/2},$$ 正好是群阶中最大的 $p$ 的幂，因此它是 $\mathrm{GL}_n(\mathbb Z/p^r\mathbb Z)$ 的一个 Sylow $p$-子群。

**注** 这里的核是一个 $p$-群，但当 $r>2$ 时，一般不能把它的乘法直接写成矩阵加法：乘积 $(I_n+pB)(I_n+pC)$ 中还会出现 $p^2BC$ 项。

## 5. 满同态下子群的原像

**引理** 设 $\varphi:G\to H$ 为满群同态，$H_1\le H$，令 $G_1=\varphi^{-1}(H_1)$。则：

1. $\ker\varphi\le G_1$，且限制映射 $\varphi|_{G_1}:G_1\to H_1$ 为满同态，其核仍是 $\ker\varphi$；
2. 左陪集之间有双射 $$G/G_1\longrightarrow H/H_1,\qquad gG_1\longmapsto\varphi(g)H_1,$$ 因而 $[G:G_1]=[H:H_1]$；
3. 若 $H_1\trianglelefteq H$，则 $G_1\trianglelefteq G$，并有群同构 $$G/G_1\cong H/H_1.$$

**证明** 因 $e_H\in H_1$，有 $\ker\varphi\subseteq G_1$。满射性保证 $H_1$ 中每个元素在 $G_1$ 中都有原像，从而得到第 1 项。第 2 项的映射良定义且为双射：$$\varphi(g_1)H_1=\varphi(g_2)H_1\iff\varphi(g_2^{-1}g_1)\in H_1\iff g_2^{-1}g_1\in G_1\iff g_1G_1=g_2G_1.$$ 当 $H_1$ 正规时，两个商集都有群结构，上述双射还保持群运算，故得到第 3 项。证毕。

**注** 若 $H_1$ 不正规，$G/G_1$ 与 $H/H_1$ 在这里仅指左陪集组成的集合；此时仍有陪集双射，但不能直接称其为“商群同构”。

