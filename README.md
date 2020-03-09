# Miao-A-SongHao-Linear-Algebra-Notes
宋浩老师“惊叹号”系列[《线性代数》网课](https://www.bilibili.com/video/av29971113)笔记及时间点目录

# 前言
- 我发现吧，线代没记笔记真不行。浩浩学习，天天向上。数学网课强推[👍👍👍👍👍宋浩老师](https://space.bilibili.com/66607740)的视频，冲冲冲~~~
- 🐣 如有遗漏或错误欢迎推PR或发Issue~

# 线性代数
## 💨P1 二阶三阶行列式
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
## P2 n阶行列式
### ⌚ 00:55 N阶行列式计算
- 按行展开：
  - 行标取标准排列
  - 列标取排列的所有可能，从不同行不同列取出n个元素相乘
  - 共有N!项
  - 每一项的符号由列标排列的奇偶性决定，偶正奇负
### ⌚ 20:50 下三角行列式
- 左下方三角形区域元素全部为0
- 下三角行列式 = 主对角线元素相乘
### ⌚ 23:14 上三角行列式
- 左上方三角形区域元素全部为0
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
## P3 行列式的性质
- 行列式对行成立的性质对列也成立
### ⌚ 00:25 转置
- 转置：把行按列写
- 行列式转置后值不变
- 行列式转置的转置等于本身
### ⌚ 11:48 两行互换
- 行列式两行互换，值变号
