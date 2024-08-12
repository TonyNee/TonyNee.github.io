---
title: '第一章 线性空间与线性变换'
date: '2023-09-06 17:30:00'
categories: 
- 研究生课程
- 上学期
- 矩阵论
tags: 
- Math
updated:
type:
comments:
description:
keywords:
top_img:
mathjax: true
katex:
aside:
aplayer:
highlight_shrink:
random:
---

<!-- 索引语 -->
{% note blue 'fas fa-bullhorn' flat %}
&emsp;&emsp;线性空间是某一类事物从量方面的一个数学抽象，线性变换则是反映线性空间元素之间最基本的线性函数关系。
{% endnote %}

<!-- 一级标题 -->
# 1. 线性空间

## 1.1 线性空间的概念
{% note pink modern %}
定义 1.1&emsp;&emsp;设*V*是一个以 ***α***，***β***，***γ***，...为元素的非空集合，*F*是一个数域。在其中定义两种运算，一种叫加法：∀***α***，***β***∈*V*，***α***+***β***∈*V*；另一种叫数量乘法：∀*k*∈*F*，***α***∈*V*，*k**α***∈*V*，并且满足下面八条运算法则：
&emsp;&emsp;（1）加法交换律：***α***+***β***=***β***+***α***；
&emsp;&emsp;（2）加法结合律：(***α***+***β***)+***γ***=***α***+(***β***+***γ***)；
&emsp;&emsp;（3）数乘结合律：(*kl*)***α***=*k*(*l**α***)；
&emsp;&emsp;（4）数量分配律：(*k+l*)***α***=*k**α***+*l**α***；
&emsp;&emsp;（5）元素分配律：*k*(***α***+***β***)=*k**α***+*k**β***；
&emsp;&emsp;（6）*V*中存在{% label 零元素 orange %}：∃**$α_0$**∈*V*，∀***α***∈*V*，***α***+**$α_0$**=***α***，记 **$α_0$**=**0**；
&emsp;&emsp;（7）{% label 负元素 orange %}存在：∀***α***∈*V*，∃***β***∈*V*，使 ***α***+***β***=**0**，记 ***β***=-***α***；
&emsp;&emsp;（8）{% label 存在1 orange %}∈*F*，1·***α***=***α***；
则称*V*为数域*F*上的**线性空间**。*V*中元素成为**向量**。*F*为实（复）数域时，称*V*是实（复）线性空间。
{% endnote %}

{% note green modern %}
定理 1.1&emsp;&emsp;线性空间*V*具有如下性质：
（1）*V*中的零元素唯一；
（2）*V*中任意元素的负元素唯一；
（3）设0为数零，**0**为*V*中零向量，则
- 0·**α**=**0**；
- *k*·**0**=**0**，*k*∈*F*；
- 若*k*·**α**=**0**，则一定有*k*=0或**α**=**0**；
- (-1)**α**=-**α**。
{% endnote %}

&emsp;&emsp;举例：
- 矩阵空间：    {% raw%} $ V=F^{m×n}={A=(a_{ij})_{m×n} | a_{ij}∈F} $ {% endraw %}
- 多项式空间：  {% raw%} ${P_{\rm{n}}}[x] = \{ \sum\limits_{i = 0}^{n - 1} {{a_i}{x^i}|} {a_i} \in R\} $ {% endraw %}
注意：次数等于n-1的多项式集合不是线性空间，因为加法不封闭。





## 1.2 线性空间的基与维数
{% note pink modern %}
定义 1.2&emsp;&emsp;设*V*是线性空间，若存在一组线性无关的向量 **$α_1$**，**$α_2$**，...，**$α_{n}$**，使空间中任意向量可由它们线性表示，则称向量组{ **$α_1$**，**$α_2$**，...，**$α_{n}$**}为*V*的一组**基**。基所含向量个数为*V*的**维数**，记为dim*V*=n，n≤+∞。
{% endnote %}


## 1.3 坐标

## 1.4 基变换与坐标变换

## 1.5 子空间

### 1.5.1 子空间概念
{% note pink modern %}
定义 1.5&emsp;&emsp;设{% raw %} ${V_n}(F)$ {% endraw %}为线性空间，*W*是*V*的非空子集合。若*W*的元素关于*V*中加法与数乘向量运算也构成线性空间，则称*W*是*V*的一个子空间。
{% endnote %}

{% note green modern %}
定理 1.5&emsp;&emsp;设*W*是线性空间{% raw %} ${V_n}(F)$ {% endraw %}的非空子集合，则*W*是{% raw %} ${V_n}(F)$ {% endraw %}的子空间的充要条件是：
- 若{% raw %} $\alpha ,\beta  \in W$ {% endraw %}，则{% raw %} $\alpha  + \beta  \in W$ {% endraw %}；
- 若{% raw %} $\alpha  \in W$ {% endraw %}，{% raw %} $k  \in F$ {% endraw %}，则{% raw %} $k\alpha  \in W$ {% endraw %}。
{% endnote %}

