#
![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410111754924.png)

CNN层：和之前ResNet 卷积层的训练相似。（把图片缩小）
1x1 Cov : 用来减少通道数。
Transposed conv ：把图片还原成输入时的维度，k是通道数，表示是k类分类。


### 转置卷积

转置卷积也是一种卷积
卷积不会增大输入的高宽，我们引入转置卷积用来增大输入的高宽。（向上采样）

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410111954198.png)


![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202410112025946.png)
