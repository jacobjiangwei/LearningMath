## 专业术语名词

#### deductions  推理

Deduction is drawing a conclusion from something known or assumed. This is the type of reasoning we use in almost every step in a mathematical argument. 

#### proposition 命题，主张

A proposition is a mathematical statement such as "3 is greater than 4," "an infinite set exists," or "7 is prime."

#### axiom 公理
An axiom is a proposition that is assumed to be true. With sufficient information, mathematical logic can often categorize a proposition as true or false, although there are various exceptions (e.g., "This statement is false").

#### prime 质数
只有读了英语，你才知道当时的翻译多晦涩难懂。prime是主流，首要的意思，因此第一批数学家就翻译成了“本质的数字，质数”。如果没有人究其所以然，这个质数只能死记硬背这个概念。

#### conjecture 猜想

## 课程内容

Proof is a method to ascertain the truth, you name the methods.
Proof这是一套用来证明事实的方法论，你自己选择使用什么方法，例如观察observation，或者是老板的言论，老板永远是对的，或者是宗教的言论，或者各种各种言论，很难argue。甚至写代码的人，会说这个代码没有bug，如果有bug，你来证明给我看。proof很难捕捉，论证。

而数学的优点，就是它无视与神灵宗教言论，哪怕一个年轻的孩子，只要论证严谨，他都可以扳倒一个有名望的教授的错误结论。在数学的层面上，不存在泰山压顶，大家用一套语言工作。

因此math的论证是严谨的，mathimatically proof is a verification of proof by a chain of logical deductions from a set of claims. 数学要可验证，必须有逻辑缜密的推理。

##### proposition #1，x²+x+41永远是质数

|  x   | 结果  | 是否质数
|  ----  | ----  | ----  |
| 0 | 41 | 是
| 1 | 43 | 是
| 2 | 47 | 是
| 3 | 53 | 是
| 20 | 461 | 是
| 39 | 1601 | 是

这时候很多人都会认为是质数，铁定的了。实际上简单的归纳法是错误的，只尝试一丢丢答案是不足以证明这一定是对的，例如尝试到41，就错了。

##### proposition #2，任意的正整数a,b,c,d，都无法满足这个公式a⁴ + b⁴ + c⁴ = d⁴ 

直至很多年后有人发现
a = 95800
b = 217519
c = 414560
d = 422481

老师通过这个例子说明了，不要以为尝试几个可能，就以为是正确的proof了，这些都不足够。要有逻辑推理，不能只有穷举暴力解法。
他又通过这个例子，告诉我们，有时候有的答案，甚至要1000位的数字才能找到那个公式。因此加密学，会使用这些数学公式来设定密码，如果有心人打算暴力解开rsa的密码，那他要穷举很多年，因为公式决定了它有无数位后的某个数字才是答案。
我真希望当年的大学老师，有这么认真的讲一下数字的应用场景，勾起我们的兴趣。

##### proposition #3， four color map theorem四色定理

如果在平面上劃出一些邻接的有限区域，那么可以用四种颜色来给这些区域染色，使得每两个邻接区域染的颜色都不一样[2][3]；另一个通俗的说法是：每个无外飞地的地图都可以用不多於四种颜色来染色，而且不會有两个邻接的区域颜色相同。被称为邻接的两个区域是指它们有一段公共的边界，而不仅仅是一个公共的交点。例如右图左下角的圆形中，红色部分和绿色部分是邻接的区域，而黄色部分和红色部分则不是邻接区域。

1976年，数学家凱尼斯·阿佩爾和沃夫冈·哈肯借助电子计算机首次得到一个完全的证明，四色问题也终于成为四色定理。这是首个主要借助计算机证明的定理。这个证明一开始并不为许多数学家接受，因为不少人认为这个证明无法用人手直接验证。尽管随着计算机的普及，数学界对计算机辅助证明更能接受，但仍有数学家希望能够找到更简洁或不借助计算机的证明。

##### proposition #4，Goldbach's conjecture 

every even integer is sum of either prime or one is known as

哥德巴赫1742年在给欧拉的信中提出了以下猜想：任一大于2的整数都可写成三个质数之和 [1]  。但是哥德巴赫自己无法证明它，于是就写信请教赫赫有名的大数学家欧拉帮忙证明，但是一直到死，欧拉也无法证明。 [2]  因现今数学界已经不使用“1也是素数”这个约定，原初猜想的现代陈述为：任一大于5的整数都可写成三个质数之和。(n>5：当n为偶数，n=2+(n-2)，n-2也是偶数，可以分解为两个质数的和；当n为奇数，n=3+(n-3)，n-3也是偶数，可以分解为两个质数的和)欧拉在回信中也提出另一等价版本，即任一大于2的偶数都可写成两个质数之和。今日常见的猜想陈述为欧拉的版本。把命题"任一充分大的偶数都可以表示成为一个素因子个数不超过a个的数与另一个素因子不超过b个的数之和"记作"a+b"。1966年陈景润证明了"1+2"成立，即"任一充分大的偶数都可以表示成二个素数的和，或是一个素数和一个半素数的和"。
今日常见的猜想陈述为欧拉的版本，即任一大于2的偶数都可写成两个素数之和，亦称为“强哥德巴赫猜想”或“关于偶数的哥德巴赫猜想”。

老师循循道来了其他的2大猜想，多希望我们的老师可以畅所欲言的讲一下数学的历史，多么有趣呀
Bernard Riemann hypothesis
poincare conjecture 

## 逻辑学

#### conjunction 就是交集，也就是与的意思
#### disjunction 就是或的意思，either a is true or b is true.
https://www.math.uvic.ca/faculty/gmacgill/guide/Logic.pdf

最简单的判断，就是p 是 true 论证了q是true，那么推理 p->q就是true。如果推q是false，那么推理p->q就是false。

表格里最容易绕人脑子的是这句：
如果p是false，那么推理任何结果，都是true。例如“假如猪能飞，我就给你一千万”，这句推理是正确的，因为猪不能飞。于是会有人说，凭什么你说这句推理是正确的呢？

其实网上也有各种讨论，其实这就是规定而已，没有什么道理可言。他们假设说，如果说推理不正确，可能带来的误会更大。例如“假如猪会飞，我就给你一千万”，我们宣布这句话是不正确的推理。这里就暗含了，猪真的飞了，而且你没有给我一千万的钱。其实会造成更大的误会。

##### 案例if n > 2  <=> n² > 4。 这是错误的双向implication。因为n可能是负数。

因此要双向检查验证看看。

## 公理的特性

1. consistent

   简单说就是一贯性，不能自相矛盾的例子出现。

2. complete

   完整，不能只证明其中一两个case，要全面。

实际上这个公理的要求，看似简单，实则很多数学家穷其一生在证明其中一些例子。因为数字是无穷的，你需要有办法完整覆盖。

还存在正确的proof，但是很难证明。例如，爸妈让你好好学习，你就能美梦成真。老师很可爱的说，这是wrong proof。哈哈，多么有趣的第一节课。



https://www.youtube.com/watch?v=L3LMbpZIKhQ&t=2095s

































