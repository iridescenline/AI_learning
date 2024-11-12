encoder+decoder
### Encoder:
class token（论文用的是1维）+Positional embedding
encoder做的事情是将输入序列x to 另一个序列h。
Encoder中有多个block块。每个block块有多个操作。包含multi-head attention和residual connection和layer normalization（在transformer中使用的是layer norm，而并不使用 batch norm） 和 linear （orz FC）。
![0dde0b9569e5cbd967f2a6efa758ce5.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122106894.jpg)

![a3fd172c192d0a525f1c8be25c99f23.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122107356.jpg)
![ae97e7b5f66d7e7c6a9dfeef1ce0932.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122112985.jpg)

而还有更多细节可以探究，比如为什么用layer norm，而不是用 batch norm？以及encoder中block内的操作顺序更换位置，效果又会如何？

![dce2280f3349b5bf57e07bb111b1e7b.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122117250.jpg)
