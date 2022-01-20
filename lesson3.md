https://www.youtube.com/watch?v=NuGDkmwEObM

## 专业名词

lemma 辅助定理，用来增强推到到更进一步的结论的辅助快捷定理

polynomial 多项式，意思是有多个参数的方程式，例如*x*3 + 2*xyz*2 − *yz* + 1.

dignoal 斜过来的

invariant 恒定量，不变式子

parity 

Inversions 颠倒

substract 减去

precedes 领先于

## 课程笔记内容

证明定理定proof的特点

1. correct
2. complete 
3. Clear
4. brief
5. elegant 
6. well organized 
7. In-order

老师夸张的说，你最好能证明到从1=1倒推到你的结论，这样子的证明才是步步为营，稳扎稳打。

一个好的proof就好像一个好的代码段。老师讲了几个代码导致的事故历史，airbus的第一次意外开了门，因为一个程序bug。还讲了一个x光做胸片的，不慎高强度给了超高辐射的惨案。还讲了Gorge Bush总统竞选因为一个软件bug导致的竞选失败。老师还顺带吹了牛逼，他是akamai的创始人之一。我操。全世界绝大部分网站都是他们分发了很大一部分的，他也谈到，软件bug会导致全球性的事故。

他开了个玩笑，50年后，也许你坐的飞机的代码，是你身边的学习编程的同学写的，因此你要极度小心，让写的代码按照既定的目标去执行。does it what supposed to do。

讲了著名的费马定理

https://en.wikipedia.org/wiki/Fermat%27s_Last_Theorem

他讲了10大不该使用的proof

1. proof by throwing in the kitchen sink meaning

To throw the kitchen sink means **to use up one's last resource, exhausting everything one is capable of, to achieve an objective**. The expression derives from World War I or II, when households in the Unted Kingdom gave up everything they had except the kitchen sink to meet the mad demand for material, especially metal.

意思是是，别一句带过，说proof就在fact里，让老师自己琢磨。。。哈哈，有的学生就这么鸡贼的

2. 后面说了很多，不要潦草，不要引用某个大数学家的论据，有可能人家就是错的。我不翻译了，这老师约法三章在前。



#### 例题1

这就是经典的华容道，但是是个3*3的9宫格里，放了a,b,c,d,e,f,g,h。从上到下依次排列，但是g,h放反了位置了，看你是否有能力翻转回正常场景。经过小游戏后，老师提出来了命题

Theorem it's impossible to make any sequence of legal move to return the original position.

这个解题的方法则是：

invariant 不变量

寻找不变量，永久都不会变的，来证明这个华容道是永久无法复原的。



定理一：老师现场演示了一个字母的左右移动，从上往下读的顺序是不发生任何变化的。

定理二：这个需要稍微动手玩一下，你就会发现每个上下移动的瞬间，移动的数字都是或前进/后退2格子的字母。也就是说，

定理三：在移动过程中，inverted pair的次数必须是偶数次增减，或者保持不变。

字母顺序错乱的pair，我们管它叫inverted pair。字母顺序错乱，指的是相对关系本该alphabeta的顺序，实际上它却跟本该有的顺序不对，我们就认为是一个inverted pair。如果这个inverted pair的数量是奇数，那么它永远回不到过去，因为起始点正确的应该是0，然后任何一次正确的移动，总是+2，-2。

如何证明定理3呢？

分类梳理每个case

1. row左右移动，顺序保持不变
2. column的移动，2个前后的跳动，因此总是成双的修改顺序 

因此可以发现，

column竖着移动一次，交换了前后的顺序。因此必须是偶数次，才能恢复正常。

定理4: 每个开局的状态中，无法恢复的pair，永远是奇数。



ok，我们开始使用归纳法。

假定这个理论是对的，

我们的base case P(0), 即如果一步都不动，那么有奇数个inverted pair。G/H的位置颠倒了，从顺序上讲，其他都是正常的。

那么P(n)我们就假定都不能推导到正常的顺序。我们只需要证明，P(n+1)依然无法恢复正常，就可以彻底完成推理归纳。

按照定理4，无论你如何挪动，它是奇数的pairity，它永远都是奇数。

因此，我们可以得出结论，无论如何你怎么改动这个顺序，它永远都恢复不到正常的状态。



这节课这道题推理很短，20分钟，花了我一周时间来来回回反复的看，才看懂。当然了，我其中玩了无数次华容道，打瞌睡，真的坚持下来非常不容易。





下一个内容是介绍了strong induction， axiom

跟ordinary induction的区别是，前者通过P(n) implies P(n+1), 而strong的方式则通过P(0), P(1).... P(n) implies P(n+1)

老师玩了一个很有趣的对比游戏。

8个积木，每次拆开2组，就把他们拆的那组的数字相乘，得出积分，以此类推，直至只剩下1乘以1。惊讶的是，无论你如何拆，最终结果居然都是28。

于是题目来了，证明8无论如何拆，相乘的最终的积分之和，永远是28。

 Theorem来了，任意策略 n block的游戏，produced same score。S(n)

例如 S(8) = 28

Base case: 

n = 1. S(1) = 0 ,因为1没法拆，没法相乘，直接为0

Induction step: 

从P(1), P(2)....P(n)来证明P(n+1)

Look at n+1 blocks , 

P(n+1) 的积分之和，肯定是P(n) 加上 P(n+1)的拆分结果，假定左边拆为K，右边则为n+1-K

那么S(n+1)的结果就是 k * (n+1-k)  + P(k) + P(n+1-k) , 我们试图证明它与K无关。

结果就发现自己堵住了，因此，再次make strong induction, 我们认为S(n) = n*(n-1) / 2 

把上面的公式代入，果然K就可以自行消掉了，S(n+1) 就等于 n(n+1)/2





