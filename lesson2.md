https://www.youtube.com/watch?v=z8HKWUWS-lA

## 专业名词

theorem 定理

whole number 自然正整数0，1，2，3，4，5 ...... 999999999

rational number 有理数 （天，这个翻译真的难。rational是理性的意思，也可以是分数，但是小数点是有限位数的）

irrational number无理数 （ 圆周率，或者有无数小数点的数字叫无理数）

numerator 分子

denominator 分母

https://www.mathsisfun.com/definitions/numerator.html

simplified to lowest terms 数字无法找到公约数，意思是都没办法继续变小了，譬如，以下的英文解释说都是质数，实际上这里指的没有公约数了。

**A fraction** is said to written using lowest terms if its numerator and denominator are relatively prime , that is, they have no common factors other than 1 . (Some books use "simplest form" to mean the same thing.)

induction 归纳法

## 课程笔记内容

我们知道theorem其实就是公理一步步推理出来的，可以用作快速工作推理的工具，因此定理是非常必须的快捷方式。

那么如何证明一个定理呢？ 

这里提到了反证法

In a proof by contradiction, you assume the opposite of what you trying to prove, and you take steps for logical deductions forward until you arrived at a contradiction, you prove false equals true.

#### 证明定理案例1

## A proof that the square root of 2 is irrational

https://www.homeschoolmath.net/teaching/proof_square_root_2_irrational.php

Let's suppose √2 is a rational number. Then we can write it √2 = *a/b* where *a*, *b* are whole numbers, *b*not zero.

We additionally assume that this *a/b* is simplified to lowest terms, since that can obviously be done with any fraction. Notice that in order for *a/b* to be in simplest terms, both of *a* and *b* cannot be even. One or both must be odd. Otherwise, we could simplify *a/b* further.

