![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162104203.png)
##### 第一步：分割展平嵌入(patch embedding)
![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162111832.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162127486.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162128013.png)

**图片分割**

ViT首先将输入的224x224图片划分为多个小的视觉块（patch）。例如，在ViT-B/16模型中，图片被划分为每个大小为16x16的块。因此，对于224x224的图片，分割后可以得到：

- 每张图片的块数是14x14 。
- 每个块的大小为16x16，经过处理的块总数为196（14（行）* 14（列））。

 **展平和嵌入**

对于每个16x16的块，将其展平为一个一维向量。每个块的展平结果为：

- 每个块展平后为16x16x3=768维向量。

##### 第二步：添加token和位置编码（以及一层dropout）
![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162111630.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162124433.png)

### 第三步 encoder block  （x12）

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162137158.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162136954.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162138912.png)

第四步：mlp层
![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162147519.png)

![image.png](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411162147087.png)
