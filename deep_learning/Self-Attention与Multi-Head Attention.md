### Self-Attention
![67a83ae5200746cd919471e73e363e6.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112309256.jpg)

![ccb8337f1f99fb6bf9297ffe1c48d21.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112311285.jpg)

![e1074f49dcc410f3054609ed3ebaf9d.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112311901.jpg)

输入x经过input embedding变成$a$，$q=a\cdot W^q$，$k=a\cdot W^k$，相关性$\alpha=q\cdot k$(也可以使用其他方法来计算$\alpha$)。$\alpha$经过softmax之后得到$\alpha '$,$\alpha '$与$W^v$相乘得到b。
又，这是一个可并行化的过程，所以可以写成矩阵相乘的形式。
总体来说，就是得出了下面这个公式。（$d$代表向量 $k^i$ 的长度，除以$\sqrt{d}$ ​ 的原因在论文中的解释是“进行点乘后的数值很大，导致通过softmax后梯度变的很小，所以通过除以$\sqrt{d}$ 来缩放。)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112320051.png)



![152a49bc990934c95c20a0db85898fa.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112325966.jpg)
![2ccbe384d0ba72e6fb436d5baf9f7f5.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112328907.jpg)
![d9a5b796eb7afcc19e4bffca83982b3.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112328120.jpg)
![2326e19275fa76d66d31628a73c3709.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411112328217.jpg)
化简到最后，发现除了输入，也就只有$W^q,W^k,W^v$三个参数需要学习。


### Multi-Head Attention