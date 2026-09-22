
# Set (集合)

> [!note] 定义
> - Any collection of objects that you can describe it（before Russell(罗素))
> - ZFC set theory

### 范畴 (Category) 的基本概念

> [!note] 范畴的定义
> 一个**范畴** $\mathcal{C}$ 由以下数据构成：
> - **对象** (objects)：记作 $\operatorname{Ob}(\mathcal{C})$
> - **态射** (morphisms/arrows)：对任意对象 $A, B$，有一族态射 $\operatorname{Hom}_{\mathcal{C}}(A, B)$
> - **复合** (composition)：$\circ: \operatorname{Hom}(B, C) \times \operatorname{Hom}(A, B) \to \operatorname{Hom}(A, C)$
> - **恒等态射** (identity)：每个对象 $A$ 有 $\operatorname{id}_A \in \operatorname{Hom}(A, A)$
>
> 满足：
> 1. **结合律**：$(h \circ g) \circ f = h \circ (g \circ f)$
> 2. **单位律**：$f \circ \operatorname{id}_A = f = \operatorname{id}_B \circ f$

> [!example] 常见范畴
> | 范畴 | 对象 | 态射 |
> |:---:|:----:|:----:|
> | **Set** | 集合 | 函数 |
> | **Grp** | 群 | 群同态 |
> | **Ab** | 阿贝尔群 | 阿贝尔群同态 |
> | **Ring** | 环 | 环同态 |
> | **Vect**$_F$ | $F$-向量空间 | 线性映射 |
> | **Top** | 拓扑空间 | 连续映射 |

### 集合范畴 **Set**

> [!note] 定义
> **Set** 是**以全体集合为对象、以集合间的函数为态射**的范畴。
>
> - 对象：$X, Y, Z, \dots$（集合）
> - 态射：$\operatorname{Hom}_{\textbf{Set}}(X, Y) = \{ f: X \to Y \mid f \text{ 是函数} \}$
> - 复合：函数的通常复合 $(g \circ f)(x) = g(f(x))$
> - 恒等态射：$\operatorname{id}_X(x) = x$

> [!success] **Set** 的特殊性质
>
> **1. 始对象 (initial object)**
> - $\varnothing$（空集）是 **Set** 的始对象：对任意集合 $Y$，存在唯一的函数 $\varnothing \to Y$（空函数）
>
> **2. 终对象 (terminal object)**
> - $\{*\}$（单点集）是 **Set** 的终对象：对任意集合 $X$，存在唯一的函数 $X \to \{*\}$（常值函数）
>
> **3. 积 (product)**
> - $X \times Y$（笛卡尔积）配上投影映射 $\pi_X, \pi_Y$ 是范畴论中的积
>
> **4. 余积 (coproduct)**
> - $X \sqcup Y$（无交并）配上包含映射 $i_X, i_Y$ 是范畴论中的余积
>
> **5. 笛卡尔闭性**
> - **Set** 是笛卡尔闭范畴：存在双射 $\operatorname{Hom}(X \times Y, Z) \cong \operatorname{Hom}(X, Z^Y)$，其中 $Z^Y$ 是从 $Y$ 到 $Z$ 的函数集

> [!tip] 泛性质 (Universal Property) 视角
> 范畴论的核心思想是用**态射**而非元素来刻画对象。例如：
>
> **笛卡尔积的泛性质**：
> 对任意集合 $A$ 及映射 $f: A \to X$、$g: A \to Y$，存在**唯一的**映射 $\langle f, g \rangle: A \to X \times Y$ 使得下图交换：
> $$
> \begin{CD}
> A @. \\
> @V{f}VV @VV{g}V \\
> X @<<{\pi_X}< X \times Y @>>{\pi_Y}> Y
> \end{CD}
> $$
> 这种描述完全不依赖集合元素的细节，只依赖态射关系——这就是**范畴论**的精髓。

> [!note] 为什么要关注 **Set**？
> **Set** 在范畴论中扮演基础性角色：
> 1. **可表函子**：很多范畴可以通过 Hom 函子 $\operatorname{Hom}(X, -)$ 嵌入 **Set**
> 2. **遗忘函子** (forgetful functor)：如 $U: \textbf{Grp} \to \textbf{Set}$ 把群"遗忘"其结构，只保留底层集合
> 3. **自由-遗忘伴随**：自由群构造 $\dashv$ 遗忘函子构成一对伴随函子——这是范畴论中最重要的模式之一



# Group
## 定义

> [!note] 群的定义
> 一个满足下列条件的非空集合被称为**群(Group)**
> 可以定义一个运算 \*满足
> (1). 封闭性
> (2). 结合律(associatitivity)
> (3). 存在单位元
> (4). 存在逆元
> 
> 如果这个运算还满足交换律(commutativity)，则称这个群为**Able群**或**交换群**
> 如果一个集合和运算 \* 只满足(1),(2)，则称这个集合为**半群**
> 如果一个集合和运算 \* 只满足(1),(2),(3)，则称这个集合为**幺半群**