&emsp;&emsp;证明非空子集合是否为子空间，仅需使用定理1.5即可。
&emsp;&emsp;由此可证得，线性空间{% raw %} ${V_n}(F)$ {% endraw %}中的一组向量{% raw%} ${\alpha _1},{\alpha _2},....,{\alpha _m}$ {% endraw%}所构成的一切线性组合的集合是*V*的一个子空间，即
{% raw %} $$L\{ {\alpha _1},{\alpha _2},....,{\alpha _m}\}  = \{ \alpha |\alpha  = \sum\limits_{i = 1}^m {{k_i}{\alpha _i},} {k_i} \in F\} $$ {% endraw %}
若{% raw%} ${\alpha _1},{\alpha _2},....,{\alpha _n}$ {% endraw%}是*V*的一组基，则{% raw %} ${V_n}(F)$ {% endraw %}可表示为
{% raw %} $${V_n}(F) = L\{ {\alpha _1},{\alpha _2},....,{\alpha _m}\} $$ {% endraw %}
&emsp;&emsp;对于矩阵{% raw %} $A \in {F^{m{\rm{ \times n}}}}$ {% endraw %}，则有
零空间：&emsp;&emsp;{% raw %} $N(A) = \{ X|AX = \overrightarrow 0 \}  \subseteq {F^n},$ {% endraw %}
列空间：&emsp;&emsp;{% raw %} $R(A) = L\{ {A_1},{A_2},...,{A_n}\}  \subseteq {F^n}，$ {% endraw %}

### 1.5.2 交空间、和空间
{% note green modern %}
定理 1.6&emsp;&emsp;设{% raw%} ${W_1}$ {% endraw%}，{% raw%} ${W_2}$ {% endraw%}是线性空间*V*的子空间，则有
- {% raw%} ${W_1}$ {% endraw%}与{% raw%} ${W_2}$ {% endraw%}的交集{% raw%} ${W_1} \cap {W_2} = \{ \alpha |\alpha  \in {W_1}\& \alpha  \in {W_2}\} $ {% endraw%}是*V*的子空间，称为{% raw%} ${W_1}$ {% endraw%}与{% raw%} ${W_2}$ {% endraw%}的交空间；
- {% raw%} ${W_1}$ {% endraw%}与{% raw%} ${W_2}$ {% endraw%}的和
{% raw%} $${W_1} + {W_2} = \{ \alpha |\alpha  = {\alpha _1} + {\alpha _2},{\alpha _1} \in {W_1},{\alpha _2} \in {W_2}\} $$ {% endraw%} 是*V*的子空间，成为{% raw%} ${W_1}$ {% endraw%}与{% raw%} ${W_2}$ {% endraw%}的和空间。
{% endnote %}
&emsp;&emsp;一般地，若{% raw%} ${W_1} = L\{ {\alpha _1},{\alpha _2},....,{\alpha _s}\} ${% endraw%}，{% raw%} ${W_2} = L\{ {\beta _1},{\beta _2},....,{\beta _r}\} $ {% endraw%}，则有
{% raw%} $${W_1} + {W_2} = L\{ {\alpha _1},{\alpha _2},....,{\alpha _s},{\beta _1},{\beta _2},....,{\beta _r}\} $$ {% endraw%} 。
{% raw%} $${W_1} \cap {W_2} \subseteq {W_i} \subseteq {W_1} + {W_2} \subseteq V$${% endraw%} 
{% raw%} $$\dim ({W_1} \cap {W_2}) \le \dim ({W_i}) \le \dim ({W_1} + {W_2}) \le \dim (V)$${% endraw%}

### 1.5.3 维数定理
{% note green modern %}
定理 1.7（维数定理）&emsp;&emsp;设{% raw%} ${W_1}$ {% endraw%}和{% raw%} ${W_2}$ {% endraw%}是线性空间*V*的子空间，则有如下维数公式：
$$\dim {W_1} + \dim {W_2} = \dim ({W_1} + {W_2}) + \dim ({W_1} \cap {W_2})$$
证明思路：基扩充方法（从{% raw%} ${W_1} \cap {W_2}$ {% endraw%}的基出发）
{% endnote %}
### 1.5.4 子空间的直和
{% note pink modern %}
定义 1.6&emsp;&emsp;设{% raw%} ${W_1}$ {% endraw%}，{% raw%} ${W_2}$ {% endraw%}是线性空间*V*的子空间，{% raw%} $W = {W_1} + {W_2}$ {%endraw%}，如果{% raw%} ${W_1} \cap {W_2} = \{ \overrightarrow 0 \} $ {% endraw%}，则称*W*是{% raw%} ${W_1}$ {% endraw%}与{% raw%} ${W_2}$ {% endraw%}的直和子空间，记为
{% raw%} $$W = {W_1} \oplus {W_2}$$ {% endraw%}。
{% endnote %}

{% note green modern %}
定理 1.8&emsp;&emsp;


{% endnote %}




# 2. 内积空间
## 2.1 欧氏空间与酉空间
{% note pink modern %}
定义 1.7&emsp;&emsp;对数域*F*上的*n*维线性空间{% raw%} ${V_n}(F)$ {% endraw%}，定义一个从{% raw%} ${V_n}(F)$ {% endraw%}中向量到数域*F*的二元运算，记为{% raw%} **$(\alpha ,\beta )$** {% endraw%}，即{% raw%} $(\alpha ,\beta ):{V_n}(F) \to F $ {% endraw%} 


{% endnote %}





# 3. 线性变换




$$ R_z=\begin{bmatrix}\cos\sigma_3&\sin\sigma_3&0\\ -\sin\sigma_3&\cos\sigma_3&0\\0&0&1\end{bmatrix}$$