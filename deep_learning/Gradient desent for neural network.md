## gradient descent
![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410062024149.png)
**$a_i^{[1]}$下标$i$代表node in layer；上标数字代表是第几层隐藏层。**

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410062029732.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410062033803.png)

综上，
层数有：$n_x=n^{[0]},n^{[1]},n^{[2]}$
参数有：$w_{(n^{[1]},n^{[0]})}^{[1]},b_{(n^{[1]},1)}^{[1]},w_{(n^{[2]},n^{[1]})}^{[2]},b_{(n^{[2]},1)}^{[2]}$
代价函数为：$$J(w^{[1]},b^{[1]},w^{[2]},b^{[2]})=\frac{1}{m}\sum_{i=1}^{n}L(\widehat{y},y)$$

注：$L(\widehat{y},y)$是损失函数,其中$\widehat{y}$即为$a^{[2]}$
所以要训练参数，我们需要对算法进行梯度下降的计算。
在训练神经网络的时候，随机初始化参数很重要。
一旦把初始化参数为某些值之后，每个梯度下降的循环都会计算预测值。
每一次运行梯度下降，都会重复计算以下内容：
$$\widehat{y}$$   $$dw^{[i]}=\frac{\partial{J}}{\partial{w^{[i]}}}$$  $$db^{[i]}=\frac{\partial{J}}{\partial{b^{[i]}}}$$ $$w^{[i]}=w^{[i]}-\alpha{w^{[i]}}$$ $$b^{[i]}=b^{[i]}-\alpha{b^{[i]}}$$



![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410062103363.png)


## stachastic gradient descent（随机梯度下降）
在数据量很大的时候，采用梯度下降，运行速度十分缓慢。于是，引入随机梯度下降。
每个步骤只随机选择一个样本，并仅使用该样本来计算，从而减少计算的项数，计算成本更低，提高运算速度。
此外，随机梯度下降在数据存在冗余的时候可以发挥出更大作用。
值得注意的是，虽然随机梯度下降在严格定义下，每一步仅对一个随机样本进行计。但在实际应用过程中，每一步选择一小部分数据或者小批量数据进行计算更为常见。介于单个样本点和所有样本之间，使用小批量（mini-batch）可以对参数进行更稳定的估计，


### mini-batch gradient descent
batch gradient descent 同时处理整个训练集
而mini-batch gradient descent，每次同时处理的是单个的mini-batch $X^{\{i\}}$,$Y^{\{i\}}$,而不是同时处理全部的$X$和$Y$训练集。
![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410091952475.png)
$X^{[i]}$和$Y^{[i]}$示例如上图。