From the equality √2 = *a/b* it follows that 2 = *a*2/*b*2,  or  *a*2 = 2 · *b*2.  So the square of *a* is an even number since it is two times something.

From this we know that *a* itself is also an even number. Why? Because it can't be odd; if *a* itself was odd, then *a* · *a* would be odd too. Odd number times odd number is always odd. Check it if you don't believe me!

Okay, if *a* itself is an even number, then *a* is 2 times some other whole number. In symbols, *a* = 2k where k is this other number. We don't need to know what k is; it won't matter. Soon comes the contradiction.

If we substitute *a* = 2k into the original equation 2 = *a*2/b2, this is what we get:

| 2    | =    | (2k)2/b2 |
| ---- | ---- | -------- |
| 2    | =    | 4k2/b2   |
| 2*b2 | =    | 4k2      |
| b2   | =    | 2k2      |

This means that *b*2 is even, from which follows again that *b* itself is even. And that is a contradiction!!!

WHY is that a contradiction? Because we started the whole process assuming that *a/b* was simplified to lowest terms, and now it turns out that *a* and *b* both would be even. We ended at a contradiction; thus our original assumption (that √2 is rational) is not correct. Therefore √2 cannot be rational.

老师娓娓道来，希腊人对于无理数的厌恶历史，以至于有人证明了等边为1的直角三角形，它的最长边是√2，是个无理数，以至于当局把数学当作神灵的同时，厌恶指出神灵错误的人，于是把那个人给杀了。

这就暗示了，在数学的道路上，历史会重复的，证明了别人错误的同时，有可能会触犯一些根本的领导层的看法，或者推翻了神圣的理论基础，甚至会为此丢掉生命。数学nerd真不容易呀。

#### 定理2 - 图片要看清

此节课形象的用一个ppt演示了，把一个长方形切为4小块，然后重新计算面积，居然比之前大了。我百思不得其解，最终意识到图片上的长宽标值与实际长度不符。

这也告诉我们要极其严谨，很多时候作图错了，后面步步都是错的。



#### induction axiom归纳法证明公理

**Mathematical induction** is a [mathematical proof](https://en.wikipedia.org/wiki/Mathematical_proof) technique. It is essentially used to prove that a statement *P*(*n*) holds for every [natural number](https://en.wikipedia.org/wiki/Natural_number) *n* = 0, 1, 2, 3, . . . ; that is, the overall statement is a sequence of infinitely many cases *P*(0), *P*(1), *P*(2), *P*(3), . . . . Informal metaphors help to explain this technique, such as falling dominoes or climbing a ladder:

说白了，你必须要证明 P(n)=>P(n+1), 因为你只要能推理下一个数值也是正确的公式，你就依次推理下去，解决了所有的问题，即可证明这个axiom的consistent and complete. 具体案例如下：

https://en.wikipedia.org/wiki/Mathematical_induction

归纳法会看起来很奇怪，先假定公式是正确的，然后计算第一个起点，如果正确，那么你只需要依次推理下一个值是正确的，就可以源源不断的，像链表一样抓住了所有值。

这类题目的通用解法就是：

Proof, by induction ， for all n in integer, n³-n always can be divided by 3.

So first n=0, and it's true. 0 can be divided by 3.

Next inductive step , n -> n+1 来证明公式依然有效

Examine:  (n+1)³ - (n+1) => n³+3n²+3n+1 - (n+1) =>  n³+3n²+2n 

此时，你会发现这个进入了死胡同，因为这个结果不像是3的倍数

如何办呢？此时注意，induction一定要利用上原条件，n³-n是3的倍数，要假定它是对的，利用起来。

  n³+3n²+2n => (n³-n) + (3n² + 3n) => 至此证明了全部都是3的倍数组成的。

因此从0是3的倍数，1的代入结果也是对的，我们可以归纳推理下去，以后所有的结果都是对的。

我想了一下，这么复杂的公式，我好像高中的确学过，真的忘得一干二净，因为从来都没有价值，只有做题的意义。所以somehow，每当有人说中国人数学学得比美国好，学得早，咱们孩子很少就能加减乘除超过美国孩子的时候，我内心还是会打个问号。真的学得早好吗？是不是超越了孩子能理解的阶段？是不是学习的意义还没有理解，就去灌输这个知识真的有效吗？well, I don't know, it's hard to argue, burdens on me, I would rather bury it in my mind.

#### 归纳证明case3

证明所有的马都是一个颜色

这个压根就没法用公式，因为n都不存在，这时候就需要抽象问题变成公式的能力

for a set of P(n) horses, they are all same color.

于是老师故意带大家入坑，假模假样的开始证明，依然分3步

1. P(1) , 这个集合一匹马，自然all same color
2. 假定这个理论是对的，我们来证明P(n+1)是同一个color，因为p1,p2...pn都是一个color，那么我们只是再加了一个n+1的case，自然也是same color
3. 最终得出结论，所有的马都是一个颜色

这个错误的利用归纳法，活灵活现的表现了学习的正反边界。

因为这个的base case，不应该是只有P(1), P(1)甚至无法推导出来P(2)，谈何直接利用公式直接assume是对的呢？

这个case告诉我们，归纳法使用要慎重，归纳要有规律可循，有连续性和衔接性。

我们的数学书上，经常讲一个定理，然后避重就轻的只讲正面的案例，不讲不该用，误错的案例，留给孩子家长自己摸索。我举个最近儿子学习的用大约摸数字，比大小的题目。

书上的案例：电影院有441个座位，一年级有221人，二年级有239人，请问座位够不够？

正常的解法，221估算成220，239估算成230，经过简单的相加得出450，于是答出，就算往小了估计，也不够，因此座位肯定不够。

这道题换个数字还可以这么考试：

电影院有500个座位，一年级有221人，二年级有239人，请问座位够不够？

正常的解法，221估算成230，239估算成240，经过简单的相加得出450，于是答出，就算往大了估计，也够，因此座位肯定够。

可是这样子的做题方式很傻，孩子并不清楚这一刻该往小估计，还是往大估计。

孩子可能往4舍5入的估算方向进行，譬如221估计成了220，239估计成了240。万一题目的座位是460个，这时候到底是够还是不够呢？

就算我们大人，也是往小，往大各自估算了一遍，最终才敢确定估算的方向，才能答题，也就是说，这样的设计题目，完全违背了这道题的初衷：估算让计算更省事，实际上，更费事了。

数学应该让人更省事，更高效。不知道我这么说，会不会被人讲夹带私货，但是我这是个人笔记，记录而已，不必细究。

##### 归纳证明case4

这里老师讲了一个mit的校园草坪设立捐赠排位的难题。推论是否能在2的n次方里，永远能L型用3个格子的纪念碑，而且放在中间。

https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2010/readings/MIT6_042JF10_chap03.pdf

题目详情见3.2.5章节。

结论是，如果你发现归纳法无法证明下去的时候，尝试把条件变宽松，变扩大，使得你的P(n)更加powerful，因此更容易证明P(n+1)。

