> [!example] 
> $(\mathbb{Z},+),(\mathbb{Q},+),(\mathbb{R},+),(\mathbb{C},+)$都是群，且是Able群
> ({0}，+）是群
> ({1，-1}，$\times$）是 Able 群
> ({1，-1，0}，$\times$）是幺半群
> $\mathbb{R}$ 上的 n 阶可逆方阵与矩阵乘法构成群
> $A \in \{M_{n\times n}(\mathbb{C})\big| |A| \not = 0\}$ 称为一般线性群，记作 $GL_n$
> 一般线性群还有另外一个定义：
> $GL(V)=\{\phi: \phi \in \mathcal{L}(V),\phi 是线性同构 (isomorphism)\}$
> 

> [!note] the order of the group
> 群$(G,+)$的 (order) 就是集合 G 的元素个数(有限)或者势(无限)

### 重要的群
> [!example] 对称群 $S_n$
> 所有的 n 阶置换映射 $\sigma(k_1,k_2,\cdots,k_n)$ 于映射的复合构成的群

> [!example] 二面体群（Dihedral Group) $D_n$
>  一个 n 阶正多边形执行以下操作得到的群
>  - 绕中心旋转
>  - 沿某条对称轴翻转

### 群的基本性质

1. 群只有一个单位元
2. a,b,c 是群 G 的元素，那么 $ab=ac\Rightarrow b=c$
3. 群中某个元素的逆元是唯一的
4. $(ab)^{-1}=b^{-1}a^{-1}$
5. $(a^{-1})^{-1}$
6. 记 $(a^{-n})=(a^{-1})^n$

### 群的元素的阶

> [!note] 群的元素的阶
> 设 a 是群 G 的一个元素，并且有 $a^k=e(单位元)$，那么称最小的 k 是元素 a 的阶，记为 |a|
> EX：
> 对群 $(\mathbb{Z}/4\mathbb{Z},\times)$，元素 $\overline{2}$ 的阶为 2，因为 $\overline{2}^2 =\overline{4}=0$

**性质**：
> [!tip] 
> - 如果群Ｇ中的元素ａ满足 $a^i = a^j，i\not = j$，那么 a 有有限的阶，$|a| = |i-j|$
> - 记 |a|=n，那么 $a^k =e \iff n|k$
> - $a^i=a^j \iff i \equiv j(mod\,n)$

> [!success] 
> 如果一个阿贝尔群的元素有着有限的最大的阶 c，那么 c 是该群中所有元素的阶的公倍数

**证明**：设 $a\in G$ 使得 $|a| = c$（$c$ 为最大阶）。任取 $b \in G$，记 $|b| = d$。下证 $d \mid c$。

反证法：假设 $d \nmid c$。，由算数基本定理知，则存在素数 $p$，使得 $d$ 中 $p$ 的幂次高于 $c$ 中 $p$ 的幂次，即
$$
c = p^{\alpha} \cdot c_1,\quad d = p^{\beta} \cdot d_1
$$
其中 $p \nmid c_1$，$p \nmid d_1$，且 $\beta > \alpha \ge 0$。(即对两者进行公共质因数分解)

考虑如下两个元素：
- $x = a^{p^{\alpha}}$，有 $|x| = |a^{p^{\alpha}}| = c_1$
- $y = b^{d_1}$，有 $|y| = |b^{d_1}| = p^{\beta}$

因为 $G$ 是**阿贝尔群**，$x$ 与 $y$ 可交换。又 $\gcd(c_1, p^{\beta}) = 1$，故
$$
|x y| = |x| \cdot |y| = c_1 \cdot p^{\beta}
$$
（交换群中，阶互素的两元素之积的阶等于它们阶的乘积。）

于是
$$
|x y| = c_1 \cdot p^{\beta} \ge c_1 \cdot p^{\alpha+1} > c_1 \cdot p^{\alpha} = c
$$
这与 **$c$ 是群中元素的最大阶**矛盾。因此假设不成立，必有 $d \mid c$。$\square$

### 群的乘法

> [!note] 定义
> 设 $(G,+),(H,\times)$ 是两个群那么 $G\times H$ 与运算 $*$ 是一个群，其中 $*$ 的定义为：
> $(g,h)*(g',h')=(g+g',h\times h')$

### 子群

> [!note] 定义
> 设 $(G,+)$ 是一个群，$H\subset G$，$(H,+)$ 也是一个群，那么称 H 是 G 的子群

> [!success] 
> 对于群 $(G,+)$ 非空子集 H，需检验以下两者就可以保证它是子群
> - 封闭性
> - 逆存在
> 
> 而对于有限的群 G，则只需要检验封闭性

### 群的中心

> [!note] 定义
> 群 $G$ 中与所有元素可交换的元素构成的集合称为群 $G$ 的**中心**，记为 $C(G)$
> $$
> C(G) = \{ g \in G \mid gh = hg,\ \forall h \in G \}
> $$

> [!tip] 性质
> 群的中心是 $G$ 的一个**交换子群**（实际上也是 $G$ 的正规子群）。

> [!example]
> - $C(S_3) = \{ e \}$（$S_3$ 的中心平凡，只有单位元）
> - $C(\mathbb{Z}_n) = \mathbb{Z}_n$（交换群的中心是其自身）
> - $C(D_n) = \{ e \}$（$n>2$ 时二面体群中心平凡；$n=2$ 时 $D_2 \cong \mathbb{Z}_2 \times \mathbb{Z}_2$，中心为其自身）
> - $C(GL_n(\mathbb{R})) = \{ a I_n \mid a \in \mathbb{R}^\times \}$（纯量矩阵）
> - $C(\mathbb{Z}) = \mathbb{Z}$

**证明中心是子群**：
1. 单位元 $e$ 与所有元素可交换，故 $e \in C(G)$
2. 若 $g_1, g_2 \in C(G)$，则对任意 $h \in G$，有 $(g_1g_2)h = g_1(g_2h) = g_1(hg_2) = (g_1h)g_2 = h(g_1g_2)$，故 $g_1g_2 \in C(G)$（封闭性）
3. 若 $g \in C(G)$，由 $gh = hg$ 两边同乘 $g^{-1}$ 得 $hg^{-1} = g^{-1}h$，故 $g^{-1} \in C(G)$（逆封闭）


### 循环群

> [!note] 定义
> 如果群 $G$ 中存在一个元素 $g$，使得 $G$ 中每个元素都是 $g$ 的幂（即 $G = \{g^k \mid k \in \mathbb{Z}\}$），则称 $G$ 为**循环群**，记为 $G = \langle g \rangle$，称 $g$ 为 $G$ 的一个**生成元**。

> [!example]
> - $(\mathbb{Z}, +)$ 是无限循环群，生成元为 $1$（或 $-1$）
> - $(\mathbb{Z}/n\mathbb{Z}, +)$ 是 $n$ 阶有限循环群，生成元为 $\overline{1}$
> - 单位根群 $\{e^{2\pi i k/n} \mid k = 0,1,\dots,n-1\}$ 在乘法下构成 $n$ 阶循环群

> [!tip] 基本性质
> 1. **同构分类**：任一无限循环群同构于 $\mathbb{Z}$；任一 $n$ 阶有限循环群同构于 $\mathbb{Z}/n\mathbb{Z}$
> 2. **子群**：循环群的子群仍是循环群
> 3. **有限循环群的子群**：$n$ 阶循环群 $\langle g \rangle$ 对每个 $d \mid n$ 有**唯一**一个 $d$ 阶子群 $\langle g^{n/d} \rangle$
> 4. **生成元的个数**：
>    - 无限循环群 $\mathbb{Z}$ 有且仅有 $2$ 个生成元：$1$ 和 $-1$
>    - $n$ 阶有限循环群 $\mathbb{Z}/n\mathbb{Z}$ 恰有 $\varphi(n)$ 个生成元（$\varphi$ 为 Euler 函数），即与 $n$ 互素的剩余类
> 5. **有限生成阿贝尔群基本定理**：每个有限生成阿贝尔群可分解为循环群的直积/直和

### 由子集生成的子群
> [!note] 定义
> 设 S 是 群 G 的一个子集，记 $\langle S \rangle$ 为包含子集 S 的最小的子群

### 群的同构

> [!note] 定义
> 设 $(G, \cdot)$ 和 $(H, \ast)$ 是两个群。若存在双射 $\varphi: G \to H$ 使得对任意 $a, b \in G$ 有
> $$
> \varphi(a \cdot b) = \varphi(a) \ast \varphi(b)
> $$
> 则称 $\varphi$ 是 $G$ 到 $H$ 的一个**群同构**，记作 $G \cong H$，称 $G$ 与 $H$ **同构**。

> [!tip] 直观理解
> 同构的两个群在**代数结构**上完全一样，只是元素的"名字"不同。同构的群有完全相同的群论性质（阶、交换性、子群结构等）。

> [!example] 例子
> - $(\mathbb{Z}, +) \cong (2\mathbb{Z}, +)$，同构映射为 $\varphi(n) = 2n$
> - $(\mathbb{R}^+, \times) \cong (\mathbb{R}, +)$，同构映射为 $\varphi(x) = \ln x$（正实数乘法群同构于实数加法群）
> - 任一 $n$ 阶有限循环群同构于 $\mathbb{Z}/n\mathbb{Z}$
> - 任一无限循环群同构于 $\mathbb{Z}$
> - $S_3 \not\cong \mathbb{Z}/6\mathbb{Z}$（因为前者非交换，后者交换）

> [!tip] 同构基本定理
> 1. **第一同构定理**：若 $\varphi: G \to H$ 是群同态，则 $G/\ker\varphi \cong \operatorname{im}\varphi$
> 2. **第二同构定理**：若 $H \le G$，$N \trianglelefteq G$，则 $H/(H \cap N) \cong HN/N$
> 3. **第三同构定理**：若 $N \trianglelefteq G$，$N \le H \trianglelefteq G$，则 $(G/N)/(H/N) \cong G/H$

### p-群 (p-group)

> [!note] 定义
> 设 $p$ 为素数。群 $G$ 称为 **p-群**，若 $G$ 中每个元素的阶都是 $p$ 的幂次。
>
> 对于**有限群**，由 Lagrange 定理可知 $G$ 是 p-群 $\iff$ $|G| = p^n$（$n \ge 0$）。

> [!example] 例子
> | 群 | 是否 p-群 | 说明 |
> |:---:|:--------:|:----|
> | $\mathbb{Z}/p\mathbb{Z}$ | ✅ | 阶为 $p$ |
> | $\mathbb{Z}/p^n\mathbb{Z}$ | ✅ | 阶为 $p^n$ |
> | $(\mathbb{Z}/2\mathbb{Z})^n$ | ✅ | 2-群，阶为 $2^n$ |
> | $D_4$（正方形对称群） | ✅ | 阶为 $8 = 2^3$ |
> | $Q_8$（四元数群） | ✅ | 阶为 $8 = 2^3$ |
> | $S_3$ | ❌ | 阶为 $6$，不是单一素数的幂 |
> | $\mathbb{Z}/6\mathbb{Z}$ | ❌ | 阶为 $6$ |

> [!success] 性质 1：有限 p-群的中心非平凡
> 设 $G$ 是有限 p-群且 $|G| > 1$，则中心 $C(G) \neq \{e\}$，且 $|C(G)| \ge p$。
>
> **证明**：考虑类方程（class equation）：
> $$
> |G| = |C(G)| + \sum_{i=1}^{k} [G : C_G(g_i)]
> $$
> 其中 $g_i$ 取遍各非中心共轭类的代表元。对每个 $i$，$[G : C_G(g_i)] > 1$ 且是 $|G| = p^n$ 的因子，故 $p \mid [G : C_G(g_i)]$。于是等式右边除 $|C(G)|$ 外的各项都被 $p$ 整除，又 $|G|$ 被 $p$ 整除，因此 $p \mid |C(G)|$。特别地 $|C(G)| \ge p$。$\square$

> [!success] 性质 2：幂零性
> 所有有限 p-群都是**幂零群** (nilpotent group)。

> [!success] 性质 3：Sylow 定理的关联
> 对任意有限群 $G$，若 $|G| = p^n \cdot m$ 且 $p \nmid m$，则 $G$ 的 Sylow $p$-子群就是 $G$ 中阶最大的 p-子群（阶为 $p^n$）。

> [!success] 性质 4：Frattini 商群
> 设 $G$ 是有限 p-群，$\Phi(G)$ 为 Frattini 子群（所有极大子群的交），则 $G/\Phi(G)$ 是**初等阿贝尔 p-群**，即若干 $\mathbb{Z}/p\mathbb{Z}$ 的直积。

> [!note] 有限 p-群的分类
> - **阶 $p$**：唯一，$\mathbb{Z}/p\mathbb{Z}$（循环群）
> - **阶 $p^2$**：两类
>   - $\mathbb{Z}/p^2\mathbb{Z}$（循环群）
>   - $\mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$（初等阿贝尔群）
> - **阶 $p^3$**：对奇素数 $p$ 共 5 种；$p=2$ 也是 5 种（$D_4$、$Q_8$、$\mathbb{Z}/8\mathbb{Z}$、$\mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$、$\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$）

### 幂零群 (Nilpotent Group)

幂零群是比阿贝尔群更广、比可解群更窄的一类群，可以视为"逐步可交换"的群。

> [!note] 定义（下中心系列）
> 设 $G$ 是群，定义**下中心系列** (lower central series)：
> $$
> \gamma_1(G) = G,\quad \gamma_{k+1}(G) = [\gamma_k(G), G]
> $$
> 其中 $[H, K] = \langle h^{-1}k^{-1}hk \mid h \in H, k \in K \rangle$ 为**换位子群**。
>
> 若存在 $c$ 使得 $\gamma_{c+1}(G) = \{e\}$，则称 $G$ 为**幂零群**，最小的这样的 $c$ 称为**幂零类** (nilpotency class)。

> [!note] 等价定义（上中心系列）
> 定义**上中心系列** (upper central series)：
> $$
> Z_0(G) = \{e\},\quad Z_{k+1}(G) = \pi^{-1}(C(G/Z_k(G)))
> $$
> 即 $Z_{k+1}(G)/Z_k(G) = C(G/Z_k(G))$（中心提升）。
>
> $G$ 是幂零群 $\iff$ 存在 $c$ 使得 $Z_c(G) = G$，此时幂零类为最小的这样的 $c$。

> [!example] 幂零类的例子
> | 群 | 幂零类 | 说明 |
> |:---:|:-----:|:----|
> | 阿贝尔群（非平凡） | $1$ | $Z_1(G) = G$，即 $\gamma_2(G) = \{e\}$ |
> |  Heisenberg 群（$3\times 3$ 上三角幺模阵） | $2$ | 典型"最简非交换幂零群" |
> | 四元数群 $Q_8$ | $2$ |  |
> | 二面体群 $D_4$ | $2$ | $D_4$ 是 2-群，幂零类 2 |
> | 二面体群 $D_n$（$n\ge 3$ 奇数） | ❌ 非幂零 | $D_3 \cong S_3$ 可解但非幂零 |
> | $S_3$ | ❌ 非幂零 | $\gamma_2(S_3) = A_3$，$\gamma_3(S_3) = A_3$ 停滞 |

> [!success] 基本性质
> 1. **阿贝尔群 $\subset$ 幂零群 $\subset$ 可解群**（真包含关系）
> 2. **有限 p-群都是幂零群**（这是 p-群最重要的性质之一）
> 3. **有限群是幂零群 $\iff$ 它是其所有 Sylow 子群的直积**：
>    $$
>    G \cong P_{p_1} \times P_{p_2} \times \cdots \times P_{p_k}
>    $$
>    其中 $P_{p_i}$ 是 $G$ 的 Sylow $p_i$-子群。
> 4. 幂零群的子群和商群仍是幂零群
> 5. 幂零群中，正规化子条件成立：若 $H < G$ 是子群，则 $H \subsetneq N_G(H)$（真包含于其正规化子中）

> [!tip] Heisenberg 群（幂零类 2 的典型例子）
> $$
> H(\mathbb{R}) = \left\{
> \begin{pmatrix}
> 1 & a & c \\
> 0 & 1 & b \\
> 0 & 0 & 1
> \end{pmatrix}
> \;\middle|\; a,b,c \in \mathbb{R}
> \right\}
> $$
> 其换位子 $[x,y]$ 落在中心 $\left\{\begin{pmatrix}1&0&*\\0&1&0\\0&0&1\end{pmatrix}\right\}$ 中，故 $\gamma_3 = \{e\}$，幂零类为 2。

> [!success] 与可解群的对比
> | 性质 | 幂零群 | 可解群 |
> |:---:|:------:|:------:|
> | 导群列终止 | 不一定 | ✅ 终止于 $\{e\}$ |
> | 下中心系列终止 | ✅ 终止于 $\{e\}$ | 不一定 |
> | 有限 p-群 | ✅ 总是 | ✅ 总是 |
> | Sylow 子群是否正规 | ✅ 都是 | ❌ 不一定 |
> | $S_3$ | ❌ 非幂零 | ✅ 可解 |
> | 直积分解 | 分解为 Sylow 直积 | 不一定能分解 |

### 可解群 (Solvable Group)

可解群起源于 Galois 理论研究多项式根式可解性的核心概念——**多项式可用根式求解当且仅当其 Galois 群是可解群**。

> [!note] 定义（导群列）
> 设 $G$ 是群。定义**导群** (derived subgroup / commutator subgroup) $G' = [G, G]$ 为所有换位子生成的子群：
> $$
> G' = \langle x^{-1}y^{-1}xy \mid x,y \in G \rangle
> $$
>
> 由此定义**导群列** (derived series)：
> $$
> G^{(0)} = G,\quad G^{(1)} = G',\quad G^{(k+1)} = [G^{(k)}, G^{(k)}]
> $$
>
> 若存在 $n$ 使得 $G^{(n)} = \{e\}$，则称 $G$ 为**可解群**。最小的这样的 $n$ 称为**导长度** (derived length)。

> [!example] 例子
> | 群 | 导长度 | 说明 |
> |:---:|:-----:|:----|
> | 阿贝尔群 | $1$ | $G' = \{e\}$ |
> | $S_3$ | $2$ | $S_3' = A_3 \cong \mathbb{Z}_3$，$S_3'' = \{e\}$ |
> | $S_4$ | $3$ | $S_4' = A_4$，$S_4'' = V_4$（Klein 四元群），$S_4''' = \{e\}$ |
> | $S_n\ (n \ge 5)$ | ❌ 不可解 | $A_n$ 是非交换单群，导群列停滞 |
> | 幂零群 | 有限 | 幂零 $\Rightarrow$ 可解 |
> | $A_5$ | ❌ 不可解 | 非交换单群，$A_5' = A_5$ |

> [!success] 基本性质
> 1. **阿贝尔群 $\subset$ 幂零群 $\subset$ 可解群**
> 2. 可解群的子群和商群仍是可解群
> 3. 若 $N \trianglelefteq G$ 且 $N$ 和 $G/N$ 都可解，则 $G$ 可解
> 4. **$S_n$ 可解 $\iff$ $n \le 4$**（$n\ge 5$ 时 $A_n$ 是非交换单群）
> 5. **Feit–Thompson 定理（奇阶定理）**：所有奇数阶有限群都是可解群（深刻结果，论文长达 255 页）

> [!tip] 与 Galois 理论的联系
> 设 $f(x) \in \mathbb{Q}[x]$ 是一个多项式，$E$ 是 $f$ 在 $\mathbb{C}$ 上的分裂域，则
> $$
> f(x)\text{ 可用根式求解} \iff \operatorname{Gal}(E/\mathbb{Q})\text{ 是可解群}
> $$
>
> 例如：
> - 二次、三次、四次多项式**总是**可用根式求解（$S_2, S_3, S_4$ 均可解）
> - 一般的五次及以上多项式**不可**根式求解（$S_n\ (n\ge5)$ 不可解）
> - 具体反例：$x^5 - x + 1$ 的 Galois 群是 $S_5$，不可解，故不能用根式求解

> [!note] 三类群的关系总结
> $$
> \text{阿贝尔群} \;\subsetneq\; \text{幂零群} \;\subsetneq\; \text{可解群}
> $$
> - 阿贝尔群：$G' = \{e\}$，一次交换
> - 幂零群：通过取与 $G$ 的换位子逐步消灭非交换性（下中心系列），比可解强
> - 可解群：通过反复取导群逐步消灭非交换性，条件更弱
>
> 反例链：
> - $S_3$：可解 $\wedge$ 非幂零
> - $A_5$（或 $S_5$）：不可解

### 单群 (Simple Group)

单群是有限群论的"原子"——所有有限群都可以分解为单群的"乘积"（合成因子）。

> [!note] 定义
> 若群 $G$ 只有平凡正规子群 $\{e\}$ 和 $G$ 自身，则称 $G$ 为**单群**。
>
> 换言之：单群**不能**分解为更小的正规商群（没有非平凡的正规子群）。

> [!example] 例子
> | 群 | 是否单群 | 说明 |
> |:---:|:--------:|:----|
> | $\mathbb{Z}/p\mathbb{Z}$（$p$ 素数） | ✅ **单群** | 素数阶循环群都是单群 |
> | $\mathbb{Z}/n\mathbb{Z}$（$n$ 合数） | ❌ | 有非平凡子群（正规子群） |
> | $A_n\ (n \ge 5)$ | ✅ **单群** | 交错群的核心结论 |
> | $A_3 \cong \mathbb{Z}_3$ | ✅ | 素数阶，也是交错群单性的特例 |
> | $A_4$ | ❌ | $V_4 \trianglelefteq A_4$ |
> | $S_n\ (n\ge 2)$ | ❌ | $A_n \trianglelefteq S_n$ |
> | $PSL_n(\mathbb{F}_q)$（$n\ge 2$ 且排除小例外） | ✅ | 典型 Lie 型单群 |

> [!success] 两条关键性质
>
> **1. 可解单群只有素数阶循环群**
> $$
> G \text{ 可解且单} \iff G \cong \mathbb{Z}/p\mathbb{Z}
> $$
> 这就是为什么可解群的合成因子全是素数阶循环群，从而与 Galois 理论完美衔接。
>
> **2. Jordan–Hölder 定理**
> 每个有限群 $G$ 都有**合成列** (composition series)：
> $$
> G = N_0 \triangleright N_1 \triangleright \cdots \triangleright N_r = \{e\}
> $$
> 其中每个 $N_i/N_{i+1}$ 是单群，称为**合成因子**。这些合成因子（不计顺序）是唯一确定的。
>
> 因此，**单群是所有有限群的"基本粒子"**。

> [!note] 有限单群分类定理 (CFSG)
> 这是 20 世纪数学最宏大的成果之一（约 10,000 页，100 多位数学家参与）。所有有限单群分为以下 4 类：
>
> | 类别 | 描述 | 例子 |
> |:---:|:----|:----|
> | **素数阶循环群** | $\mathbb{Z}/p\mathbb{Z}$ | $\mathbb{Z}_2, \mathbb{Z}_3, \mathbb{Z}_5, \dots$ |
> | **交错群** | $A_n\ (n\ge 5)$ | $A_5, A_6, A_7, \dots$ |
> | **Lie 型单群** | 典型群、例外群（Chevalley 群） | $PSL_n(\mathbb{F}_q)$，$E_8(q)$ 等 |
> | **散在单群** (Sporadic) | 26 个不属以上三类的特例 | **魔群** (Monster, $|M| \approx 8\times 10^{53}$) |

> [!tip] 关于 $A_n$ 的单性证明思路
> 证明 $A_n\ (n\ge 5)$ 是单群的关键引理：
> 1. $A_n$ 由 3-轮换生成
> 2. $A_n$ 中所有 3-轮换互相共轭
> 3. 若 $N \trianglelefteq A_n$ 非平凡，则 $N$ 包含某个 3-轮换
> 4. 从而 $N$ 包含所有 3-轮换，故 $N = A_n$
>
> $A_5$ 是散在单群中一些群的"祖先"——例如魔群有 $A_5$ 作为其子商群。

> [!success] 回顾三类群的关系
> 用单群的语言重新总结整个群论脉络：
>
> | 群类 | 合成因子 | 判定 |
> |:----:|:--------:|:----|
> | 阿贝尔群 | 素数阶循环群 | $G' = \{e\}$ |
> | 幂零群 | 素数阶循环群（且在特定顺序下正规） | 上/下中心系列终止 |
> | 可解群 | 素数阶循环群 | 导群列终止 |
> | 一般有限群 | 任意单群 | — |
>
> 所以 Galois 理论中"多项式根式可解"对应"Galois 群的合成因子全是素数阶循环群"，这正是可解群的定义特征。

# Ring

## 定义
> [!note] 环的定义
> 一个集合R如果满足一下条件则称之为 **环(ring)**
> (1). 可以定义运算 + ，满足(R, +)为Albian群
> (2). 可以定义运算 \*， 满足(R, \*)为半群
> (3). + ,\* 满足结合律
> 
> 如果(R, \*)是Albe群，则称之为 **交换环**
> 如果一个交换环无零因子，即$ab=0 \Rightarrow a=0 \lor b=0$，则称之为 **整环**
> 如果(R, \*)是Able群，则称R是一个 **域(field)**

> [!example] 环的几个例子：
> - 数域$\mathbb{F}$上的全体 n 阶方阵构成一个环，成为 **n阶全方阵环**
> - 整数，多项式是整环
## 理想
> [!note] 环的理想
> 满足以下条件的集合 $I$ 成为环 $R$ 的 **理想**：
> - $I$ 是 $R$ 的加法子群
> - $I$ 满足吸收性，即$\forall a \in I, x\in R : ax \in I$

# Field

## 定义 

> [!note] 域的定义
> 满足以下条件的集合 $F$ 并配合两个运算（**记为** 加法 “+” 和乘法 “\*” ）为域
> 1.  (F, +) 为交换环(将单位元记为 0)
> 2. (F\\{0},\*) 为交换环(将单位元记为 1)
> 3. 分配律成立

## 有限域乘法群是循环群

### 定理陈述
设 $\mathbb{F}_q$ 为 $q$ 元有限域（$q = p^n$，$p$ 为素数），则其乘法群 $\mathbb{F}_q^\times = \mathbb{F}_q \setminus \{0\}$ 是 $q-1$ 阶循环群。

下面先以 $\mathbb{F} = \mathbb{Z}_p$（$p$ 为素数）的情形给出详细证明。一般有限域的证明完全类似，只需将 $p-1$ 替换为 $q-1$。

### 引理
> [!tip] 引理 1（Lagrange 定理）
> 有限群中，每个元素的阶整除群的阶。$\\$
> 故 $\mathbb{Z}_p^\times$ 中每个元素的阶整除 $p-1$。

> [!tip] 引理 2（多项式根的个数）
> 域上 $d$ 次多项式至多有 $d$ 个根（计重数）。$\\$
> 故方程 $x^d = 1$ 在 $\mathbb{Z}_p$ 中至多有 $d$ 个解。

> [!tip] 引理 3（Euler 恒等式）
> $$
> \sum_{d \mid n} \varphi(d) = n
> $$
> 其中 $\varphi(d)$ 为 Euler 函数（不超过 $d$ 且与 $d$ 互素的正整数个数）。

### 证明

约定记号：$\psi(d) = \#\{x \in \mathbb{Z}_p^\times \mid |x| = d\}$，即群中阶**恰好**为 $d$ 的元素个数。

**Step 1：元素的阶只可能是 $p-1$ 的因子**

由 Lagrange 定理（引理 1），$\mathbb{Z}_p^\times$ 的阶为 $p-1$，故每个元素的阶整除 $p-1$。因此
$$
\psi(d) = 0 \quad(\text{若 } d \nmid (p-1))
$$
将所有可能阶的元素个数相加，得到群的总阶数：
$$
\sum_{d \mid (p-1)} \psi(d) = |\mathbb{Z}_p^\times| = p-1 \tag{1}
$$

**Step 2：$\psi(d)$ 的上界**

考虑多项式 $f(x) = x^d - 1 \in \mathbb{Z}_p[x]$，其中 $d \mid (p-1)$。

- 若 $\mathbb{Z}_p^\times$ 中**不存在** $d$ 阶元，则显然 $\psi(d) = 0$。
- 若存在某个 $a \in \mathbb{Z}_p^\times$ 使得 $|a| = d$，则 $\langle a \rangle = \{1, a, a^2, \dots, a^{d-1}\}$ 是 $d$ 阶循环子群。这 $d$ 个元素都满足 $x^d = 1$（因为 $(a^k)^d = (a^d)^k = 1$）。

  由引理 2，$d$ 次多项式 $f(x)$ 在域 $\mathbb{Z}_p$ 中至多有 $d$ 个根，因此 $x^d - 1$ 的**全部**根就是 $\langle a \rangle$ 中的 $d$ 个元素。

  于是 $\mathbb{Z}_p^\times$ 中满足 $|x| \mid d$ 的元素恰好就是 $\langle a \rangle$。而 $\langle a \rangle$（$d$ 阶循环群）中阶恰为 $d$ 的元素个数为 $\varphi(d)$（即其生成元的个数）。故
  $$
  \psi(d) = \varphi(d) \quad(\text{若存在 } d \text{ 阶元})
  $$

综上，对任意 $d \mid (p-1)$，有
$$
\psi(d) \le \varphi(d) \tag{2}
$$

**Step 3：夹逼得到等式**

由 Euler 恒等式（引理 3）：
$$
\sum_{d \mid (p-1)} \varphi(d) = p-1 \tag{3}
$$

结合 (1)、(2)、(3) 得：
$$
p-1 = \sum_{d \mid (p-1)} \psi(d) \le \sum_{d \mid (p-1)} \varphi(d) = p-1
$$

不等式两端相等，故中间的不等式必须处处取等号，即对每个 $d \mid (p-1)$，
$$
\psi(d) = \varphi(d) \tag{4}
$$

**Step 4：存在生成元**

特别地，取 $d = p-1$：
$$
\psi(p-1) = \varphi(p-1) \ge 1
$$

因为 $\varphi(n) \ge 1$ 对所有 $n \ge 1$ 成立（至少 $1$ 与 $n-1$ 都与 $n$ 互素）。故 $\mathbb{Z}_p^\times$ 中存在 $p-1$ 阶元，即 $\mathbb{Z}_p^\times$ 是 $p-1$ 阶循环群。$\square$

### 推论
> [!success]
> 1. $\mathbb{Z}_p^\times$ 恰有 $\varphi(p-1)$ 个生成元（本原元）。
> 2. 对每个 $d \mid (p-1)$，恰有 $\varphi(d)$ 个 $d$ 阶元。
> 3. 对每个 $d \mid (p-1)$，$\mathbb{Z}_p^\times$ 有唯一一个 $d$ 阶子群（即 $\langle a^{(p-1)/d} \rangle$，其中 $a$ 为任一生成元）。

### 例子：$\mathbb{Z}_7^\times$

$p=7$，$p-1=6$

| 元素 | 阶 |
|:---:|:--:|
| $\overline{1}$ | 1 |
| $\overline{2}$ | 3 |
| $\overline{3}$ | 6 ← **生成元** |
| $\overline{4}$ | 3 |
| $\overline{5}$ | 6 ← **生成元** |
| $\overline{6}$ | 2 |

验证推论：
- $\varphi(6) = \varphi(2)\varphi(3) = 1 \times 2 = 2$，恰有 2 个生成元：$\overline{3}, \overline{5}$ ✅
- $\varphi(1)=1$ 个 1 阶元：$\overline{1}$
- $\varphi(2)=1$ 个 2 阶元：$\overline{6}$
- $\varphi(3)=2$ 个 3 阶元：$\overline{2}, \overline{4}$
- 唯一 2 阶子群：$\{\overline{1}, \overline{6}\}$
- 唯一 3 阶子群：$\{\overline{1}, \overline{2}, \overline{4}\}$

### 推广到一般有限域

对任意有限域 $\mathbb{F}_q$（$q = p^n$），只需将上述证明中的 $p$ 换为 $q$：
- $\mathbb{F}_q^\times$ 的阶为 $q-1$
- $\mathbb{F}_q$ 仍是域，引理 2（多项式根数限制）仍然成立
- 其余推理完全一致

故 $\mathbb{F}_q^\times \cong \mathbb{Z}/(q-1)\mathbb{Z}$ 是循环群。


# module

> [!note] 模的定义
> 对于交换环 R，R-模为一个交换群(M, +)，给出一个映射：R $\times$ M $\rightarrow$ M，满足：
> 1. $(r_1+r_2)m = r_1m + r_2m$
> 2. $r(m_1+m_2) = rm_1 + rm_2$
> 3. $r_1r_2m=r_1(r_2m)$
> 4. $1_Rm=m$

### 群环与 G-模

> [!note] 群环 (Group Ring / Group Algebra)
> 设 $G$ 是群，$R$ 是交换环。**群环** $R[G]$ 是以 $G$ 为基的自由 $R$-模，乘法由 $G$ 的乘法线性扩张定义：
>
> $$
> R[G] = \left\{ \sum_{g \in G} r_g g \;\middle|\; r_g \in R,\ \text{仅有有限个非零} \right\}
> $$
>
> 乘法：$(r_g g)(r_h h) = (r_g r_h)(gh)$，并按分配律展开。

> [!note] G-模的定义
> 设 $G$ 是群。一个 **(左) G-模** 是满足以下条件之一的阿贝尔群 $M$：
>
> **等价定义 1（群作用）**：$M$ 是阿贝尔群，$G$ 作用在 $M$ 上，且每个 $g \in G$ 诱导 $M$ 的群自同构：
> $$
> g \cdot (m_1 + m_2) = g \cdot m_1 + g \cdot m_2
> $$
>
> **等价定义 2（群环）**：$M$ 是 $\mathbb{Z}[G]$-模（或更一般地，$k[G]$-模，$k$ 是域）。
>
> **等价定义 3（函子）**：将群 $G$ 视为只有一个对象 $*$ 的范畴，则 $G$-模等价于函子 $G \to \textbf{Ab}$（或 $G \to k\textbf{-Vect}$）。

### G-模范畴 $G\text{-}\textbf{Mod}$

> [!note] 定义
> **$G\text{-}\textbf{Mod}$** 是以全体 $G$-模为对象、$G$-模同态为态射的范畴。
>
> - 对象：$G$-模 $M, N, \dots$
> - 态射：$f: M \to N$ 满足 $f(g \cdot m) = g \cdot f(m)$（即与 $G$-作用交换的群同态）
> - 零对象：$\{0\}$（平凡 $G$-模）
> - 核与余核：由通常的群同态核与余核自然诱导

> [!success] 重要性质
>
> **1. $G\text{-}\textbf{Mod}$ 是阿贝尔范畴**
> - 有核、余核、直和、直积
> - 正合列概念完备（是群上同调的舞台）
>
> **2. 遗忘函子**
> $$
> U: G\text{-}\textbf{Mod} \to \textbf{Ab}
> $$
> 将 $G$-模 $M$ 映为底层阿贝尔群，"遗忘" $G$ 的作用。
>
> **3. 平凡模函子**
> $$
> \text{Triv}: \textbf{Ab} \to G\text{-}\textbf{Mod}
> $$
> 将阿贝尔群 $A$ 视为 $G$ 平凡作用的 $G$-模（$g \cdot a = a$）。
>
> **4. 不变子群函子 (Invariants)**
> $$
> (-)^G: G\text{-}\textbf{Mod} \to \textbf{Ab},\quad M^G = \{ m \in M \mid g \cdot m = m,\ \forall g \in G \}
> $$
> 这是群上同调 $H^0(G, M) = M^G$ 的来源。

> [!tip] 群上同调 (Group Cohomology)
> $G\text{-}\textbf{Mod}$ 是群上同调的自然设定。取 $M$ 的 **内射分解** 或使用 **标准余链复形**：
> $$
> H^n(G, M) = \operatorname{Ext}^n_{\mathbb{Z}[G]}(\mathbb{Z}, M)
> $$
> 其中 $\mathbb{Z}$ 视为平凡 $G$-模。
>
> 低阶解释：
> - $H^0(G, M) = M^G$（不变子群）
> - $H^1(G, M) = \operatorname{Der}(G, M)/\operatorname{PDer}(G, M)$（导子模内导子）
> - $H^2(G, M) = \{G \text{ 被 } M \text{ 的中心扩张}\}$（群扩张的分类）

> [!example] 例子
> | $G$-模 | 描述 |
> |:------:|:----|
> | $\mathbb{Z}$（平凡作用） | $g \cdot n = n$，用于定义群同调 $H_n(G, \mathbb{Z})$ |
> | $\mathbb{Z}[G]$（正则模） | $G$ 通过左乘作用在自身群环上 |
> | $\operatorname{Ind}_H^G(M)$ | 诱导模：$M$ 是 $H$-模，$\mathbb{Z}[G] \otimes_{\mathbb{Z}[H]} M$ |
> | Lie 代数 $(\mathfrak{g}, [\cdot,\cdot])$ 的对偶 | 在 Lie 群表示论中出现 |

### 群的特征标 (Character of a Group)

特征标是表示论的核心工具——用**迹**（trace）来刻画表示，将抽象的群元素映射为复数。

> 基础表示论参见：[[高等线性代数/群表示论/群表示论]]

> [!note] 定义
> 设 $\rho: G \to \operatorname{GL}(V)$ 是群 $G$ 在 $\mathbb{C}$ 上的有限维表示。其**特征标** (character) 为函数 $\chi_\rho: G \to \mathbb{C}$：
> $$
> \chi_\rho(g) = \operatorname{tr}(\rho(g)) \quad (\text{表示矩阵的迹})
> $$

> [!success] 基本性质
> 1. **类函数**：$\chi(hgh^{-1}) = \chi(g)$，在共轭类上取常值
> 2. $\chi_{\rho \oplus \psi} = \chi_\rho + \chi_\psi$，$\chi_{\rho \otimes \psi} = \chi_\rho \cdot \chi_\psi$
> 3. **表示由特征标唯一决定**：$\rho \cong \psi \iff \chi_\rho = \chi_\psi$
> 4. $\chi(e) = \dim V$（次数）

> [!example] 实例：$S_3$ 在 $\mathbb{C}^3$ 上的置换表示
>
> $S_3$ 自然地**置换坐标**：
> $$
> \sigma \cdot (x_1, x_2, x_3) = (x_{\sigma^{-1}(1)}, x_{\sigma^{-1}(2)}, x_{\sigma^{-1}(3)})
> $$
>
> **Step 1 —— 写出矩阵，计算迹**
>
> 对三种类型的群元，表示矩阵分别为：
> $$
> \rho(e) = \begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix},\qquad
> \rho(1\;2) = \begin{pmatrix}0&1&0\\1&0&0\\0&0&1\end{pmatrix},\qquad
> \rho(1\;2\;3) = \begin{pmatrix}0&0&1\\1&0&0\\0&1&0\end{pmatrix}
> $$
>
> 取迹得：
> $$
> \chi_\text{perm}(e)=3,\quad
> \chi_\text{perm}(1\;2)=1,\quad
> \chi_\text{perm}(1\;2\;3)=0
> $$
>
> 注意：$(1\;3)$ 和 $(2\;3)$ 也是迹 $1$，$(1\;3\;2)$ 也是迹 $0$。所以 $\chi_\text{perm}$ 在三个共轭类上的值为：
> $$
> \chi_\text{perm} = (3,\;1,\;0)
> $$
>
> **Step 2 —— 分解为不可约表示**
>
> 这个表示可以分解为两个 $G$-不变子空间的直和：
> $$
> \mathbb{C}^3 = W_1 \oplus W_2
> $$
> - $W_1 = \operatorname{span}\{(1,1,1)\}$ → **平凡表示** $\chi_\text{triv}$，所有群元映射为 $1$
> - $W_2 = \{(x_1,x_2,x_3) \mid x_1+x_2+x_3 = 0\}$ → **标准表示** $\chi_\text{std}$
>
> 由 $\chi_{\rho \oplus \psi} = \chi_\rho + \chi_\psi$ 得：
> $$
> \chi_\text{std} = \chi_\text{perm} - \chi_\text{triv}
> = (3-1,\; 1-1,\; 0-1) = (2,\;0,\;-1)
> $$
>
> 此外 $S_3$ 还有一个**符号表示** $\chi_\text{sign}$（对换 $\to -1$，轮换 $\to 1$）：
>
> **$S_3$ 的完整特征标表：**
>
> | $S_3$ | $e$ | $(1\;2)$ | $(1\;2\;3)$ |
> |:----:|:---:|:--------:|:----------:|
> | $\chi_\text{triv}$ | $1$ | $1$ | $1$ |
> | $\chi_\text{sign}$ | $1$ | $-1$ | $1$ |
> | $\chi_\text{std}$ | $2$ | $0$ | $-1$ |
>
> **Step 3 —— 验证正交性**
> $$
> \langle \chi_\text{std}, \chi_\text{std} \rangle
> = \frac{1}{6}\big(1\cdot 2^2 + 3\cdot 0^2 + 2\cdot (-1)^2\big)
> = \frac{4+0+2}{6} = 1
> $$
> 内积为 $1$ ⇒ $\chi_\text{std}$ 是**不可约**的。
>
> 同时可验证其他正交关系：
> $$
> \langle \chi_\text{triv}, \chi_\text{sign} \rangle = \frac{1}{6}(1\cdot1\cdot1 + 3\cdot1\cdot(-1) + 2\cdot1\cdot1) = \frac{1-3+2}{6} = 0
> $$
>
> **Step 4 —— 任意表示的分解公式**
>
> 给定任何 $S_3$ 的表示 $\rho$，只需计算内积即可读出分解：
> $$
> \rho \cong \chi_\text{triv}^{\oplus a} \oplus \chi_\text{sign}^{\oplus b} \oplus \chi_\text{std}^{\oplus c}
> $$
> 其中 $a = \langle \chi_\rho, \chi_\text{triv} \rangle$，$b = \langle \chi_\rho, \chi_\text{sign} \rangle$，$c = \langle \chi_\rho, \chi_\text{std} \rangle$。
>
> 例如对置换表示：$a = \langle (3,1,0), (1,1,1) \rangle = \frac{3+3+0}{6} = 1$，$c = \langle (3,1,0), (2,0,-1) \rangle = \frac{6+0+0}{6} = 1$，$b = 0$。所以 $\rho_\text{perm} \cong \chi_\text{triv} \oplus \chi_\text{std}$。✅





 
