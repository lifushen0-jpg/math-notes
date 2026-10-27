# 实线上的傅里叶变换与函数的下降性

## 1. 从傅里叶级数到傅里叶变换

对 $2\pi$ 周期函数，在适当条件下可以写出傅里叶级数
$$f(x)\sim\frac{a_0}{2}+\sum_{n=1}^{\infty}\bigl(a_n\cos nx+b_n\sin nx\bigr),$$
其中
$$a_n=\frac1\pi\int_{-\pi}^{\pi}f(x)\cos nx\,dx,\qquad b_n=\frac1\pi\int_{-\pi}^{\pi}f(x)\sin nx\,dx.$$
对于周期为 $L$ 的函数，频率相应变为 $2\pi n/L$。因此，周期函数的频率是离散的；研究 $\mathbb R$ 上的非周期函数时，则需要考虑连续的频率变量 $\xi\in\mathbb R$。这是引入傅里叶变换的动机，但不能仅凭“把求和换成积分”就得到严格的反演公式。

本文统一采用以下约定：若 $f\in L^1(\mathbb R)$，定义它的**傅里叶变换**为
$$\widehat f(\xi)=\int_{\mathbb R}f(x)e^{-2\pi i x\xi}\,dx.$$
若满足相应的反演条件，则
$$f(x)=\int_{\mathbb R}\widehat f(\xi)e^{2\pi i x\xi}\,d\xi.$$
例如，当 $f,\widehat f\in L^1(\mathbb R)$ 且 $f$ 在 $x$ 处连续时，上述反演公式在该点成立。反演公式中的积分变量是 $\xi$。

## 2. 可积函数的傅里叶变换

设 $f\in L^1(\mathbb R)$，即 $\int_{\mathbb R}|f(x)|\,dx<\infty$。

**有界性** 由三角不等式及 $|e^{-2\pi i x\xi}|=1$，可得
$$|\widehat f(\xi)|\le\int_{\mathbb R}|f(x)|\,dx=\|f\|_1.$$

**连续性** 对任意 $h\in\mathbb R$，
$$|\widehat f(\xi+h)-\widehat f(\xi)|\le\int_{\mathbb R}|f(x)|\,|e^{-2\pi i xh}-1|\,dx.$$
右端与 $\xi$ 无关，且当 $h\to0$ 时趋于 $0$（可先控制 $|x|$ 很大处的积分，再利用指数函数在有界区间上的一致连续性）。故 $\widehat f$ 在 $\mathbb R$ 上一致连续。

**Riemann–Lebesgue 引理** 若 $f\in L^1(\mathbb R)$，则
$$\widehat f(\xi)\longrightarrow0\qquad(|\xi|\to\infty).$$

**证明思路** 令 $h=1/(2|\xi|)$，其中 $\xi\ne0$，则 $e^{-2\pi i\xi h}=-1$。将积分中的 $f(x)$ 平移，可得
$$\widehat f(\xi)=\frac12\int_{\mathbb R}\bigl(f(x)-f(x-h)\bigr)e^{-2\pi i x\xi}\,dx,$$
从而
$$|\widehat f(\xi)|\le\frac12\|f-f(\,\cdot-h)\|_1.$$
利用 $L^1$ 函数的平移连续性，即 $\|f-f(\,\cdot-h)\|_1\to0$（$h\to0$），便得到结论。证毕。

综上，$$f\in L^1(\mathbb R)\quad\Longrightarrow\quad \widehat f\in C_0(\mathbb R),$$ 其中 $C_0(\mathbb R)$ 表示在无穷远处趋于 $0$ 的连续函数。

**注意** $\widehat f(\xi)\to0$ 不等于 $\widehat f\in L^1(\mathbb R)$。例如 $f=\mathbf1_{[-1,1]}$ 可积，但
$$\widehat f(\xi)=\frac{\sin(2\pi\xi)}{\pi\xi}\quad(\xi\ne0)$$
并不绝对可积。

## 3. 适度下降函数

“适度下降”在不同教材中的具体定义可能不同。这里采用一种足以保证可积的条件：若存在常数 $C>0,\varepsilon>0$，使得
$$|f(x)|\le\frac{C}{(1+|x|)^{1+\varepsilon}}\qquad(x\in\mathbb R),$$
就称 $f$ 满足此处的**适度下降条件**。由于右端在 $\mathbb R$ 上可积，这个条件保证 $f\in L^1(\mathbb R)$，因而 $\widehat f$ 有定义、连续且在无穷远处趋于 $0$。常见的更具体条件 $|f(x)|\le C/(1+x^2)$ 也有同样作用。

**注** 上述下降条件控制的是 $f$ 本身。若要对 $\widehat f$ 求导，还需要控制 $xf(x)$ 等乘积；若要证明 $\widehat f$ 下降得更快，则通常需要 $f$ 具有可积的导数。

