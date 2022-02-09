# 笔记目录

[TOC]

## ☄ 说明

- 此笔记对应视频来自[bilibili](https://www.bilibili.com/)视频网站，视频网址[《线性代数》高清教学视频 “惊叹号”系列 宋浩老师](https://www.bilibili.com/video/av29971113)
- 此笔记改自github用户[cy69855522](https://github.com/cy69855522)，开源项目地址[Miao-A-SongHao-Linear-Algebra-Notes](https://github.com/cy69855522/Miao-A-SongHao-Linear-Algebra-Notes)，此笔记完善了大部分细节并补充了绝大多数晦涩难懂的证明过程
- 此笔记建议搭配视频一同食用最佳~
- 笔记作者：zijiren233

## ☄ P1 二阶三阶行列式

### ⌚ 02:48 二阶行列式划线计算

* 行列式一定是方的

### ⌚ 15:00 三阶行列式划线计算

* 主对角线：╲
* 副对角线：╱

### ⌚ 22:29 N阶行列式预备知识

* 排列：1，2，……，n组成的一个有序数组叫n级排列，中间不能缺数
  * 如`3级排列：123，132，213，231，312，321`
* 逆序：大数排在小数前面
* 逆序数：逆序的总数
* 奇/偶排列：逆序数为奇/偶
* 标准排列：`123……N`
* 对换：交换排列中的两个数
  * 做一次对换，排列奇偶性改变

### ⌚ 24:21 名场面：宋浩点名田莎莎等

## ☄ P2 n阶行列式

### ⌚ 00:55 N阶行列式计算

* 按行展开：
  * 行标取标准排列
  * 列标取排列的所有可能，从不同行不同列取出n个元素相乘
  * 共有N!项
  * 每一项的符号由列标排列的奇偶性决定，偶正奇负

### ⌚ 20:50 下三角行列式

* 右上方三角形区域元素全部为0
* 下三角行列式 = 主对角线元素相乘

### ⌚ 23:14 上三角行列式

* 左下方三角形区域元素全部为0
* 上三角行列式 = 主对角线元素相乘

### ⌚ 24:40 对角线行列式

* 只有主对角线上有数

### ⌚ 25:30 副对角线行列式

* 副对角线行列式 = `(-1)^(n(n-1)/2) * 副对角线元素相乘`
* 符号来自于按行展开

### ⌚ 31:00 三角行列式总结

![三角行列式](https://oss.pyhdxy.com/img/2022/02/03/00:00:14-三角行列式.jpg)

### ⌚ 31:09 行列式三种定义

* 1.按行展开，==符号==由列标排列决定

* 2.按列展开，==符号==由行标排列决定

* 3.胡乱展开，==符号==由行标排列逆序数和列标排列逆序数之和决定 ：

$$
(-1)^{\left[N\left(i1,i2,……,iN\right)+N\left(j1,j2,……,jN\right)\right]}
$$

## ☄ P3 行列式的性质

* 行列式对行成立的性质对列也成立

### ⌚ 00:25 性质一 转置

* 转置：把行按列写
* 行列式转置后值不变
* 行列式转置的转置等于本身

### ⌚ 11:48 性质二 两行互换

* 行列式两行互换，值变号

### ⌚ 20:38 性质三 两行相同

* 行列式两行相同，等于0

### ⌚ 23:10 性质四 行公因子k

* 行列式某行都乘以k，等于用k乘以这个行列式。即行列式某一行有公因子k，可往外提一次
* 若行列式所有元素都有公因子k，k外提N次

### ⌚ 28:05 性质五 两行成比例

* 行列式两行成比例，则行列式值为0
* 某一行全为0，则行列式为0

### ⌚ 34:20 性质六 和分解

* 若行列式某一行元素都可以表示为两项和，则行列式等于两个行列式相加

$$
\begin{vmatrix}
1+2 & 2+3 \\
3 & 3
\end{vmatrix}
=
\begin{vmatrix}
1 & 2 \\
3 & 3
\end{vmatrix}
+
\begin{vmatrix}
2 & 3 \\
3 & 3
\end{vmatrix}
$$

### ⌚ 43:36 性质七 行叠加

* 某一行乘以一个数加到另一行上去，行列式值不变

### ⌚ 51:12 行列式值计算通用法

* 将行列式化为上三角行列式，连乘对角线元素
  * 利用性质七将左下角元素从左到右从上到下消为0

## ☄ P4 行列式按行展开

### ⌚ 04:36 余子式

* 在行列式中选中某个元素，去掉所在行列，剩余的元素构成的行列式叫这个元素的余子式`M_ij，M代表余子式，i代表选中元素的行标，j列标，ij从1开始`

### ⌚ 07:42 代数余子式

* 在余子式前面加上符号`(-1)^(i+j)`

### ⌚ 09:38 降阶：行列式按某一行/列展开

* ==行列式的值== = 某一行所有元素乘以自己的代数余子式的积之和，列同理
  * [回到 求特征值](#⌚ 00:00 求特征值（计算含参行列式）思路)


### ⌚ 16:50 异乘变零定理

* 某行元素与另一行元素的代数余子式乘积之和为零


### ⌚ 27:17 拉普拉斯定理

* k阶子式：任取k行k列，交叉处构成的行列式为k阶子式
* k阶子式的余子式：除去选中行列，其余行列形成的子式为k阶子式的余子式
* k阶子式的代数余子式：多个符号`(-1)^所有行标与列标之和`

### ⌚ 30:17 拉普拉斯展开定理

* 取定k行，由k行元素组成的所有k阶子式与其代数余子式乘积之和 = 行列式值

### ⌚ 38:30 同阶行列式相乘

* 同阶行列式相乘的值 = 两个行列式做矩阵乘法后得到的行列式的值

## ☄ P5 行列式的计算（一）

### ⌚ 14:33 纯数字行列式计算

* 将行列式化为上三角行列式，连乘对角线元素

### ⌚ 21:50 已知行列式求余子式之和

* 构造新行列式

  <img src="https://oss.pyhdxy.com/img/2022/02/02/22:38:07-image-20220202223807104.png" alt="image-20220202223807104" align='left' style="zoom: 50%;" />

### ⌚ 30:06 对角线为x，其余为a的行列式计算技巧

- 制造行和
  $$
  \begin{align}
  &
  \begin{vmatrix}
  
  x & a & a & a \\
  a & \ddots & \ddots & \vdots \\
  a & \ddots & \ddots & \vdots \\
  a & \cdots & \cdots & x
  
  \end{vmatrix}
  =
  \begin{vmatrix}
  
  x+(n-1)a & a & a & a \\
  x+(n-1)a & \ddots & \ddots & \vdots \\
  x+(n-1)a & \ddots & \ddots & \vdots \\
  x+(n-1)a & \cdots & \cdots & x
  
  \end{vmatrix}
  =x+(n-1)a
  \begin{vmatrix}
  
  1 & a & a & a \\
  1 & \ddots & \ddots & \vdots \\
  1 & \ddots & \ddots & \vdots \\
  1 & \cdots & \cdots & x
  
  \end{vmatrix}
  \\
  &=x+(n-1)a
  \begin{vmatrix}
  
  1 & 0 & 0 & 0 \\
  1 & x-a & \ddots & \vdots \\
  1 & \ddots & \ddots & \vdots \\
  1 & \cdots & \cdots & x-a
  
  \end{vmatrix}
  
  =x+(n-1)a\,\times\,(n-1)(x-a)
  
  \end{align}
  $$
  

[回到 求秩方法](#⌚ 41:15 求秩方法)

[回到 求特征值](#⌚ 00:00 求特征值（计算含参行列式）思路)

## ☄ P6 行列式的计算（二）

### ⌚ 00:00 行列式计算基础思路

* 1.化成上三角
* 2.把某行/列尽可能多得化成0，然后展开

### ⌚ 01:05 三叉形行列式

* 加边法：在顶上加一行1，左边多出的一列（除第一行）为0，行列式值不变

### ⌚ 17:42 范德蒙德行列式

![范德蒙德行列式](https://oss.pyhdxy.com/img/2022/02/02/23:55:33-范德蒙德行列式.png )

### ⌚ 40:42 反对称行列式

* `a_ij = -a_ji`

* 主对角线全为0

* 上下位置对应成相反数

* 奇数阶，行列式值 D = 0
  $$
  \begin{align}
  
  D=
  
  \begin{vmatrix}
  0 & a & b\\
  -a & 0 & c\\
  -b & -c & 0
  \end{vmatrix}
  
  =
  (-1)^3\,
  
  \begin{vmatrix}
  0 & -a & -b\\
  a & 0 & -c\\
  b & c & 0
  \end{vmatrix}
  
  -D^T=-D
  
  \end{align}
  $$
  

### ⌚ 43:12 对称行列式

* `a_ij = a_ji`
* 主对角线无要求
* 上下位置对应相等

## ☄ P7 克莱姆法则

### ⌚ 00:05 解方程组

* n个方程，n个未知量

* D ≠ 0

* x_j = D_j / D，D为方程组系数构成的行列式，D_j代表把方程组值用于替换D的第j列得到的行列式，x_j代表解

  <img src="https://oss.pyhdxy.com/img/2022/02/02/23:56:00-克莱姆法则.png" alt="克莱姆法则" align='left' style="zoom:150%;" />

### ⌚ 09:11 解齐次线性方程组

* n个方程，n个未知量

* 齐次：方程组值都为0，即无常数

* 齐次方程，至少有零解

* `若 D ≠ 0，只有零解` `若 D = 0 <=> 有非零解`

  <img src="https://oss.pyhdxy.com/img/2022/02/02/23:56:29-克莱姆法则_齐次.png" alt="克莱姆法则_齐次" align='left' style="zoom:150%;" />

[回到 行列式判断线性相关](#⌚ 37:20 行列式判断线性相关)

## ☄ P8 矩阵概念

### ⌚ 22:20 矩阵和行列式比较

* 矩阵可以是不方的
* 零矩阵：元素都是0的矩阵为零矩阵（有形状）
* 负矩阵：A的负矩阵为-A，所有元素取相反数
* 方阵：行数 = 列数
* 单位阵E：对角线上为1，其余元素为0，一定为方阵
* 同型矩阵：形状相同
* 矩阵相等：同型且值对应相等
  * 零矩阵不一定相等，可能不同型
* 方阵的主对角线：╲，次对角线：╱，不是方阵则没有

## ☄ P9 矩阵运算（一）

### ⌚ 00:00 名场面：宋浩免费赠送自制知识卡片

### ⌚ 02:50 矩阵加减法

* 只有同型矩阵才能相加减
* 对应元素相加减

### ⌚ 07:53 矩阵数乘运算

* 用k乘以矩阵，相当于把==k乘以矩阵的所有元素==
  * 矩阵所有元素均有公因子，公因子外提一次（行列式是n次）

### ⌚ 13:58 矩阵乘法

* 前提：左矩阵列数 = 右矩阵行数
* 结果矩阵的行数 = 左矩阵行数，列数 = 右矩阵列数
* 结果矩阵第i行第j列的值 = 左矩阵第i行与右矩阵第j列对应元素乘积之和
* 宋氏七字：中间相等，取两头
* `AB 一般≠ BA` AB有意义，BA不一定有意义。若`AB = BA`，则称A，B可交换
* 左乘：在矩阵左边乘上一个矩阵，右乘同理
* `AB = 0 ≠> A=0 或 B=0`
* `AB = AC，A≠0 ≠> B=C`
* 与零矩阵左/右乘：零矩阵与任何矩阵相乘都为零矩阵
* 与单位阵左/右乘：`AE = A, EA = A`，此时E的形状可能不同
* `(AB)C = A(BC)`，AB顺序不可变
* `(A + B)C = AC + BC`，AB顺序不可变
* `k(AB) = (kA)B = A(kB)`，AB顺序不可变

## ☄ P10 矩阵运算（二）

### ⌚ 00:00 矩阵幂运算

* `A^0 = E`
* `A^k1 · A^k2 = A^(k1+k2)`
* `(A^k1)^K2 = A^k1k2`
* `(AB)^k 一般≠ A^k · B^k`
  * `(AB)^2 = ABAB ≠ A^2 · B^2 = AABB`
* `(A + B)^2 = A^2 + BA + AB + B^2 ≠ A^2 + 2AB + B^2`
  * `(A - B)^2 ≠ A^2 - 2AB + B^2`
* `(A + E)^2 = A^2 + 2AE + E^2`
* A^k^需满足A为方阵

### ⌚ 23:49 矩阵转置

* `A^T`代表`A`的转置，把行按列写
* `(A^T)^T = A`
* `(A + B)^T = A^T + B^T`
* `(kA)^T = kA^T`
* `(AB)^T = B^T · A^T`

## ☄ P11 特殊矩阵

### ⌚ 00:00 数量矩阵

* 数量矩阵：主对角线元素全部相等，其余元素为0

  * 数与数量矩阵相乘、数量矩阵的和、差、乘结果都是一个数量矩阵
  * 数量矩阵aE，和任意可乘矩阵B有 `(aE)B = B(aE) = aB`

  $$
  \begin{bmatrix}
  a & & & & \\
    & a & & \\
    & & a & \\
    & & & a \\
  \end{bmatrix}
  =a\rm E
  $$

### ⌚ 05:27 对角形矩阵

* 对角形矩阵：对角线上有值，其余为0

  * 对角线矩阵可以表示为`diag(a1, a2, ……, an)`，a~1~~~n~为对角线上的元素
  * 数量矩阵是特殊的对角型矩阵
  * 数和对角型的乘法、对角型矩阵加、减、乘后任然是对角型矩阵
  * 左乘、右乘==>左行右列

[回到 与对角形矩阵相似的条件](#⌚ 22:06 与对角形矩阵相似（对角化）的条件)
$$
\begin {align}

\begin {bmatrix}
a_1 & & &\\
& a_2 & & \\
& & \ddots & \\
& & & a_n
\end {bmatrix}
=diag(a_1,a_2,...,a_n)
\\

\begin {bmatrix}
k_1 & &\\
& k_2 & \\
& & k_3
\end {bmatrix}
\begin {bmatrix}
1 & 2 & 3\\
2 & 2 & 2 \\
8 & 8 & 8
\end {bmatrix}
=
\begin {bmatrix}
1k_1 & 2k_1 & 3k_1\\
2k_2 & 2k_2 & 2k_2 \\
8k_3 & 8k_3 & 8k_3
\end {bmatrix}
\\
\begin {bmatrix}
1 & 2 & 3\\
2 & 2 & 2 \\
8 & 8 & 8
\end {bmatrix}
\begin {bmatrix}
k_1 & &\\
& k_2 & \\
& & k_3
\end {bmatrix}
=
\begin {bmatrix}
1k_1 & 2k_2 & 3k_3\\
2k_1 & 2k_2 & 2k_3 \\
8k_1 & 8k_2 & 8k_3
\end {bmatrix}

\end {align}
$$

### ⌚ 12:45 三角型矩阵

* 上三角行矩阵
  * 主对角线之下的所有元素全为0
* 下三角形矩阵
  * 主对角线之上的所有元素全为0
* 数和三角型矩阵的乘积，以及三角型之间的和、差、积均是三角型

### ⌚ 14:00 对称\反对称矩阵

* 对称矩阵

  * `a_ij = a_ji`

  * ==对于对称矩阵A，`A^T = A`==

  * 两个同阶对称矩阵的和、差、数乘仍然是对称的，但是乘积一般不是对称的
    $$
    \begin {align}
    &A,B同阶对称，A^T=A,B^T=B\\
    &(1).\,(A + B)^T = A^T + B^T = A + B\\
    &(2).\,(A - B)^T = A^T - B^T = A - B\\
    &(3).\,(kA)^T=kA^T=kA\\
    &(4).\,(AB)^T=B^TA^T=BA≟AB
    \end {align}
    $$

  * A,B对称，AB对称 <=> A,B可交换

* 反对称矩阵

  * `a_ij = -a_ji`
  * 主对角线元素全部为0
  * ==对于反对称矩阵A，`A^T = -A`==

## ☄ P12 逆矩阵（一）

### ⌚ 03:04 方阵的行列式

### ⌚ 12:54 方阵的行列式的性质

* `|A^T| = |A|`
* `|kA| = k^n · |A|`
* `|AB| = |A| · |B|`

### ⌚ 24:28 伴随矩阵

* 只有方阵才有伴随矩阵
* 伴随矩阵`A^*`：求所有元素的代数余子式，**按行求的代数余子式按列放**，构成矩阵
* `AA^* = A^*A = |A|E`（只要是个方阵就永远成立）
* `|AA^*| = ||A|E| = |A|^n·|E|`
  * `|A|·|A^*| = |A|^n`
  * `|A^*| = |A|^(n-1)`

## ☄ P13 逆矩阵（二）

* 逆矩阵：设A为n阶方阵，存在同阶方阵B，使得`AB=BA=E`，则A的逆矩阵`A^-1 = B`
  * 未必所有方阵均可逆，比如零矩阵
  * 如果方阵可逆，逆矩阵唯一

### ⌚ 10:58 方阵可逆条件

* 若矩阵满足`|A| ≠ 0`，则其非奇异，非退化，满秩
* A可逆 <=> |A| ≠ 0，`A^-1 = 1/|A| · A^*`

* 若A、B都为n阶方阵，|A| ≠ 0 且 (AB = E **==或==** BA = E)，则`A^-1 = B`

### ⌚ 21:16 求逆矩阵方法

* 1.伴随矩阵法 `A^-1 = 1/|A| · A^*`

$$
\begin {align}
&
\text{例5: A+B=AB}\quad\text{证明(A-E)可逆}\\
&AB-A-B=0 \Rightarrow AB-A-B+E=E \Rightarrow (A-E)B-(A-E)E=E\\
&(A-E)(B-E)=E \Rightarrow (A-E)^{-1}=B-E


\end {align}
$$

* 2.初等变换法（一般用这个）

### ⌚ 47:33 解矩阵方程常见错误总结

* 1.注意提公因式的方向
* 2.矩阵不能减一个数字，需要补一个E
* 3.永远不要把矩阵放在分母上
* 4.一定要先判断矩阵是否可逆，再使用逆矩阵

### ⌚ 54:42 逆矩阵性质

* A可逆，则A^-1可逆，且`(A^-1)^-1 = A`
* A,B均可逆，则AB可逆，`（AB)^-1 = B^-1 A^-1`
* A可逆，则
  * A^T可逆
  * `(A^T)^-1 = (A^-1)^T`
  * 若 k ≠ 0，`(kA)^-1 = (A^-1)/k`
* 若A可逆，`|A^-1| = |A|^-1` 等号右边为A的行列式分之一

$$
AA^{-1}=E\,两边同时取行列式\,|A||A^{-1}|=1\,两边同时除以|A|\,\Rightarrow |A^{-1}|=\frac {1} {|A|}=|A|^{-1}
$$

* 若A可逆，`A^*`也可逆，`(A^*)^-1 = A/|A|`

$$
AA^*=|A|E\,左右同除|A|\Rightarrow (\frac {1} {|A|}A)A^*=E\quad即(A^*)^{-1} = \frac {1} {|A|}A
$$

### ⌚ 66:58 伴随矩阵`A^*`小专题

* 1.求代数余子式，按行求，按列放
* 2.`AA^* = A^*A = |A|E`
* 3.`|A^*| = |A|^(n-1)`
* 4.`A^-1 = A^*/|A|, A^* = |A|A^-1`
* 5.`(A^*)^* = |A|^(n-2) A` 此处用到小专题第四条结论和：若A可逆，`A^*`也可逆，`(A^*)^-1 = A/|A|`
* 6.`((A^*)^*)^* = |A|^((n-1)(n-2)+1) A^-1`

## ☄ P14 分块矩阵

### ⌚ 00:00 分块要求

* 横线/竖线一气到头

<img src="https://oss.pyhdxy.com/img/2022/02/03/20:53:07-image-20220203205305538.png" alt="image-20220203205305538" align='left' style="zoom: 50%;" />

### ⌚ 04:34 标准形

* 从左上角开始的一串1不断，其余全是0

$$
\begin {bmatrix}
1 & & & & &\\
& \ddots & & & &\\
& & 1 & & &\\
& & & 0 & &\\
& & & & \ddots & \\
& & & & & 0
\end {bmatrix}_{m\times n}
=
\begin {bmatrix}
E_{r\times r} & 0_{r\times (n-r)}\\
0_{(m-r)\times r} & 0_{(m-r)\times(n-r)}
\end {bmatrix}
$$

* 不一定是方阵

### ⌚ 09:34 分块矩阵加法

### ⌚ 10:39 分块矩阵数乘

### ⌚ 11:12 分块矩阵乘法

* 把每个子块看作元素，做矩阵乘法
* 前提：子块可乘

$$
\begin {bmatrix}
A_1 & A_2\\
A_3 & A_4
\end {bmatrix}
\begin {bmatrix}
B_1 & B_2\\
B_3 & B_4
\end {bmatrix}
=
\begin {bmatrix}
A_1B_1+A_2B_3 & A_1B_2+A_2B_4\\
A_3B_1+A_4B_3 & A_3B_2+A_4B_4
\end {bmatrix}
$$

### ⌚ 20:25 分块矩阵转置

* 先把子块视作元素求矩阵转置，再对每个子块求转置

### ⌚ 23:23 拉普拉斯展开定理在分块矩阵中的应用例题

* 例题：求特殊分块矩阵行列式

$$
\begin {align}

&H=
\begin {bmatrix}
A & C\\
0 & B
\end {bmatrix}
\quad A为m阶，B为n阶且都可逆\\
&证：|H|=
\begin {vmatrix}
A & C\\
0 & B
\end {vmatrix}
=
|A||B|\ne0
\quad（并非行列式的直接展开）\\
&用拉普拉斯展开：

\end {align}
$$

<img src="https://oss.pyhdxy.com/img/2022/02/03/21:24:06-image-20220203212405296.png" alt="image-20220203212405296" style="zoom:50%;" />

<img src="https://oss.pyhdxy.com/img/2022/02/03/21:35:54-image-20220203213553979.png" alt="image-20220203213553979" style="zoom:50%;" />
$$
H=
\begin {bmatrix}
A & C\\
0 & B
\end {bmatrix}\qquad
H^{-1}=
\begin {bmatrix}
A^{-1} & -A^{-1}CB^{-1}\\
0 & B^{-1}
\end {bmatrix}
$$


### ⌚ 39:08 分块矩阵的逆

* ==对角==分块矩阵求逆，直接把所有对角子块变为对应的逆矩阵

$$
\begin {align}
&
\begin {bmatrix}
A &\\
& B
\end {bmatrix}^{-1}
=
\begin {bmatrix}
A^{-1} &\\
& B^{-1}
\end {bmatrix}
\\
&推论:
\begin {bmatrix}
A_1 & & &\\
& A_2 & &\\
& & \ddots &\\
& & & A_s
\end {bmatrix}^{-1}
=
\begin {bmatrix}
A_1^{-1} & & &\\
& A_2^{-1} & &\\
& & \ddots &\\
& & & A_s^{-1}
\end {bmatrix}

\end {align}
$$

## ☄ P15 初等变换（一）

### ⌚ 00:00 三种初等变换

* 交换两行
* 用k(k≠0)乘某一行
* 某一行的L倍加到另一行上去
* 做初等变换要用箭头`→`，不能用等号`=`

### ⌚ 11:18 初等变换和行列式变换的对比

- 矩阵的初等变换和行列式变换没有任何关系
- A是方阵的时候

$$
\begin {cases}
交换两行 & A\to B \qquad|A|&=-|B|\\
用k(k\ne 0)乘某一行 & A\to B \qquad k|A|&=|B|\qquad \\
某一行乘一个数加到另一行上去 & A\to B \qquad |A|&=|B|
\end {cases}
$$

### ⌚ 24:50 矩阵化标准型

* 任何矩阵都通过初等变换化为标准型

### ⌚ 29:45 矩阵等价

* A经初等变换可得B，则A与B等价
  * 反身性：A与自身等价，`A≌A`
  * 对称性：`A≌B => B≌A`
  * 传递性：`A≌B, B≌C => A≌C`
* 任何矩阵等价于标准型

## ☄ P16 初等变换（二）

### ⌚ 00:00 初等方阵

* 对`E`做一次初等(行/列)变换得到的矩阵为初等方阵

<img src="https://oss.pyhdxy.com/img/2022/02/04/17:43:16-image-20220204174315021.png" alt="image-20220204174315021" style="zoom: 50%;" />

### ⌚ 09:15 初等方阵的行列式和逆矩阵

$$
\begin {align}
&
\begin {vmatrix}
 1 & & &\\
 & 1 & &\\
 & & 1 &\\
 & & & 1 
\end {vmatrix}
\to
\begin {vmatrix}
 & & 1 &\\
 & 1 & &\\
 1 & & &\\
 & & & 1 
\end {vmatrix}
=-1
\qquad |E(i,j)|=-1
\\
&
\begin {vmatrix}
 1 & & &\\
 & 1 & &\\
 & & 1 &\\
 & & & 1 
\end {vmatrix}
\to
\begin {vmatrix}
 1 & & &\\
 & 1 & &\\
 & & 5 &\\
 & & & 1 
\end {vmatrix}
=5
\qquad |E(i(k))|=k \quad (k\ne 0)
\\
&
\begin {vmatrix}
 1 & & &\\
 & 1 & &\\
 & & 1 &\\
 & & & 1 
\end {vmatrix}
\to
\begin {vmatrix}
 1 & & 5 &\\
 & 1 & &\\
 & & 1 &\\
 & & & 1 
\end {vmatrix}
=1
\qquad
|E(i,j(k))|=1 \quad (k\ne 0)
\end {align}
$$

* 初等方阵均可逆，其逆矩阵也是初等方阵

$$
E^{-1}(i,j)=E(i,j) \qquad E^{-1}(i(k))=E(i(\frac {1} {k})) \qquad E^{-1}(i,j(l))=E(i,j(-l))
$$

* 初等方阵的转置也是初等方阵

### ⌚ 14:56 初等方阵与矩阵做乘法

* 用初等变换得到的初等方阵左乘A，相当于对A实施同种初等==行==变换；右乘相当于==列==变换
  * 左行右列


$$
\begin {align}
&
E(2(3))=
\begin {bmatrix}
1 & &\\
 & 3 &\\
 & & 1
\end {bmatrix}
\qquad
E(1,3)=
\begin {bmatrix}
& & 1\\
& 1 &\\
1 & & 
\end {bmatrix}
\qquad
A=
\begin {bmatrix}
1 & 2 & 3\\
4 & 5 & 6\\
7 & 8 & 9
\end {bmatrix}
\\
&
E(2(3))A=
\begin {bmatrix}
1 & 2 & 3\\
12 & 15 & 18\\
7 & 8 & 9
\end {bmatrix}
\qquad
AE(1,3)=
\begin {bmatrix}
3 & 2 & 1\\
6 & 5 & 4\\
9 & 8 & 7
\end {bmatrix}
\end {align}
$$

### ⌚ 44:13 初等方阵用处

* 初等方阵是初等变换的载体
* 多个初等方阵可以化矩阵为标准形
  * 任意矩阵A，存在初等方阵P~1~,P~2~...P~s~ ,Q~1~,Q~2~...Q~t~ ,则 `P_s ··· P_1·A·Q_1 ··· Q_t` 为标准型
  * 若A与B等价，存在可逆矩阵P、Q，使得PAQ = B

* A可逆 <=> A的标准形为E
* A可逆 <=> A = 多个初等方阵的乘积

## ☄ P17 初等变换（三）

### ⌚ 00:00 初等变换法求逆矩阵

* 初等==行==变换法（只做初等行变换）：将A通过一系列初等行变换得到E之时，施加相同的初等行变换在E上可以使E变为A^-1。`(A, E) → (E, A^-1)`

$$
\begin {align}

A^{-1}&=Q_1Q_2\dots Q_t \qquad \qquad A^{-1}A&=Q_1Q_2\dots Q_tA \\
A^{-1}&=Q_1Q_2\dots Q_tE \qquad \qquad E&=Q_1Q_2\dots Q_tA\\
&即：\\
&Q_1Q_2\dots Q_tA = E\\
&Q_1Q_2\dots Q_tE = A^{-1}

\end {align}
$$

### ⌚ 13:51 解题过程总结

* 注1.先第1列再第2列再第3列……
* 注2.写整行，对整行操作
* 注3.第一列处理好后，第一行不再主动参与运算，后面同理
* 注4.做变换时矩阵与矩阵直接用箭头连接
* 注5.只做行变换
* 注6.不管是否可逆，如坐标化不成E，则不可逆，因为初等变换对于矩阵行列式值的改变是非零倍

## ☄ P18 矩阵的秩（一）

### ⌚ 00:00 k阶子式

* k阶子式：任取k行k列，交叉处构成的行列式为k阶子式

### ⌚ 02:10 矩阵的秩

* 非零子式的最高阶数：秩

[回到 行秩与列秩](#⌚ 00:00 行秩与列秩)

## ☄ P19 矩阵的秩（二）

### ⌚ 00:00 矩阵的秩

* 矩阵A的秩表示为`rank(A) = r(A)`
* 设A形状为`(m, n)`
  * 若`r(A) = m`，则==行==满秩
  * 若`r(A) = n`，则==列==满秩
  * 若`r(A) = min{m, n}`
  * 否则`r(A) < min{m, n}`，降秩
* 若A为方阵，满秩 <=> |A|≠ 0 <=> A可逆

### ⌚ 07:35 求矩阵的秩

* `r(A) = r` <=> 有一个r阶子式不为0，所有r+1阶为0
  * r+2阶及以上的子式一定为0，因为r+2阶子式按行展开中的余子式全为r+1阶，r+1阶子式全为0
  * 某一阶子式全为0，那么高阶子式全为0


### ⭐️⭐️⭐️⌚ 14:23 阶梯形矩阵

* 若有零行，零行在非零的下边
* 左起有首非零元左边零的个数随行数增加而严格增加
* 宋氏阶梯折线法：横线可跨多个数，竖线只跨一个数

### ⌚ 32:09 行简化阶梯形矩阵

* 行简化阶梯形：是阶梯
  * 非零行的首非零元是1
  * 首非零元所在列的其余元素是0
* 宋氏三步走（判断行简化阶梯形）
  * 画折线，判断阶梯形
  * ○画出首非零元
  * 首非零元画竖虚线，首非零元是1，其余都为0

### ⌚ 41:15 求秩方法

* 矩阵的秩 = 非零行的行数\首非零元的个数
* 初等（行、列）变换不改变秩
* 矩阵求秩：A–初等变换–>阶梯形–数非零行的行数–>OK

<img src="https://oss.pyhdxy.com/img/2022/02/04/20:43:06-image-20220204204304759.png" alt="image-20220204204304759" style="zoom: 50%;" />

[参考 制造行和的方法](#⌚ 30:06 对角线为x，其余为a的行列式计算技巧)

### ⌚ 53:11 秩的性质

* 1.`r(A) = r(A^T)`
* 2.任意矩阵乘以可逆矩阵，秩不变
  * 设`A(m, n), P为m阶可逆方阵, Q为n阶可逆方阵`
  * 则`r(A) = r(PA) = r(AQ) = r(PAQ)`，因为可逆矩阵可以表示为一系列初等方阵的积

### ⌚ 58:49 广告：宋浩打油诗

* 线性代数好深奥
* 矩阵方程行列式
* 数学如何呵呵学得好奥
* 山东财大找宋浩

## ☄ P20 向量的定义

### ⌚ 10:11 向量定义

* 向量：N个数成的有序数组，常用αβγ表示
* 维数：N
* 行向量：横着写，列向量：竖着写的向量
* 零向量：元素全为0
* 负向量：取相反数
* 向量相等：同维数，元素对应相等
* `kα = 0 <=> k=0 or α=0`

## ☄ P21 向量间的线性关系（一）

### ⌚ 00:00 线性关系

* 1.零向量可由任意向量组表示
* 2.向量组中任一向量可由向量组表示
* 3.任一向量都可由N维基本（单位）向量组表示

$$
\varepsilon_1=(1,0,...,0),\,\varepsilon_2=(0,1,...,0),\,...,\,\varepsilon_n=(0,0,...,1)
$$


### ⌚ 19:41 向量组的等价

* 同维
* 两个向量组可以相互线性表示
  * 反身性
  * 对称性
  * 传递性


$$
\begin {align}
&\{\alpha_1 \dots \alpha_m\}≌\{\beta_1\dots\beta_n\}\\
&\{\alpha_1 \dots \alpha_m\}≌\{\alpha_1 \dots \alpha_m\}\\
&\{\alpha_1 \dots \alpha_m\}≌\{\beta_1\dots\beta_n\}\quad \{\beta_1\dots\beta_n\}≌\{\alpha_1 \dots \alpha_m\}\\
&\{\alpha_1 \dots \alpha_m\}≌\{\beta_1\dots\beta_n\}\quad \{\beta_1\dots\beta_n\}≌\{\gamma_1 \dots \gamma_s\} \Rightarrow \{\alpha_1 \dots \alpha_m\}≌\{\gamma_1 \dots \gamma_s\}
\end {align}
$$

## ☄ P22 向量间的线性关系（二）

### ⌚ 00:00 线性相关与无关

* 线性相关：`α1,α2,...,αn`是n个m维向量组，若存在一组不全为0的`k1,k2,...,kn`，使得`k1α1 + k2α2 + ... + knαn = 0`，则向量组线性相关，否则无关
* 向量组中两向量成比例，向量组必线性相关
* 含零向量的向量组，必线性相关
* 一个零向量必相关
* 一个非零向量必无关
* 一个向量α相关 <=> α=0

### ⌚ 16:37 扩大后向量组与原向量组

* 若向量组线性相关，增加向量后依然相关
  * 部分组相关 → 整体相关
  * 整体组无关 → 部分无关

### ⌚ 25:40 接长后向量组与原向量组

* 线性无关的向量组接长后也线性无关；线性相关的向量组截短后也线性相关

### ⌚ 37:20 行列式判断线性相关

* n个n维向量（维数=个数）构成的行列式D≠0，那么线性无关，否则相关
  * [参考 解齐次线性方程组](#⌚ 09:11 解齐次线性方程组)


## ☄ P23 线性相关线性无关

### ⌚ 00:00 定理一

* `α1,α2,...,αs`相关 <=> 至少有一个向量可由其余向量表示

$$
\begin {align}
&系数不全为0，假设k_1\ne0\quad k_1\alpha_1+k_2\alpha_2+\dots+k_s\alpha_n=0
\\
\Rightarrow\,\alpha_1&=-\frac {k_2} {k_1}\alpha_2-\dots-\frac {k_s} {k_1}\alpha_n
\\
&=m_1\alpha_2+m_2\alpha_3+\dots\qquad(m_1,\dots,m_{n-1}可全为0，即\alpha_1为零向量)
\end {align}
$$

### ⌚ 04:32 定理二

* `α1,α2,...,αs`无关，`α1,α2,...,αs,βs`相关，β可由`α1,α2,...,αs`唯一表示

$$
\begin {align}
&存在不全为0的k_1\dots k_{s+1}\quad使得\quad k_1\alpha_1+\dots+k_s\alpha_s+k_{s+1}\beta=0
\\
&设k_{s+1}=0\qquad k_1\alpha_1+\dots+k_s\alpha_s=0\quad 与\alpha_1\dots\alpha_s线性无关矛盾
\\
&所以k_{s+1}\ne0 \qquad \beta = -\frac {k_1} {k_{s+1}}\alpha_1\dots-\frac {k_s} {k_{s+1}}\alpha_s
\\
&唯一性：
\\
&\beta=m_1\alpha_1+\dots+m_s\alpha_s

\qquad \beta=n_1\alpha_1+\dots+n_s\alpha_s
\\
&(m_1-n_1)\alpha_1+\dots+(m_s-n_s)\alpha_s=0
\\
&\Rightarrow\begin {cases}
m_1-n_1=0\\
\dots\\
m_s-n_s=0
\end {cases}
\quad\Rightarrow \beta可由\alpha_1\dots\alpha_s唯一表示
\end {align}
$$

### ⌚ 13:57 定理三：替换

* `α1,α2,...,αs`线性无关，可由`β1,β2,...,βt`表示，则s≤t
  * `α1,α2,...,αs`可由`β1,β2,...,βt`表示，s>t，则`α1,α2,...,αs`相关

### ⌚ 13:57 定理四

* 若向量个数m>向量维数n，则m个n维向量一定线性相关
  * n+1个n维向量相关
  * [回到 向量组的秩](#⌚ 12:45 向量组的秩)

### ⌚ 21:22 推论

* 两个==等价的（可以相互表示且同维）==线性无关组所含向量个数相同

## ☄ P24 向量组的秩（一）

### ⌚ 00:00 极大线性无关组

* `α1,α2,...,αs`的部分组`α1,α2,...,αr`满足：
  * `α1,α2,...,αr`无关
  * `α1,α2,...,αs`中每个向量均可由`α1,α2,...,αr`表示
  * 任意r+1个都线性相关

### ⌚ 08:04 极大线性无关组性质

* 一般来说，极大线性无关组不唯一
  * 同一个向量组的任意两个极大线性无关组，所含向量的个数相同

* 全是零的向量组，没有极大线性无关组
* 一个线性无关的向量组，它的极大无关组就是它本身
* 任何一个向量组和它的极大无关组是等价的，向量组中的任何向量都可由极大无关组表示

### ⌚ 12:45 向量组的秩

* 向量组的秩：极大无关组含向量的个数，记作`r(α1,α2,...,αs)`
* 如果全是零向量，秩为0
* `0 ≤ r(α1,α2,...,αs) ≤ min{向量个数s，向量维数n}`
  * [参考 线性相关向量个数与维数的关系](#⌚ 13:57 定理四)

* `α1,α2,...,αs`无关 <=> `r = s`
* `α1,α2,...,αs`相关 <=> `r < s`
* 若`α1,α2,...,αs`可由`β1,β2,...,βt`表示，那么`r(α1,α2,...,αs) ≤ r(β1,β2,...,βt)`
  * 等价的向量组有相同的秩

## ☄ P25 向量组的秩（二）

### ⌚ 00:00 行秩与列秩

* 行秩 = 列秩 = ==矩阵==的秩
  * [参考 矩阵的秩](#☄ P18 矩阵的秩（一）)


$$
A=
\begin {bmatrix}
1&1&1&1&1&3\\
0&2&1&1&5&6\\
9&1&0&0&1&1
\end {bmatrix}
\quad
行
\begin {cases}
\alpha_1=(1,1,1,1,1,3)\\
\alpha_2=(0,2,1,1,5,6)\\
\alpha_3=(9,1,0,0,1,1)
\end {cases}
\quad
列
\begin {cases}
\beta_1\\
\beta_2\\
\beta_3\\
\beta_4\\
\beta_5\\
\beta_6
\end {cases}
$$

### ⌚ 07:06 定理

* `r(AB) ≤ min{r(A), r(B)}`
  * `R(A)+R(B)-n ≤ R(AB) ≤ min{R(A),R(B)} ≤ max{R(A),R(B)} ≤ R(A:B) ≤ R(A) + R(B)`


### ⭐️⭐️⭐️⌚ 11:12 极大线性无关组的求法

* 初等==行变换==不改变矩阵==列向量组==的==线性关系==
  1. 不管原向量是行或列，均按列构成矩阵
  2. 只做行变换，化==行简化==阶梯型
  3. 首非零元所在列做极大无关组
  4. 其余向量表示系数直接写出

$$
\begin {align}
&
\begin {bmatrix}
1 & 2 & -2 & 3\\
-2 & -4 & 4 & -6\\
2 & 8 & -2 & 0\\
-1 & 0 & 3 & -6
\end {bmatrix}
\stackrel{行}{\longrightarrow}
\begin {bmatrix}
1 & 0 & -3 & 6\\
0 & 1 & \frac {1} {2} & -\frac {3} {2}\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end {bmatrix}
\\
&
\beta_1\beta_2是极大线性无关组 \to\alpha_1\alpha_2是极大线性无关组
\\
&
\beta_3=-3\beta_1+\frac {1} {2}\beta_2 \to \alpha_3=-3\alpha_1+\frac {1} {2}\alpha_2
\\
&
\beta_4=6\beta_1-\frac {3} {2}\beta_2 \to \alpha_4=6\alpha_1-\frac {3} {2}\alpha_2
\end {align}
$$

## ☄ P26 线性方程组

### ⌚ 00:00 二元一次方程与初等变换

* 求秩过程类似与求方程组的解，初等变换类似于消元

## ☄ P27 线性方程组有解判定

### ⌚ 00:00 有解判定

$$
\begin {cases}
x_1+x_2+x_3=1\\
x_1-x_2-x_3=-3\\
2x_1+9x_2+10x_3=11
\end {cases}
\quad
系数矩阵A=
\begin {bmatrix}
1 & 1 & 1\\
1 & -1 & -1\\
2 & 9 & 10
\end {bmatrix}
\quad
增广\bar A=
\left[
\begin {array}{ccc:c}
1 & 1 & 1 & 1\\
1 & -1 & -1 & -3\\
2 & 9 & 10 & 11
\end {array}
\right]
$$

* 系数矩阵`A`=方程组左边系数构成的矩阵
* 增广矩阵`Ā`=`A`右边加上结果那一列
* 设m为方程组个数，n为未知数个数，当`r(A) = r(Ā)`，有解
  * `r(A) = r(Ā) = n`，唯一解
  * `r(A) = r(Ā) < n`，无穷解
  * 当`r(A) ≠ r(Ā)`，无解

$$
\begin {align}
&
\left[
\begin {array}{ccc:c}
1 & 0 & 0 & 1\\
0 & 1 & 0 & 2\\
0 & 0 & 1 & 3
\end {array}
\right]
\quad
\begin {cases}
x_1=1\\
x_2=2\\
x_3=3
\end {cases}
\quad &唯一解
\quad r(A)=r(\bar A)=3=未知量的个数
\\
&
\left[
\begin {array}{ccc:c}
1 & 0 & 1 & 5\\
0 & 1 & 1 & 9\\
0 & 0 & 0 & 0
\end {array}
\right]
\quad
\begin {cases}
x_1=5-x_3\\
x_2=9-x_3\\
\
\end {cases}
\quad &无穷解
\quad r(A)=r(\bar A)=2<未知量的个数
\\
&
\left[
\begin {array}{ccc:c}
1 & 0 & 1 & 3\\
0 & 1 & 0 & 4\\
0 & 0 & 0 & 1
\end {array}
\right]
\quad
\begin {cases}
x_1+x_3=3\\
x_2=4\\
0=1
\end {cases}
\quad &无解
\quad r(A)=2\ne r(\bar A)=3=未知量的个数
\end {align}
$$

### ⌚ 16:10 判断秩、解的过程

<img src="https://oss.pyhdxy.com/img/2022/02/02/23:57:17-求解.png" alt="求解"  />

* 行简化阶梯型首非零元`1`的个数就是n

## ☄ P28 齐次方程组的解

### ⌚ 00:00 齐次方程组

* 一定有解，至少有零解，`r(A) = r(Ā)`
* `r(A) = n` <=> 唯一零解
* `r(A) < n` <=> 有非零解/无穷解
* 方程个数m < 未知量个数n，有非零解，`r(A) ≤ min{m, n} = m < n`
* m = n 有非零解 <=> `|A| = 0` <=> `r(A) < n` <=> A不可逆
  * 只有零解 <=> `|A| ≠ 0` <=> `r(A) = n` <=> A可逆
  * r(A)等于n 对于矩阵阵A来说就是A满秩，A满秩所以A的行列式不等于零，而对于A的向量组来说A的行列式不等于零，所以线性无关，k只能全部取零，所以只有零解。

* 解齐次线性方程组可直接写系数矩阵A，不用写增广矩阵Ā

## ☄ P29 方程组解的结构（一）

### ⌚ 00:00 齐次方程组解的结构

* 两解`(η1，η2)`相加仍是解
* 解的倍数`kη`仍然解

### ⌚ 06:54 基础解系

* `η1, η2, ..., ηs`线性无关
  * 任何解可由`η1, η2, ..., ηs`表示

### ⌚ 08:56 齐次方程基础解系求法

* 列出系数矩阵`A`
  * 只做初等行变换化为行简化阶梯型
  * 得到首非零元的表示
  * 对自由项取极大无关组（One-Hot）并带入所有x即可得到基础解系

$$
\begin {align}
&
A=[\dots ] \stackrel{行}{\longrightarrow}
\begin {bmatrix}
1 & 0 & -\frac {9} {4} & -\frac {3} {4} & \frac {1} {4}\\
0 & 1 & \frac {3} {4} & -\frac {7} {4} & \frac {5} {4}\\
0 & 0 & 0 & 0 & 0
\end {bmatrix}
\Rightarrow
\begin {cases}
x_1=\frac {9} {4}x_3+\frac {3} {4}x_4-\frac {1} {4}x_5
\\
x_2=-\frac {3} {4}x_3+\frac {7} {4}x_4-\frac {5} {4}x_5
\end {cases}
\quad x_3,x_4,x_5是自由未知量
\\
&
令
\begin {bmatrix}
x_3\\
x_4\\
x_5
\end {bmatrix}
取
\begin {bmatrix}
1\\
0\\
0
\end {bmatrix}
\begin {bmatrix}
0\\
1\\
0
\end {bmatrix}
\begin {bmatrix}
0\\
0\\
1
\end {bmatrix}
\Rightarrow
\eta_1=
\begin {bmatrix}
\frac {9} {4}\\
-\frac {3} {4}\\
1\\
0\\
0
\end {bmatrix}
\quad
\eta_2=
\begin {bmatrix}
\frac {3} {4}\\
-\frac {7} {4}\\
0\\
1\\
0
\end {bmatrix}
\quad
\eta_3=
\begin {bmatrix}
-\frac {1} {4}\\
-\frac {5} {4}\\
0\\
0\\
1
\end {bmatrix}
\quad
\eta_1,\eta_2,\eta_3是基础解系
\\
&
(1).\eta_1,\eta_2,\eta_3线性无关\\
&
(2).任意解可由\eta_1,\eta_2,\eta_3线性表示\quad
\begin {bmatrix}
x_1\\
x_2\\
x_3\\
x_4\\
x_5
\end {bmatrix}
=
\begin {bmatrix}
\frac {9} {4}x_3+\frac {3} {4}x_4-\frac {1} {4}x_5\\
-\frac {3} {4}x_3+\frac {7} {4}x_4-\frac {5} {4}x_5\\
x_3+0x_4+0x_5\\
0x_3+x_4+0x_5\\
0x_3+0x_4+x_5
\end {bmatrix}
=
\begin {bmatrix}
\frac {9} {4}x_3\\
-\frac {3} {4}x_3\\
x_3\\
0x_3\\
0x_3
\end {bmatrix}
+
\begin {bmatrix}
\frac {3} {4}x_4\\
\frac {7} {4}x_4\\
0x_4\\
x_4\\
0x_4
\end {bmatrix}
+
\begin {bmatrix}
\frac {1} {4}x_5\\
\frac {5} {4}x_5\\
0x_5\\
0x_5\\
x_5
\end {bmatrix}
\\
&=x_3\eta_1+x_4\eta_2+x_5eta_3
\end {align}
$$

* 解个数：`n - r(A)`
* 理解：齐次线性方程组其实就是对各个变量`x1,x2,...,xn`间关系的限制，通过初等行变换可以消除潜在的非自由变量，矩阵的秩指关系的最简表示个数，在此处代表非自由变量的个数，基础解系实际上是由自由变量决定的

齐次方程组的通解就是常数与基础解系积的和，可以表示任意一个解

* 不在左边的都是自由未知量

### ⭐️⭐️⭐️⌚ 45:26 定理

* 若矩阵`A_m*n`和`B_n*s`满足`AB = 0_m*n`，则`r(A) + r(B) ≤ n`
  * 推理：
  * `AB = 0` => A左乘B的每一列都为0 => B的每一列都是A的一组解 => `r(B) = B的列秩 ≤ A的自由变量数 = n（A列数，也就是A中变量x的个数） - r(A)`

$$
\begin {align}
&
A_{m\times n}\quad B_{n\times s} \quad AB=0_{m\times s}\quad 则r(A)+r(B) \le n
\\
&
证明：B=(\beta_1,\beta_2,\dots,\beta_s) \quad AB=(A\beta_1,A\beta_2,\dots,A\beta_s)=(0,0,\dots,0)
\\
&
A\beta_i=0\quad i=1,2,\dots,s \quad \beta_i是Ax=0的解
\\
&
1)\,\,r(A)=n \quad 唯一零解 \quad \beta_i=0 \quad r(A) \le n \quad 成立
\\
&
2)\,\,r(A)<n \quad 有无穷解 \quad 基础解系中有n-r(A)个 \quad r(B)=r(\beta_1,\beta_2,\dots,\beta_s) \le n-r(A)
\\
&
\Rightarrow r(A)+r(B) \le n
\end {align}
$$

## ☄ P30 方程组解的结构（二）

### ⌚ 00:00 导出组

* 设非齐次线性方程组为`Ax = b`，则其导出组为`Ax = 0`
* 设`α_1,α_2`为`Ax = b`的解，`α_1-α_2`是`Ax = 0`的解
* 设α为`Ax = b`的解，η为`Ax = 0`的解，则`A(α + η) = b` => `α + η`是`Ax = b`的解

### ⌚ 04:27 非齐次方程组解的结构

* 特解：满足非齐次方程组的随便一个解
* 非齐次方程组的解 = 特解 + 导出组的通解
* 求特解：化`Ā`至行最简阶梯型，得到首非零元表示，令所有自由变量为0，得到一个特解

<img src="https://oss.pyhdxy.com/img/2022/02/05/23:16:53-image-20220205231651756.png" alt="image-20220205231651756" style="zoom: 50%;" />

<img src="https://oss.pyhdxy.com/img/2022/02/05/23:23:05-image-20220205232304565.png" alt="image-20220205232304565" style="zoom: 50%;" />

## ☄ P32 矩阵的特征值与特征向量（一）

### ⌚ 00:00 矩阵的特征值与特征向量

* 设A为n阶**方**阵，对一个数λ，存在非零列向量α，使得`Aα = λα`
  * 则λ为一个特征值
  * α为λ对应的特征向量
  * λ可为0
  * α不可为0

### ⌚ 08:35 求特征值

* `Aα = λα` => `(λE - A)α = 0`
  
  * `(λE - A)x = 0`有非零解 <=> `|λE - A| = 0`
  
* 特征矩阵：`λE - A`

* 特征多项式：`|λE - A|`化简后

* 特征方程：`|λE - A| = 0`

* 特征值/特征根：`x`

* 若α为λ对应的特征向量，则cα也是λ对应的特征向量，c为常数，c ≠ 0

  * $$
    A\alpha=\lambda\alpha \quad cA\alpha=c\lambda\alpha \quad A(c\alpha)=\lambda(c\alpha)
    $$

* α对应唯一一个λ，λ可对应多个α

* 若`α1, α2`都为λ对应的特征向量，则`c1α1 + c2α2`是λ的特征向量

  * $$
    \begin {align}
    &
    A\alpha_1=\lambda\alpha_1\quad
    A\alpha_2=\lambda\alpha_2\\
    A(c_1\alpha_1+c_2\alpha_2)=c_1&A\alpha_1+c_2A\alpha_2=c_1\lambda\alpha_1+c_2\lambda\alpha_2=\lambda(c_1\alpha_1+c_2\alpha_2)
    \end {align}
    $$


## ☄ P33 矩阵的特征值与特征向量（二）

### ⌚ 00:00 求特征值（计算含参行列式）思路

* 把某行尽可能化为零，[按行展开](#☄ P4 行列式按行展开)
* 提含参数的公因子
* 每行加起来相等，[制造行和](#⌚ 30:06 对角线为x，其余为a的行列式计算技巧)

$$
\begin {align}
&
A\alpha=\lambda\alpha\quad |\lambda E-A|=0\quad
A=\begin {bmatrix}
-1 & 1 & 0\\
-4 & 3 & 0\\
1 & 0 & 2
\end {bmatrix}
\\
&
解：\alpha E-A=
\begin {bmatrix}
\lambda & &\\
 & \lambda &\\
  & & \lambda
\end {bmatrix}
-
\begin {bmatrix}
-1 & 1 & 0\\
-4 & 3 & 0\\
1 & 0 & 2
\end {bmatrix}
=
\begin {bmatrix}
\lambda+1 & -1 & 0\\
4 & \lambda-3 & 0\\
-1 & 0 & \lambda-2
\end {bmatrix}
\\
&
按第三行展开（不要直接展开）=(\lambda-2)(-1)^{3+3}
\begin {vmatrix}
\lambda+1 & -1\\
4 & \lambda-3
\end {vmatrix}
=(\lambda-2)(\lambda-1)(\lambda-1)
\\
&
\lambda_1=\lambda_2=1 \quad \lambda_3=2 \qquad (\lambda E-A)\alpha=0\,\,(\alpha\ne0)
\qquad (\lambda E-A)x=0\,\,(方阵，齐次，非零解)\\
&
1)\lambda_1=\lambda_2=1时 \qquad \alpha E-A=
\begin {bmatrix}
2 & -1 & 0\\
4 & -2 & 0\\
-1 & 0 & -1
\end {bmatrix}
\stackrel{行简化}{\longrightarrow}
\begin {bmatrix}
\dots
\end {bmatrix}
\Rightarrow
\begin {cases}
\dots\\
\dots
\end {cases}
\qquad
\eta=
\begin {bmatrix}
1\\
2\\
-1
\end {bmatrix}
\\
&
x的解系=c_1\eta\,\,(c_1\ne0)
\\
&
2)\lambda_2=2时\quad \dots
\end {align}
$$

### ⌚ 19:40 完整例题求特征值和特征向量

* 列出`|λE - A|`，检查10秒
  * 通过`|λE - A| = 0`或`|A - λE| = 0`求出λ
  * 一般利用按行展开或提公因子的技巧直接得到一个根，然后计算剩下的根
  3. 代入λ，得到矩阵`λE - A`
  4. 化为行简化阶梯型
  5. 写出同解方程组
  6. 对自由未知量取`One-Hot(即[1,0,0],[0,1,0],[0,0,1])`，得到基础解系
  7. 引入c写出通解，所有==c不同时为0==

### ⌚ 43:12 N阶三角形矩阵的特征值

* N阶三角形矩阵的特征值是主对角线上的元素

$$
\begin {align}
A=
\begin {bmatrix}
a_{11} & a_{12} & \dots & a_{1n}\\
& a_{22} & \dots & a_{2n}\\
 & & \dots & \dots\\
  & & & a_{nn}
\end {bmatrix}
\quad
|\lambda E-A|&=
\begin {bmatrix}
\lambda-a_{11} & -a_{12} & \dots & -a_{1n}\\
& \lambda-a_{22} & \dots & -a_{2n}\\
 & & \dots & \dots\\
  & & & \lambda-a_{nn}
\end {bmatrix}
\\
&
=(\lambda-a_{11})(\lambda-a_{22})\dots(\lambda-a_{nn})
\\
&\lambda_1=a_{11}\quad \lambda_2=a_{22} \quad \lambda_n=a_{nn}

\end {align}
$$

## ☄ P34 特征值与特征向量的性质

### ⌚ 00:00 基本性质

* ⭐️⭐️A和A^T有相同的特征值，特征向量可能不同

$$
|\lambda E-A^T|=|\lambda E^T-A^T|=|(\lambda E-A)^T|=|\lambda E-A|
$$

* 若矩阵A的每行元素绝对值之和小于1，且每列元素绝对值之和也小于1，则所有特征值的模小于1

$$
①\sum|a_{ij}|<1\quad i=1,\dots,n\quad ②\sum|a_{ij}|<1\quad j=1,\dots,n \quad |\lambda_k|<1
$$

* ⭐️⭐️⭐️韦达定理
  * 特征值之和（称为矩阵的迹`tra(A)`）等于对角线元素之和
  * 特征值之积等于行列式的值

[回到 相似矩阵的性质](#⌚ 07:58 相似矩阵的性质)
$$
\begin {align}
&
n个特征值\lambda_1,\lambda_2,\dots,\lambda_n \quad (1)\sum_{i=1}^n\lambda_i=\sum_{i=1}^na_{ii}\quad (2)\lambda_1\lambda_2\dots\lambda_n=|A|
\\
&
引例：
\\
&
1)x_3+bx_2+cx+d\,\,\,的根是\,1,2,3\,\,\,  则原式=(x-1)(x-2)(x-3)
\\
&
2)(x+c_1)(x+c_2)(x+c_3)\dots(x+c_n)=x^n+(c_1+c_2+\dots+c_n)+\dots+c_1c_2\dots c_n\quad(常数项可令x=0得到)
\\
&
证：
|\lambda E-A|=
\begin {bmatrix}
\lambda-a_{11} & -a_{12} & \dots & -a_{1n}\\
-a_{21} & \lambda-a_{22} & \dots & -a_{2n}\\
\dots & \dots & \dots & \dots\\
 -a_{n1} & -a_{n2} & \dots & \lambda-a_{nn}
\end {bmatrix}
=\textbf{\{}(\lambda-a_{11})(\lambda-a_{22})\dots(\lambda-a_{nn})\textbf{\}} \quad +\dots+\dots\\
&=\lambda^n-(a_{11}+\dots+a_{nn})\lambda^{n-1}+\dots+(-1)^n|A| \quad \textbf ① \qquad 其中(-a)
^n|A|常数项是\,|\lambda E-A|\,令\lambda=0得到
\\
\\
&
又|\lambda E-A|=0\,\,的根(特征值)是\,\,\lambda_1\dots\lambda_n
\\
&
则|\lambda E-A|=(\lambda-\lambda_1)(\lambda-\lambda_2)\dots(\lambda-\lambda_n)
=\lambda^n-(\lambda_1+\dots+\lambda_n)\lambda^{n-1}+\dots+(-1)^n\lambda_1\lambda_2\dots\lambda_3 \quad \textbf ②
\\
&
\begin {split}
|\lambda E-A|&=\lambda^n-(a_{11}+\dots+a_{nn})\lambda^{n-1}+\dots+(-1)^n|A| \quad \textbf ①
\\
&=\lambda^n-(\lambda_1+\dots+\lambda_n)\lambda^{n-1}+\dots+(-1)^n\lambda_1\lambda_2\dots\lambda_3 \quad \textbf②
\end {split}
\\
&
\begin {split}
即:\,\,&(1)\sum_{i=1}^n\lambda_i=\lambda_1+\dots+\lambda_n=a_{11}+\dots+a_{nn}=\sum_{i=1}^na_{ii}
\\
&(2)\lambda_1\lambda_2\dots\lambda_n=|A|
\end {split}
\end {align}
$$

* A可逆 <=> `|A| ≠ 0` <=> A所有特征根不等于0 <=> A满秩 <=> 行/列向量线性无关 <=> `Ax = 0`只有零解
* 互不相同的特征值`λ1,λ2...λm`==对应的==特征向量`α1,α2...αm`线性无关

$$
\begin {align}
&
\lambda1,\lambda_2\dots\lambda_m对应的
\\
&
\alpha_1,\alpha_2\dots\alpha_m线性无关
\\
&证(归纳法):
\\
&
m=1时 \quad \alpha_1 \ne0 \quad 线性无关(单个非零向量线性无关)
\\
&
假设对于s-1成立\quad \alpha_1\dots\alpha_{s-1}成立
\\
&
\begin {split}
对s\quad 如果线性无关，则设k_1\alpha_1+k_2\alpha_2+\dots+k_s\alpha_s&=0 \quad \textbf ①
\\
\stackrel{左乘A}{\longrightarrow}k_1A\alpha_1+k_2A\alpha_2+\dots+k_sA\alpha_s&=0
\\
\stackrel{A\alpha=\lambda\alpha}{\longrightarrow}k_1\lambda_1\alpha_1+k_2\lambda_2\alpha_2+\dots+k_s\lambda_s\alpha_s&=0 \quad \textbf ②
\\
\stackrel{\textbf ①左乘\lambda_s}{\longrightarrow}k_1\lambda_s\alpha_1+k_2\lambda_s\alpha_2+\dots+k_s\lambda_s\alpha_s&=0 \quad \textbf ③
\\
\stackrel{\textbf ② - \textbf③}{\longrightarrow}k_1(\lambda_a-\lambda_s)\alpha_1+\dots+k_{s-1}(\lambda_{s-1}-\lambda_s)\alpha_{s-1}&=0
\end {split}
\\
&
又s-1个线性无关，则k_1(\lambda_a-\lambda_s)=0\quad \dots \quad k_{s-1}(\lambda_{s-1}-\lambda_s)=0
\\
&
又\lambda_a\dots\lambda_s互不相同，所以\lambda_a-\lambda_s\ne0，则k_1\dots k_s=0
\\
&
则\textbf ①\to k_s\alpha_s=0 \quad 又\alpha_s为特征向量 \ne 0 \Rightarrow k_s=0\qquad 即k_1\dots k_s=0，所以线性无关
\end {align}
$$

* 互不相同的特征值对应的所有线性无关的特征向量线性无关

$$
\begin {align}
&\lambda_1=1对应的特征向量\alpha_1,\alpha_2线性无关\\
&\lambda_2=3对应的特征向量\alpha_3线性无关\\
&\lambda_3=5对应的特征向量\alpha_4,\alpha_5线性无关\\
&那么\alpha_1,\alpha_2,\alpha_3,\alpha_4,\alpha_5间线性无关
\end {align}
$$

* k重特征根对应的线性无关的特征向量的个数 ≤ k
  * 若λ是A的单根，那么λ对应的线性无关的特征向量只有一个
  * n阶矩阵A所有线性无关的特征向量的个数最多n个

### ⌚ 47:49 其他性质

* 若`λ`是`A`的特征值
  * `kλ`是`kA`的特征值
  
  * `λ^k`是`A^k`的特征值
  
    * $$
      \begin {align}
      &2是A的特征值，求A^5+6A^2+A+3E的特征值
      \\
      &2^5是A^5的特征值\Rightarrow A^5\alpha=2^5\alpha\\
      &2^2是A^2的特征值\Rightarrow A^2\alpha=2^2\alpha\to 6A^2\alpha=6\times2^2\alpha\\
      &2^1是A^1的特征值\Rightarrow A\alpha=2\alpha\\
      &2^0是A^0的特征值\Rightarrow E\alpha=\alpha \to 3E\alpha=3\alpha\\
      &左右全加起来：(A^5+6A^2+A+3E)\alpha=(2^5+6\times2^2+2+3)\alpha\\
      &----------------------------\\
      &做题的时候直接把A替换成A的特征值，即A\to 2,其中E替换成1\\
      &即把(A^5+6A^2+A+3E)中的A替换为2\to 2^5+6\times2^2+2+3
      \end {align}
      $$
  
  * [哈密顿一凯莱定理](https://baike.baidu.com/item/%E5%93%88%E5%AF%86%E9%A1%BF%E4%B8%80%E5%87%AF%E8%8E%B1%E5%AE%9A%E7%90%86)：`f(A)`的特征值为`f(λ)`，此处f代表多项式函数
  
  * `1/λ`是`A^-1`的特征值
  
  * `|A|/λ`是`A^*`的特征值
  
    * $$
      \begin {align}
      
      &
      \begin {split}
      A\alpha=\lambda\alpha\to \alpha=\lambda A^{-1}\alpha\to A^{-1}\alpha&=\frac {1} {\lambda}\alpha\\
      &\downarrow\\
      A^{-1}=\frac {1} {|A|}A^*\rightarrow |A|\frac {1} {|A|}A^*\alpha&=|A|\frac {1} {\lambda}\alpha\to A^*\alpha=\frac {|A|} {\lambda}\alpha
      \end {split}
      
      
      \end {align}
      $$

$$
\begin {align}
&5)A是四阶方阵，|3E+A|=0\quad AA^T=2E\quad|A|<0\quad求A^*的一个特征值\\
&解:由于|\lambda E-A|=0\Rightarrow|-(-3E-A)|=(-1)^4|-3E-A|=0\quad A的特征值是-3\\
&又A^*的特征值是\frac {|A|} {\lambda}\quad 则|A||A^*|=2^4\Rightarrow|A|^2=16，又|A|<0，则|A|=-4\\
&A^*=\frac {|A|} {\lambda}=\frac {-4} {-3}
\end {align}
$$

## ☄ P36 相似矩阵和矩阵可对角化的条件

### ⌚ 00:00 相似矩阵

* 若A、B为n阶方阵，存在n阶可逆矩阵P，使得`P^-1 AP = B`，则A与B相似，即`A ~ B`
* `A ~ A`
* `A ~ B <=> B ~ A`
* `A ~ B, B ~ C => A ~ C`

[回到 正交相似](#⌚ 28:48 正交相似)

### ⌚ 07:58 相似矩阵的性质

* 若 A \~ B，则：
  * A、B有相同的特征值
  * `|A| = |B|`
  * `tra(A) = tra(B)`
  * [参考 韦达定理](#⌚ 00:00 基本性质)

$$
\begin {align}
|\lambda E-A| \qquad \quad\,\,\,&p^{-1}AP=B\\
|\lambda E-B| \quad |\lambda E-&p^{-1}AP|=|\lambda P^{-1}EP-P^{-1}AP|=|P^{-1}||\lambda E-A||P|=|\lambda E-A|
\end {align}
$$

* 有相同特征值未必相似
* 若 A \~ B，则 ，A B同时可逆或同时不可逆，若`A可逆 <=> B可逆`，`A^-1 ~ B^-1`
* 若 A \~ B，则 `A^m ~ B^m`
* 若 A \~ B，则 `r(A) = r(B)`

$$
\begin {align}
&1)\,\,A\sim B\quad
p^{-1}AP=B\stackrel{取逆}{\longrightarrow}B^{-1}=(P^{-1}AP)^{-1}=P^{-1}A^{-1}P \Rightarrow A^{-1}\sim B^{-1}
\\
&2)A\sim B\qquad
P^{-1}AP=B\stackrel{取m次方}{\longrightarrow}B^m=P^{-1}APP^{-1}AP\dots= P^{-1}A^mP\Rightarrow A^m\sim B^m
\end {align}
$$

### ⌚ 22:06 与对角形矩阵相似（对角化）的条件

* A相似于[对角形](#⌚ 05:27 对角形矩阵)`Λ` <=> A有n个线性无关的特征向量
  * ⭐若P为特征向量的列组合`(α1, α2, α3)`，则`P^-1AP = Λ = diag(λ1, λ2, λ3) => A = PΛP^-1`
* 若A有n个互异的特征值，则`A ~ Λ`
* `A ~ Λ `<=> ==对每个ri重特征根有ri个解==（即ri个自由变量）
* [本知识点相对难理解，建议看视频](https://www.bilibili.com/video/BV1aW411Q7x1?p=36)

<img src="https://oss.pyhdxy.com/img/2022/02/07/15:18:51-image-20220207151850469.png" alt="image-20220207151850469" style="zoom: 50%;" />

### ⌚ 61:47 利用相似矩阵简单求矩阵的高次幂

<img src="https://oss.pyhdxy.com/img/2022/02/07/15:34:08-image-20220207153407188.png" alt="image-20220207153407188" style="zoom:50%;" />

## ☄ P37 实对称矩阵的对角化（一）

### ⌚ 00:00 实对称矩阵的对角化

* 所有实对称矩阵都能对角化

### ⌚ 02:00 内积

* 内积：两个向量对应相乘再相加得到的数

$$
\begin {align}
&
\alpha=
\begin {pmatrix}
1\\
2\\
3
\end {pmatrix}
\quad
\beta=
\begin {pmatrix}
0\\
0\\
8
\end {pmatrix}
\quad
则(\alpha,\beta)=1\times0+2\times0+3\times8=24
\\
&
\begin {split}
\alpha=
\begin {pmatrix}
a_1\\
a_2\\
\vdots\\
a_n
\end {pmatrix}
\quad
\beta=
\begin {pmatrix}
b_1\\
b_2\\
\vdots\\
b_n
\end {pmatrix}
\quad
(\alpha,\beta)&=a_1b_1+a_2b_2+\dots+a_nb_n
\\
&=\alpha^T\beta=\alpha\beta^T\qquad 最终是一个行向量\times列向量
\\
&\qquad\downarrow \qquad\,\,\downarrow 
\\
\alpha,\beta分别为
&
\,\,
\begin {split}
\quad列列\,\quad行行
\end {split}
\end {split}
\end {align}
$$

[回到 正交矩阵](#⌚ 00:00 正交矩阵)

* α和α的内积`(α, α) ≥ 0`
  * `(α, α) = 0 <=> α = 0`
* `(α, β) = (β, α)`
* `(kα, β) = k(α, β) = (α, kβ)`
  * `(kα, kβ) = k^2 (α, β)`
* `(α + β, γ) = (α, γ) + (β, γ)`

### ⌚ 21:09 向量的长度/范数/模

* 长度/范数/模：`||α|| = √(α, α)`
  * `(α, α) = ||α||^2`

* 单位向量：模为1
* 单位化/标准化: `α/||α||`

## ☄ P38 实对称矩阵的对角化（二）

### ⌚ 00:00 模的性质

* `||α|| ≥ 0，||α|| = 0 <=> α = 0`
* `||kα|| = |k|·||α||`

### ⌚ 04:16 柯西-施瓦茨不等式

* `|(α, β)| ≤ ||α||·||β||`

  * $$
        |a_1b_1+a_2b_2+\dots+a_nb_n \le \sqrt {a_1^2+a_2^2+\dots+a_n^2}+\sqrt {b_1^2+b_2^2+\dots+b_n^2}
    $$


### ⌚ 08:13 三角不等式

* `||α + β|| ≤ ||α|| + ||β||`

### ⌚ 09:55 正交/垂直

* `(α, β) = 0, α ⊥ β`

* `(0, α) = 0`

* 正交向量组：组中向量两两正交，==不含零向量==

* 标准正交向量组：是正交向量组，组内都是单位向量

* 若`α1,α2,...,αs`是正交向量组，那么`α1,α2,...,αs`线性无关

  * $$
    \begin {align}
    &注:两个向量不成倍数就线性无关\\
    &设\,\,k_1\alpha_1+k_2\alpha_2+\dots+k_n\alpha_n=0 \qquad ①\\
    &①与k_1做内积\,\,(\alpha_1,k_1\alpha_1+k_2\alpha_2+\dots+k_n\alpha_n)=(\alpha_1,0)\\
    &k_1(\alpha_1,\alpha_1)+k_2(\alpha_1,\alpha_2)+\dots+k_n(\alpha_1,\alpha_n)=0\\
    &\Rightarrow k_1(\alpha_1,\alpha_1)=0\Rightarrow k_1=0\\
    &①分别与k_2,k_3\dots做内积\Rightarrow k_2,k_3\dots=0\\
    &则\,\, \alpha_1\dots\alpha_n\,\,线性无关
    \end {align}
    $$


### ⌚ 25:10 施密特正交化

- 给一组线性无关的向量组`α1,α2,...,αs`，求与之正交且等价的`β1,β2,...,βs`

  ![施密特正交化](https://oss.pyhdxy.com/img/2022/02/02/23:57:54-施密特正交化.png)

* 施密特正交化（Schmidt orthogonalization）是求欧氏空间正交基的一种方法。从欧氏空间任意线性无关的向量组α1，α2，……，αm出发，求得正交向量组β1，β2，……，βm，使由α1，α2，……，αm与向量组β1，β2，……，βm等价，再将正交向量组中每个向量经过单位化，就得到一个标准正交向量组，这种方法称为施密特正交化。（来自[百度百科](https://baike.baidu.com/item/%E6%96%BD%E5%AF%86%E7%89%B9%E6%AD%A3%E4%BA%A4%E5%8C%96/756386?fr=aladdin)）

## ☄ P39 实对称矩阵的对角化（三）

### ⌚ 00:00 正交矩阵

* 正交矩阵A满足：A是n阶方阵，`AA^T = E`

* 若A是正交矩阵：
  * `|A| = ±1`
  
  * `A^-1 = A^T，且A^-1和A^T均正交`
  
  * $$
    \begin {align}
    & 由逆矩阵的定义：AB=E \quad 则A^{-1}=B \Rightarrow
    A^TA=E \quad A^{-1}=A^T\\
    & \begin {split}
    A^{-1}和A^T均正交：
    & (A^{-1})^TA^{-1}=(A^{-1})^TA^T=(AA^{-1})^T=E\\
    & (AT)^TAT=AA^T=AA^{-1}=E
    \end {split}
    \end {align}
    $$
  
* 若A、B都是正交矩阵，AB也正交

  * $$
    (AB)^TAB=B^TA^TAB=E
    $$

* 若A正交，α、β为n维列向量，则`(Aα, Aβ) = (α, β)`

  * $$
    (A\alpha,A\beta)=(A\alpha)^TA\beta=\alpha^TA^TA\beta=\alpha^T\beta=(\alpha,\beta)
    $$

  - [参考 内积最终可化为什么](#⌚ 02:00 内积)

* A正交 <=> A的列(行)向量组是标准正交向量组

$$
\begin {align}
& 证:设A=[\alpha_1,\alpha_2,\dots,\alpha_n]\\
& A^TA=[\alpha_1,\alpha_2,\dots,\alpha_n]^T[\alpha_1,\alpha_2,\dots,\alpha_n]=
\begin {bmatrix}
\alpha_1^T\\
\alpha_2^T\\
\vdots\\
\alpha_n^T
\end {bmatrix}
\begin {bmatrix}
\alpha_1 & \alpha_2 & \dots & \alpha_n
\end {bmatrix}
\\&=
\begin {bmatrix}
\alpha_1^T\alpha_1 & \alpha_1^T\alpha_2 & \dots & \alpha_1^T\alpha_n\\
&\ddots\\
&&\ddots\\
\alpha_n^T\alpha_1 & \alpha_n^T\alpha_2 & \dots & \alpha_n^T\alpha_n
\end {bmatrix}
=
\begin {bmatrix}
(\alpha_1,\alpha_1) & \dots & (\alpha_1,\alpha_n)\\
& \ddots &\\
(\alpha_n,\alpha_1) & \dots & (\alpha_n,\alpha_n)
\end {bmatrix}
=
\begin {bmatrix}
1 &  & \\
  & \ddots &\\
  &  & 1
\end {bmatrix}
\\
& \Rightarrow
\begin {cases}
(\alpha_i,\alpha_i)=||\alpha_i||^2=1\\
(\alpha_i,\alpha_j)=0
\end {cases}
\quad\Rightarrow 标准正交
\end {align}
$$

### ⌚ 21:38 实对称矩阵的对角化

* 实对称矩阵A的不同特征值对应的特征向量一定正交

$$
\begin {align}
& A^T=A \qquad \lambda_1,\lambda_2\,\,\, (\lambda_1\ne\lambda_2)\\
& A\alpha_1=\lambda_1\alpha_1 \quad A\alpha_2=\lambda_2\alpha_2\\
& (A\alpha_1,\alpha_2)=(\lambda_1\alpha_1,\alpha_2)=\lambda_1(\alpha_1,\alpha_2)\\
& \qquad ||\\
& (A\alpha_1)^T\alpha_2=\alpha_1^TA^T\alpha_2=\alpha_1^TA\alpha_2=\lambda_2\alpha_1^T\alpha_2=\alpha_2(\alpha_1,\alpha_2)\\
& \Rightarrow (\lambda_1-\lambda_2)(\alpha_1,\alpha_2)=0 \Rightarrow (\alpha_1,\alpha_2)=0
\end {align}
$$

### ⌚ 28:48 正交相似

* 若A、B是同阶方阵，存在正交矩阵P，使得`P^-1AP = B`，则A与B正交[相似](#⌚ 00:00 相似矩阵)
  * 正交相似一定相似

### ⌚ 31:24 定理

* 若A实对称，一定存在正交矩阵Q，使得`Q^-1AQ = Λ = diag(λ1, λ2, ..., λn)`
  * n阶实对称矩阵A一定有n个线性无关的特征向量
  * 设A是n阶实对称矩阵，λi是它的一个ri重特征根，那么A对应于λi的特征向量一定有ri个

### ⌚ 32:34 汇总

* 给定实对称矩阵A，求正交矩阵Q，使得`Q^-1AQ = Λ`

* 对于普通矩阵：
  * 如有n个无关的特征向量，可对角化`P^-1 AP = Λ = diag(λ1, λ2, ..., λn)`
  * 若无，则不能对角化
  
* 实对称矩阵一定能对角化：
  * 求特征值
  
  * 求特征向量
  
  * 特征向量正交化、单位化
  
  * 特征向量做成列构成Q
  
  * 特征值与特征向量顺序对应
  
    * 第三步-正交化技巧：因为实对称的不同特征值的特征向量正交，因此仅需要正交化所有重根的特征向量
  
    * $$
      \begin {align}
      & A为3阶实对称矩阵\\
      & 1)\,\,\lambda_1=2\quad\lambda_2=5\quad\lambda_3=-1\qquad三个根都是单根\\
      & \quad\,\,\downarrow \qquad\quad\,\,\downarrow \qquad\quad\,\,\downarrow\\
      & \quad\,\,\alpha_1 \quad\quad\,\,\,\alpha_2 \qquad\quad\alpha_3 \qquad \alpha_1,\alpha_2,\alpha_3\,\,已正交,直接单位化,\eta_1=\frac {1} {||\alpha_1||}\dots\\
      & Q=(\eta_1,\eta_2,\eta_3)\quad Q^{-1}AQ=\Lambda=
      \begin {bmatrix}
      \lambda_1 & & \\
       & \lambda_2 & \\
       & & \lambda_3
      \end {bmatrix}\\
      & 2)\,\,\lambda_1=1\,(单根) \quad \lambda_2=\lambda_3=10\,(二重)\\
      & \quad\downarrow\qquad\qquad\qquad\quad\,\,\downarrow\\
      & \quad\alpha_1 \qquad\qquad\qquad\alpha_2,\alpha_3 \quad (注:若相似于对角线矩阵，则重数=特征向量数，否则重数\ge特征向量数)\\
      & 其中\alpha_1=\beta_1 \quad 只把\alpha_2,\alpha_3做施密特正交化得到\beta_2,\beta_3,在单位化\dots\\
      & 3) \,\,\lambda_1=\lambda_2=\lambda_3\,\,(三重)\\
      & \to \alpha_1,\alpha_2,\alpha_3做正交化，单位化
      \end {align}
      $$
  
  
    <img src="https://oss.pyhdxy.com/img/2022/02/09/17:42:13-image-20220209174212529.png" alt="image-20220209174212529" style="zoom: 50%;" />

[回到 正交替换](#⌚ 31:06 正交替换)

## ☄ P40 二次型定义

### ⌚ 00:00 判断二次型

* 所有项都是二次（包括平方项和交叉项）

  * $$
    x^2+xy+y^2\quad xy为交叉项\qquad x_1^2+2x_1x_2+x_2^2+x_3^2-x_1x_3 \qquad \qquad x_1^2-x_2+3不是二次型
    $$


### ⌚ 03:08 n元二次型

* 包含n个变量的二次型

  * $$
    f(x_1,x_2,\dots,x_n)=二次型
    $$


### ⌚ 04:09 二次型的矩阵表达

* 平方项系数直接做成主对角线元素
  * 交叉项的系数除以2放到俩个对称的相应位置上
  
  * `X^T AX`，A的秩叫二次型的秩
  
  * $$
    \begin {align}
    & x_1^2+2x_1x_2+x_2^2-x_2x_3+2x_3^2-2x_1x_3\\
    & =[x_1,x_2,x_3]
    \begin {bmatrix}
    1 & 1 & -1\\
    1 & 1 & -\frac {1} {2}\\
    -1 & -\frac {1} {2} & 2
    \end {bmatrix}
    \begin {bmatrix}
    x_1\\
    x_2\\
    x_3
    \end {bmatrix}\\
    & =X^TAX
    \end {align}
    $$
  
* 二次型的矩阵一定对称

$$
如果非对称:
[x_1,x_2,x_3]
\begin {bmatrix}
1 & 1 & 2\\
1 & 1 & 1\\
3 & 1 & 2
\end {bmatrix}
\begin {bmatrix}
x_1\\
x_2\\
x_3
\end {bmatrix}
=x_1^2+x_2^2+x_3^2+2x_1x_2+5x_1x_3+2x_2x_3
$$

### ⌚ 21:30 标准型

* 只有平方项

### ⌚ 24:40 线性替换化为标准型

* `f(X) = X^T AX`，引入**`X = CY`**(C是一个矩阵，Y是另一个变量名)，则`f(X) = Y^T(C^T AC)Y`使`(C^T AC)`化为对角型

* $$
  \begin {align}
  & X^TAX\\
  & 第一次替换:\\
  & X=C_1Y \to Y^T(C1^TAC1)Y\\
  & 第二次替换:\\
  & Y=C_2Z \to Z^T(C_1C_2)^TA(C_1C_2)Z\\
  & 两次替换可以合并:\\
  & \begin {cases}X=C_1Y\\Y=C_2Z\end {cases}\to X=C_1C_2Z
  \end {align}
  $$

### ⌚ 35:38 合同

* A、B是两个n阶方阵，若存在可逆矩阵C，使得`C^T AC = B`，则A与B合同

* A与自身合同

* A合同于B <=> B合同于A

  * $$
    \begin {align}
    C^TAC=B \stackrel{左乘(C^T)^{-1},右乘C^{-1}}{\longrightarrow}(C^T)^{-1}BC^{-1}=A\to (C^{-1})^TB(C^{-1})=A
    \end {align}
    $$

* A合同于B，B合同于C => A合同于C

  * $$
    \begin {align}
    \begin {split}
    P_1^TAP_1=B\\
    P_2^TBP_2=C
    \end {split}
    \quad \stackrel{上式代入下式}{\longrightarrow}
    P_2^TP_1^TAP_1P_2=C\to (P_1P_2)^TA(P_1P_2)=C
    \end {align}
    $$

* A、B合同:
  * `r(A) = r(B)`  证：左乘或右乘一个可逆矩阵，秩不变

  * 同时对称：`A^T = A` <=> `B^T = B`

  * 若A、B可逆，则A^-1^与B^-1^合同

    * $$
      \begin {align}
      C^TAC=B\qquad &B^{-1}=(C^TAC)^{-1}=C^{-1}A^{-1}(C^T)^{-1}\\
      &=((C^{-1})^T)^TA^{-1}(C^{-1})^T
      \end {align}
      $$

  * A^T^与B^T^合同

### ⭐⭐⭐⌚ 49:00 矩阵间关系总结

* 正交的性质：P^T^ = P^-1^
* 正交/相似/合同 一定等价

<img src="https://oss.pyhdxy.com/img/2022/02/02/23:58:41-矩阵关系总结.png" alt="矩阵关系总结" style="zoom:125%;" />

## ☄ P41 二次型化标准型（配方法）

### ⌚ 00:00 二次型化标准型的三种方法

* 配方法（同济版只有配方法）
* 初等变换法
* 正交替换法（同实对称矩阵的对角化）

### ⌚ 02:33 配方法

* 注意：
  * 先x1，再x2，x3，……
  * 利用y线性替换x，使得对y的方程满足标准型
  * 反向求==x关于y==的表达式

<img src="https://oss.pyhdxy.com/img/2022/02/09/21:17:56-image-20220209211755668.png" alt="image-20220209211755668" style="zoom:50%;" />

<img src="https://oss.pyhdxy.com/img/2022/02/09/21:21:12-image-20220209212111767.png" alt="image-20220209212111767" style="zoom:50%;" />

* 只有交叉项的题的解题技巧（技巧固定）

  * $$
    \begin {align}
    & 2x_1x_2-4x_1x_3+10x_2x_3\qquad (只有交叉项)\\
    & \begin {cases}
    x_1=y_1-y_2\\
    x_2=y_1+y_2 & 前两个x_1,x_2替换是固定的\\
    x_3=y_3 & 后面有多少个未知量就令x_i=y_i
    \end {cases}
    \quad \to
    2y_1^2-2y_2^2+6y_1y_3+14y_2y_3
    \end {align}
    $$

## ☄ P42 二次型化标准型（初等变换法和正交替换法）

### ⌚ 00:00 初等变换法

* 对A、E做同样的初等列变换
  * 只对A做相应的初等行变换（配套的）
  * A化成对角阵之时，E化成的就是C 

```
╭ A ╮ ▁▁▁对整个矩阵做列变换  ▁▁▁╲ ╭ Λ ╮
╰ E ╯ ▔▔▔只对A做相应的行变换 ▔▔▔╱ ╰ C ╯
```

* 每次做完一套列行变换，上矩阵会变成对称的

$$
\begin {align}
& f(x)=X^TAX\quad X=CY \qquad C^TAC=\Lambda\qquad ①C=?\qquad ②\Lambda=?\\
& C可逆\quad C=P_1P_2\dots P_s \,\,\,\to\,\,\, C=EP_1P_2\dots P_s\\
& ----------------------------\\
& \begin {split}
(P_1P_2\dots P_s)^TAP_1P_2\dots P_s&=\Lambda\\
EP_1P_2\dots P_s&=C
\end {split}
\end {align}
$$

### ⌚ 22:00 规范形

* 在标准型的基础上继续变换`Λ`，使得对角线变为`1, ..., 1, -1, ..., -1, 0, ..., 0`的形式（规范形）

$$
\begin {align}

\begin {bmatrix}
1\\
&\ddots\\
&&1\\
&&&-1\\
&&&&\ddots\\
&&&&&-1\\
&&&&&&0\\
&&&&&&&\ddots\\
&&&&&&&&0
\end {bmatrix}
\to
y_1^2+\dots+y_p^2-y_{p+1}^2\dots-y_r^2\\
r(A)=r
\end {align}
$$

* 惯性定理：任意一个二次型可以通过非退化的线性替换化为规范形
  * 其中1和-1的总数等于原来矩阵的秩，且个数由原矩阵决定
  * -1无法化成1
  * 正惯性指数：正项（1）的个数
  * 负惯性指数：负项（-1）的个数
  * 符号差 = 正惯性指数 - 负惯性指数
* 任意矩阵A都与规范形合同
* 合同 <=> 有相同的秩、正惯性指数、负惯性指数

### ⌚ 31:06 正交替换

* 二次型A必然为实对称矩阵
* 正交替换的方法，与[对角化](#⌚ 32:34 汇总)相同
  * 求特征值
  * 求特征向量，正交化、单位化
  * 特征向量做成列，构成C；特征值按对应顺序做成对角阵
* 计算量大，用的比较少







![0001](https://oss.pyhdxy.com/img/2022/02/09/20:53:17-0001.jpg)

![0002](https://oss.pyhdxy.com/img/2022/02/09/20:55:52-0001.jpg)
