# Miao-A-SongHao-Linear-Algebra-Notes
bilibili 宋浩老师 “惊叹号” 系列 [《线性代数》网课](https://www.bilibili.com/video/av29971113) 笔记及时间点目录

# 💡 前言
- 我发现吧，线代没记笔记真不行。浩浩学习，天天向上。数学网课强推[👍👍👍👍👍宋浩老师](https://space.bilibili.com/66607740)的视频，冲冲冲~~~
- 如有遗漏或错误欢迎推PR或发Issue~

# ⚗ 线性代数
## ☄ P1 二阶三阶行列式
### ⌚ 02:48 二阶行列式划线计算
- 行列式一定是方的
### ⌚ 15:00 三阶行列式划线计算
- 主对角线：╲
- 副对角线：╱
### ⌚ 22:29 N阶行列式预备知识
- 排列：1，2，……，n组成的一个有序数组叫n级排列，中间不能缺数
  - 如`3级排列：123，132，213，231，312，321`
- 逆序：大数排在小数前面
- 逆序数：逆序的总数
- 奇/偶排列：逆序数为奇/偶
- 标准排列：`123……N`
- 对换：交换排列中的两个数
  - 做一次对换，排列奇偶性改变
## ☄ P2 n阶行列式
### ⌚ 00:55 N阶行列式计算
- 按行展开：
  - 行标取标准排列
  - 列标取排列的所有可能，从不同行不同列取出n个元素相乘
  - 共有N!项
  - 每一项的符号由列标排列的奇偶性决定，偶正奇负
### ⌚ 20:50 下三角行列式
- 右上方三角形区域元素全部为0
- 下三角行列式 = 主对角线元素相乘
### ⌚ 23:14 上三角行列式
- 左下方三角形区域元素全部为0
- 上三角行列式 = 主对角线元素相乘
### ⌚ 24:40 对角线行列式
- 只有主对角线上有数
### ⌚ 25:30 副对角线行列式
- 副对角线行列式 = `(-1)^(n(n-1)/2) * 副对角线元素相乘`
### ⌚ 31:00 三角行列式总结
![](三角行列式.jpg)
### ⌚ 31:09 行列式三种定义
- 1.按行展开，符号由列标排列决定
- 2.按列展开，符号由行标排列决定
- 3.胡乱展开，符号由行标排列逆序数和列标排列逆序数之和决定 `(-1)^(N(i1,i2,……,iN)+N(j1,j2,……,jN)), i：行标，j：列标`
## ☄ P3 行列式的性质
- 行列式对行成立的性质对列也成立
### ⌚ 00:25 性质一 转置
- 转置：把行按列写
- 行列式转置后值不变
- 行列式转置的转置等于本身
### ⌚ 11:48 性质二 两行互换
- 行列式两行互换，值变号
### ⌚ 20:38 性质三 两行相同
- 行列式两行相同，等于0
### ⌚ 23:10 性质四 行公因子k
- 行列式某行都乘以k，等于用k乘以这个行列式。即行列式某一行有公因子k，可往外提一次
- 若行列式所有元素都有公因子k，k外提N次
### ⌚ 28:05 性质五 两行成比例
- 行列式两行成比例，则行列式值为0
- 某一行全为0，则行列式为0
### ⌚ 34:20 性质六 和分解
- 若行列式某一行元素都可以表示为两项和，则行列式等于两个行列式相加
  ```
  | 1+2 2+3 |   | 1 2 |   | 2 3 |
  | 3   3   | = | 3 3 | + | 3 3 |
  | 4   6   |   | 4 6 |   | 4 6 |
  ```
### ⌚ 43:36 性质七 行叠加
- 某一行乘以一个数加到另一行上去，行列式值不变
### ⌚ 51:12 行列式值计算通用法
- 将行列式化为上三角行列式，连乘对角线元素
  - 利用性质七将左下角元素从左到右从上到下消为0
## ☄ P4 行列式按行展开
### ⌚ 04:36 余子式
- 在行列式中选中某个元素，去掉所在行列，剩余的元素构成的行列式叫这个元素的余子式`M_ij，M代表余子式，i代表选中元素的行标，j列标，ij从1开始`
### ⌚ 07:42 代数余子式
- 在余子式前面加上符号`(-1)^(i+j)`
### ⌚ 09:38 降阶：行列式按某一行/列展开
- 行列式的值 = 某一行所有元素乘以自己的代数余子式的积之和，列同理
### ⌚ 16:50 异乘变零定理
- 某行元素与另一行元素的代数余子式乘积之和为零
### ⌚ 27:17 拉普拉斯定理
- k阶子式：任取k行k列，交叉处构成的行列式为k阶子式
- k阶子式的余子式：除去选中行列，其余行列形成的子式为k阶子式的余子式
- k阶子式的代数余子式：多个符号`(-1)^所有行标与列标之和`
### ⌚ 30:17 拉普拉斯展开定理
- 取定k行，由k行元素组成的所有k阶子式与其代数余子式乘积之和 = 行列式值
### ⌚ 38:30 同阶行列式相乘
- 同阶行列式相乘的值 = 两个行列式做矩阵乘法后得到的行列式的值
## ☄ P5 行列式的计算（一）
### ⌚ 14:33 纯数字行列式计算
- 将行列式化为上三角行列式，连乘对角线元素
### ⌚ 21:50 已知行列式求余子式之和
- 构造新行列式
### ⌚ 30:06 对角线为x，其余为a的行列式计算技巧
## ☄ P6 行列式的计算（二）
### ⌚ 00:00 行列式计算基础思路
- 1.化成上三角
- 2.把某行/列尽可能多得化成0，然后展开
###  ⌚ 01:05 三叉形行列式
- 加边法：在顶上加一行1，左边多出的一列（除第一行）为0，行列式值不变
### ⌚ 17:42 范德蒙德行列式
![](范德蒙德行列式.png)
### ⌚ 40:42 反对称行列式
- `a_ij = -a_ji`
- 主对角线全为0
- 上下位置对应成相反数
- 奇数阶，行列式值 D = 0
### ⌚ 43:12 反对称行列式
- `a_ij = a_ji`
- 主对角线无要求
- 上下位置对应相等
## ☄ P7 克莱姆法则
### ⌚ 00:05 解方程组
- n个方程，n个未知量
- D ≠ 0
- x_j = D_j / D，D为方程组系数构成的行列式，D_j代表把方程组值用于替换D的第j列得到的行列式，x_j代表解

![](克莱姆法则.png)

### ⌚ 09:11 解齐次线性方程组
- n个方程，n个未知量
- 齐次：方程组值都为0，即无常数
- 齐次方程，至少有零解
- 若 D ≠ 0，只有零解；若 D = 0 <=> 有非零解

![](克莱姆法则_齐次.png)

## ☄ P8 矩阵概念
### ⌚ 22:20 矩阵和行列式比较
- 矩阵可以是不方的
- 零矩阵：元素都是0的矩阵为零矩阵（有形状）
- 负矩阵：A的负矩阵为`-A`，所有元素取相反数
- 方阵：行数 = 列数
- 单位阵`E`：对角线上为1，其余元素为0，一定为方阵
- 同型矩阵：形状相同
- 矩阵相等：同型且值对应相等
  - 零矩阵不一定相等
- 方阵的主对角线：╲，次对角线：╱，不是方阵则没有
## ☄ P9 矩阵运算（一）
### ⌚ 00:00 赠送自制知识卡片
- 谁有电子版啊，求分享
### ⌚ 02:50 矩阵加减法
- 只有同型矩阵才能相加减
- 对应元素相加减
### ⌚ 07:53 矩阵数乘运算
- 用k乘以矩阵，相当于把k乘以矩阵所有元素
  - 矩阵所有元素均有公因子，公因子外提一次（行列式是n次）
### ⌚ 13:58 矩阵乘法
- 前提：左矩阵列数 = 右矩阵行数
- 结果矩阵的行数 = 左矩阵行数，列数 = 右矩阵列数
- 结果矩阵第i行第j列的值 = 左矩阵第i行与右矩阵第j列对应元素乘积之和
- 宋氏七字：中间相等，取两头
- `AB 一般≠ BA` AB有意义，BA不一定有意义。若`AB = BA`，则称A，B可交换
- 左乘：在矩阵左边乘上一个矩阵，右乘同理
- `AB = 0 ≠> A=0 或 B=0`
- `AB = AC，A≠0 ≠> B=C`
- 与零矩阵左/右乘：零矩阵与任何矩阵相乘都为零矩阵
- 与单位阵左/右乘：`AE = A, EB=B`
- `(AB)C = A(BC)`，AB顺序不可变
- `(A + B)C = AC + BC`，AB顺序不可变
- `k(AB) = (kA)B = A(kB)`，AB顺序不可变
## ☄ P10 矩阵运算（二）
### ⌚ 00:00 矩阵幂运算
- `A^0 = E`
- `A^k1 · A^k2 = A^(k1+k2)`
- `(A^k1)^K2 = A^k1k2`
- `(AB)^k 一般≠ A^k · B^k`
  - `(AB)^2 = ABAB ≠ A^2 · B^2 = AABB`
- `(A + B)^2 = A^2 + BA + AB + B^2 ≠ A^2 + 2AB + B^2`
  - `(A - B)^2 ≠ A^2 - 2AB + B^2`
- `(A + E)^2 = A^2 + 2AE + E^2`
- A^k需满足A为方阵
