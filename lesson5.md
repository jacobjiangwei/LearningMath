https://youtu.be/XX7ePR21Ook

## 专业名词

denote 表示

divisible 可除尽的

scheme 方案

remainer 余

modular arithmetic 模算数理论

## 课程笔记内容


这是一个number theory的第二节课。

从加密故事开始说起。

首先程序的世界里，无非都是函数。输入明文m，根据密钥，Encryption函数输出加密文m'。反之，输入加密文m',根据Decryption函数输出明文m。


#### 第一次尝试乘法prime加密

先讲了一个基础事件，1936年，用数字原理加密用于作战信息传递。他的方案，就是把每个字母都转成26字母中的数字，最终编码成了一个数字串。然后他还非要转换成prime number，因此他就干脆在数字后面塞了一个13，使得任意数字变成了质数。注意，不是每次加13都变成了质数。

然后提前传输了一个prime number k作为密钥。

因此 Encryption: m' = m * k ， 两个prime number相乘得出结果就是密文m'
反之 Decyption:  m = m' / k

而有一个理论要牢记，给定2个很大的prime number相乘的结果，是很难高效反推出来其中任意一个数字的。想想都知道啊。。。

但是这个方案虽然简单，但是破绽也很明显。假定我获取了2个密文m1' 和 m2'。他们的数字里都是k的倍数。也许通过求最大公倍数gcd也许就能找到k。答案就解开了。

#### 第二次尝试secret prime K和public prime P共同相乘加密

这次我们依然m的消息是number，范围是0～p-1

这次Encryption m' = rem(m * K, P )  这是求余的过程，依然是m 乘以 k, 但是这次用P来求余

显然这个 Decryption 公式很难算出来了。不知道余数P, 就算知道多个拦截的信息m1', m2'都无济于事。


这里要穿插一个视频 
https://youtu.be/QsKtEuUyIdw

Prime divisibility 

Lemma:  if p is prime and p | a * b , then it implies p | a or p | b.

Proof: 
很简单如果p不能整除掉a，那么gcd（p, a) = 1, 既然最大公约数是1，那么根据上一节课倒腾水杯的实验结果，那么就是他们总存在一个左边倒腾多少次，直至剩下1升水。也就是说肯定存在一个integer s, t，使得 s * p + t * a = 1

那么至此全部都乘以 b

s * p * b + t * a * b = 1 * b
这时候，因为第一部分是有p的，肯定是p的linear combination，右边的 a * b本身就是p的整数倍，那么 b肯定是他们相加的结果，因此b肯定是p的整数倍。

因此只要 a * b能整除p，那么p就至少可以整除其中一个。


回归原课

Def x is congruent to y module n , X三等号y(mod n), if n 可以整出掉 （x - y )。
这个定义很无聊，就是x-y的余数是n的倍数。
例如 31 is congruent to 16 mudulo 5。31-16=15，15是5的倍数。

实际上模计算在生活中很常见，譬如24小时制度，我们常常默认计算20点，就是8点。那么20点和8点就是模相等。

Def Multiplicative Inverse

看这个之前，还得恶补一下模运算

https://www.youtube.com/watch?v=KvtLWgCTwn4

a 三 b  （mod n ) iff rem(a,n) = rem (b,n)

iff是if and only if 有且仅有的意思
如果a除以n的余数与b除以n的余数相等，那么可以认为a与b congurent，翻译过来有叫全等的。实际上意思是，总归能用mod n的倍数靠近过去。

挺好证明的，如果 a % n = b % n ,  那么我们假定 a = Qa * n + Ra  代表a是有Qa个n组成还有余数Ra。同样b = Pb * n + Rb
那么a - b =(Qa-Pb) * n + (Ra-Rb)
如果 a % n = b % n  ，那么意味着Ra = Rb , 因此a - b 是n的整数倍，因此a和b是congruent to modulo N

