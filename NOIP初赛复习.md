# NOIP初赛复习
## 存储空间

 1byte=8bit
 1KB=1024byte
 | 类型 |  占用字节 |
 | ----- | :-----: |
 | int | 4 
 | bool |1
 | char  |1
 | long| 4
 | float |4
 | double | 8

--------------
| 类型| 符号位 | 指数位（标识小数点位置）| 尾数位（存储数据） 
|:-----:|:------:| :---:|:---:|
| float |1bit|8bit|23bit
| double |1bit| 11bit |52bit
 
## 树
**定义n：个节点和n-1条边构成的图**
### 二叉树
####    二叉树的性质
 - 第n层上至多有 $2^{n-1}$ 个元素
 - 深度为h的二叉树最多有$2^h-1$个元素
 - 满二叉树：深度为h，有$2^h-1$个元素
 - 完全二叉树：除了最后一层是一颗满二叉树
 对于完全二叉树中的每一个节点i，其左子为2i，右子为2i+1
  #### 二叉树的遍历

 - 前序遍历 根节点 左子树 右子树
 - 中序遍历 左子树 根节点 右子树
 - 后序遍历 左子树 右子树 根节点
 - 已知前序遍历，中序遍历，可求后序遍历。
   已知中序遍历，后序遍历，可求前序遍历。
 ### Huffman Tree
#### 定义:只有叶子节点有权值的、带权路径（=节点权值*到根节点距离）总和最小的二叉树
#### 构建方法
 -   重复以下的步骤：  
    -   按照权值对每一个节点排序：D-F-T-E-R-A
    -   选择权值最小的两个节点，此处为D和F生成新的节点，节点的权重为这两个节点的权重之和，为2
 -   直到只剩最后的根节点
## 卡特兰数
$h_0=1\quad h_1=1$

$$h_n=\sum_{i=1}^{n-1}h_i\times\ h_{n-i} =\frac{4n-2}{n+1}*h_{n-1}=\frac{C_{2n}^n}{n+1}$$
#### 应用

- 一个栈的进栈序列为1，2，3，…，n，有多少个不同的出栈序列?
-  给定节点，求可以形成的二叉树的数量。
-   多边形划分为三角形。
-   出栈次序问题。
-   括号化问题。

## 进制转换
#### 十进制与二进制转换
#### 二, 八, 十六进制转换
以二进制转八进制为例, 把二进制数每三位化为一组转化成八进制数即可
#### 十进制小数与二进制转换
对十进制小数乘2得到的整数部分和小数部分,整数部分既是相应的二进制数码,再用2乘小数部分(之前乘后得到新的小数部分),又得到整数和小数部分.  
如此不断重复,直到小数部分为0或达到精度要求为止.第一次所得到为最高位,最后一次得到为最低位
**0.8125的二进制**
0.8125*2=1.625 取整数部分是1
0.625*2=1.25 取整数部分是1
0.25*2=0.5 取整数部分是0
0.5*2=1.0 取整数部分是1
## NP/PNP/P 问题
P问题
可以找到一个能在多项式的时间里解决它的算法

NP问题
可以在多项式的时间里验证一个解的问题

NPC问题
- 是一个NP问题
- 所有的 NP 问题都可以约化到它。
## 互联网

 - ISP：因特网服务提供者
 - 比特流（BitTorrent）：文件的持有者将文件发送给其中一名用户，再由这名用户转发给其它用户，用户之间相互转发自己所拥有的文件部分，直到每个用户的下载都全部完成。
 - 中继器（RP repeater）：用于两个网络节点之间物理信号的双向转发工作
 - 调制解调器：调制解调器是一种计算机硬件，它能把计算机的数字信号翻译成可沿普通电话线传送的模拟信号，而这些模拟信号又可被线路另一端的另一个调制解调器接收，并译成计算机可懂的语言。这一简单过程完成了两台计算机间的通信。
 - 路由器：路由器工作在网络的网络层上，当数据包要在不同协议、不同体系结构的网络之间进行传输时，路由器不仅可以进行路由选择，还可以进行数据包的格式转换以适应这种传送。
 - 3G技术标准：
TD-SCDMA 中国移动
 WCDMA 	中国联通
CDMA2000 中国电信
## 前缀、中缀、后缀表达式
#### 前缀表达式
前缀表达式的运算符位于操作数之前。（从右往左读） 
例如前缀表达式“- × + 3 4 5 6”： 
(1) 从右至左扫描，将6、5、4、3压入堆栈； 
(2) 遇到+运算符，因此弹出3和4（3为栈顶元素，4为次顶元素，注意与后缀表达式做比较），计算出3+4的值，得7，再将7入栈； 
(3) 接下来是×运算符，因此弹出7和5，计算出7×5=35，将35入栈； 
(4) 最后是-运算符，计算出35-6的值，即29，由此得出最终结果。 
可以看出，用计算机计算前缀表达式的值是很容易的。
#### 中缀表达式
中缀表达式就是我们平常使用的表达式。
#### 后缀表达式
后缀表达式后缀表达式与前缀表达式类似，只是运算符位于操作数之后。（从左往右读） 
例如后缀表达式“3 4 + 5 × 6 -”： 
1. 从左至右扫描，将3和4压入堆栈； 
2. 遇到+运算符，因此弹出4和3（4为栈顶元素，3为次顶元素，注意与前缀表达式做比较），计算出3+4的值，得7，再将7入栈； 
3. 将5入栈； 
4. 接下来是×运算符，因此弹出5和7，计算出7×5=35，将35入栈； 
5. 将6入栈； 
6. 最后是-运算符，计算出35-6的值，即29，由此得出最终结果。
## 竞赛的历史

NOIP→1995
NOI→1984
IOI→1989
CTSC/APIO→2007

## 其他
 - 树和二分图一定可以黑白染色
 - 编译程序：全部编译后执行
 - 解释程序：写一句运行一句
 - C++，支持多继承、多态和部分动态绑定。
-  Java，支持单继承、多态和部分动态绑定。
- 汇编语言: 可以直接访问寄存器，内存单元，I/O接口
 - 三原色: 红绿蓝
 - 网络协议为什么有多层？为了简化网络设计的复杂性, 不是为了兼容老协议
 - BIOS（Basic Input/Output System），基本输入输出系统，全称是ROM－BIOS，是只读存储器基本输入/输出系统的简写，它实际是一组被固化到电脑中，为电脑提供最低级最直接的硬件控制的程序，BIOS设置程序储存在BIOS芯片中，只有在开机时才可以进行设置。
 - 32位的CPU的字长是32位，意为单位时间内可以处理的信息量，是影响电脑运行速度的重要因素。

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzc5Nzk3NTIxXX0=
-->