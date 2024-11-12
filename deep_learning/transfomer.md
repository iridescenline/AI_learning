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

### Decoder

begin产生第一个输出“机”。

![51ff4a446c661fe0b3b3bfabcaae4f3.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122138699.jpg)
decoder的一部分输入来源于自己的输出。（这也是为什么decoder只能使用Masked Multi-Head Attention的原因）

![60de71123e2b82e85355fd08a4e90e9.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122139255.jpg)

![5c97cdf044fda2fbae6f4040f2cf933.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122138665.jpg)

Masked Multi-Head Attention
![102d18c0f859f39ed5232dec047c736.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122141387.jpg)
![74a96adea0b897bd910c67118df587b.jpg](https://erin-53347-1330131220.cos.ap-guangzhou.myqcloud.com/202411122141769.jpg)


那么，decoder是如何输出正确的输出序列长度的呢？