继续往下推理，还能证明a 三 rem(a,n) (mod n) 其实挺简单的 右边的是a%n的余数，显然余数小于n。那么a减去a跟n除法的余数，当然剩下来的就是n的倍数。

简单来说，6 三 1 (mod 5) ，意思是6和1在模数5前面，是全等的，他们都会除5的余数是1。用一个通俗的原理，拿一把长度为5的尺子来量绳子，遇到超过长度的就打转，返回继续计算，直至多余的长度在尺子长度内，若相同，则认为全等。

那么回到解密的课题

m' = m * k % p, 假定key和p提前沟通好了，怎么解密呢？

m'可以写为rem(m*k,p) , 公式可以改写为 rem( mk, p) 三 mk (mod p) ， 也进一步变为 m' 三 mk (mod p)

那么再加一个假设 k * 1/k 三 1 ( mod p) 这里有点难理解, 普通integer数字k是很难找到另一个integer直接等于1的。但是在模运算中存在。例如7 * 3 三 1 (mod 5)，3*7-1 = 20，是5的倍数。

因此 假定存在k^{-1}, 那就两边都相乘k^{-1}， m' * k^{-1} 三 m  (mod p)

因此很容易反向计算出来 m = rem(m' * k^{-1} , p) 。 注意m 必须小于prime p

这里弄个实测一下 p = 23 , k = 15, 要发送的消息是m = 16 
那么 m' = rem ( 16 * 15, 23) = 10

解密前，先需要找到k^{-1} ， 使得 k * k^{-1} = 1 (mod 23) , 也就是找到  15 * k^{-1} 三 1 (mod 23) , 这里实际上有专门的公式可以快速的计算。

这里发现 k^{-1} = 20， 因为 20* 23 = 299， 15*20 = 300， 正好mod 1

m = rem（ 20 * 10， 23） = 200 % 23 = 16， 完美复原了消息，并且只要自己把握好key和prime，那是断然不会被第三方劫持的消息破解的。

### plain message attack

其实这个算法也是有机会破解的，例如有人故意逮着特殊时期，知道对方发送的消息的原文和密文的对应关系。譬如，日本开始进攻了这类有办法推测的消息。

拿到了m' 和 m，如何反解释出来k呢？注意，p是公开的，可以协商的prime数。

根据公式，  m' = rem (m*k, p)   m = rem( m' * k^{-1}, p)

m' 三 m*k ( mod p)


这两个公式相乘 

这时候如果m可以算出来 m^{-1} (mod p)的话，我们可以两边相乘 m^{-1}

m'= * m^{-1} 三 m *  m^{-1} * k (mod p)

m' * m^{-1} 三 k ( mod p)

由此可以反推算出来key

这里再次演算一下，假定我没知道 p=23， 但是不知道 k, 我没知道发送的是m = 16，接收到的是 m' = 10的对应关系

那么先算 m^{-1}，  m^{-1} * m 三 1 ( mod p), m^{-1} * 16 三 1 ( mod 23)， 很显然 m^{-1} = 13， 因为 13 * 16 = 208，  208 -1 = 23*9

m' * m^{-1} 三 k ( mod p)  = >  10 * 13 三 k ( mod 23) ， 于是可以推算出来 k = 130 % 23 = 15, 由此得出 k = 15;

### 接下来会将fermat's little theorem 


属于我自行加菜，学习了证明方法

![属于我自行加菜，学习了证明方法](https://github.com/jacobjiangwei/LearningMath/raw/main/IMG_2305.jpg)

### Euler's theroem

![](https://github.com/jacobjiangwei/LearningMath/raw/main/IMG_2310.jpg)

### RSA 算法 
![属于我自行加菜，学习了证明方法](https://github.com/jacobjiangwei/LearningMath/raw/main/IMG_2340.jpg)

![测试代码](https://github.com/jacobjiangwei/LearningMath/raw/main/IMG_2341.jpg)
