
> [!note] n次单位根的一些性质
> 记 $w_i$为 n 次单位根，$w_0=1$有：
> 1. $w_i^n=1$，n次归为一
> 2. $w_i^{n+1}=w_i$，走一圈回原处
> 3. $w_iw_j=w_{i+j}$，相乘即次序相加
> 4. $\sum_{i=1}^nw_i=0$，全和为0

## 应用

> [!question] 
> 求n阶循环矩阵的行列式

> 记矩阵A为n阶循环矩阵，其第一行为$(a_0,a_1\ldots_{n-1})$，记$f(x)=a_{n-1}x^{n-1}+a_{n-2}x^{n-2}+\ldots+a_1x+a_0$
> 对向量$W_i=(1,w_i,w_i^2\ldots w_j^{n-1})^T$有$$AW_i=f(w_i)W_i$$
> 再记$W=(W_0,W_1\ldots W_{n-1})$，就有：$$AW=W\operatorname{diag}(f(w_0),f(w_1)\ldots f(w_{n-1}))$$
> 两边取行列式，再由$|W|\not =0$可得结论

> [!question]
>  求$(1+x)^n$ 展开式中次数为3的倍数的项的系数(包括常数项，因为3可以整除0)

> 记$1,\epsilon_1,\epsilon_2$为1的三个单位根，我么注意到：$$1^k+\epsilon_1^k+\epsilon_2^k=\begin{cases}3,k\equiv0(mod 3)\\0,k\not\equiv0(mod 3)\end{cases}$$
> 于是$2^n+(1+\epsilon_1)^n+(1+\epsilon_2)^n=\frac{2^n+2\cos(\frac{n\pi}{6})}{3}$即为所求