## 4. 光滑性与下降速度的对应

下面的两个公式说明：**$x$ 方向的可导性控制频率方向的下降，$x$ 方向的下降控制频率方向的可导性。**

**导数与下降** 若 $f$ 及其导数满足足以进行分部积分的条件，例如 $f,f'\in L^1(\mathbb R)$ 且边界项消失，则
$$\widehat{f'}(\xi)=2\pi i\xi\,\widehat f(\xi).$$
进一步，若可重复分部积分 $k$ 次且 $f^{(k)}\in L^1(\mathbb R)$，则对 $\xi\ne0$ 有
$$|\widehat f(\xi)|\le\frac{\|f^{(k)}\|_1}{(2\pi|\xi|)^k}.$$
因此，可积的导数越多，傅里叶变换在无穷远处下降得越快。

**下降与导数** 若 $x^kf(x)\in L^1(\mathbb R)$，则可对积分号下求导 $k$ 次，得到
$$\widehat f^{(k)}(\xi)=\int_{\mathbb R}(-2\pi ix)^kf(x)e^{-2\pi ix\xi}\,dx.$$
因此，足够快的空间下降会使傅里叶变换具有更多连续导数。

## 5. 快速下降函数与 Schwartz 空间

**定义** 函数 $f\in C^\infty(\mathbb R)$ 若对任意非负整数 $k,\ell$ 都满足
$$\sup_{x\in\mathbb R}|x^k f^{(\ell)}(x)|<\infty,$$
则称 $f$ 为**快速下降函数**。所有这类函数组成的集合记为 $\mathcal S(\mathbb R)$，称为 **Schwartz 空间**。

这个定义要求 $f$ 及其每阶导数都比任意固定的负幂下降得快。对固定的导数阶数 $\ell$ 和任意 $k\ge0$，有
$$f^{(\ell)}(x)=O(|x|^{-k})\qquad(|x|\to\infty).$$
特别地，$f$ 及其所有导数都属于 $L^1(\mathbb R)$，且 $x^mf^{(\ell)}(x)\in L^1(\mathbb R)$ 对所有非负整数 $m,\ell$ 都成立。

**常见例子**

1. Gaussian 函数 $f(x)=e^{-\alpha x^2}$，其中 $\alpha>0$，属于 $\mathcal S(\mathbb R)$。
2. 光滑且具有紧支撑的函数属于 $\mathcal S(\mathbb R)$。例如，设 $a<b$，则
   $$\eta(x)=\begin{cases}\exp\!\left(-\dfrac1{(x-a)(b-x)}\right),&a<x<b,\\[4pt]0,&x\notin(a,b)\end{cases}$$
   是一个光滑的紧支撑函数。

**注** “紧支撑”本身不保证属于 $\mathcal S(\mathbb R)$，还必须在整个实线上光滑。例如区间的示性函数虽有紧支撑，却不是 Schwartz 函数。

## 6. 傅里叶分析中的常用性质

以下性质对 $f,g\in\mathcal S(\mathbb R)$ 成立。在这个函数空间中，积分、求导和分部积分都有良好的适用条件。

1. **傅里叶变换保持 Schwartz 空间：**$$f\in\mathcal S(\mathbb R)\quad\Longrightarrow\quad\widehat f\in\mathcal S(\mathbb R).$$ 因而 $\widehat f$ 也光滑，并且连同所有导数一起快速下降。
2. **傅里叶反演：**$$f(x)=\int_{\mathbb R}\widehat f(\xi)e^{2\pi ix\xi}\,d\xi.$$
3. **求导转为乘法：**$$\widehat{f^{(k)}}(\xi)=(2\pi i\xi)^k\widehat f(\xi).$$ 这使微分方程中的求导运算在频率空间中变为乘法。
4. **卷积转为乘法：**若 $(f*g)(x)=\int_{\mathbb R}f(x-y)g(y)\,dy$，则 $$\widehat{f*g}(\xi)=\widehat f(\xi)\widehat g(\xi).$$
5. **能量等式：**$$\int_{\mathbb R}|f(x)|^2\,dx=\int_{\mathbb R}|\widehat f(\xi)|^2\,d\xi.$$
6. **Gaussian 函数的变换：**$$\widehat{e^{-\alpha x^2}}(\xi)=\sqrt{\frac{\pi}{\alpha}}\,e^{-\pi^2\xi^2/\alpha},\qquad\alpha>0.$$ 特别地，在本文的归一化约定下，$e^{-\pi x^2}$ 的傅里叶变换仍是 $e^{-\pi\xi^2}$。

**使用时的区分** 适度下降条件通常用于先保证 $f\in L^1$，使傅里叶变换能够按积分定义；Schwartz 条件更强，使求导、反演、卷积及反复分部积分可以在同一个函数空间内顺利进行。