# 鸣谢

本项目基本参考[@letiantian](https://github.com/letiantian)大神的[Pinyin2Hanzi](https://github.com/letiantian/Pinyin2Hanzi)作品，详情可以点击查看

## 安装

安装和使用方法参考[Pinyin2Hanzi](https://github.com/letiantian/Pinyin2Hanzi)

## 示例

```
from MHPinyin2Hanzi import DefaultHmmParams
from MHPinyin2Hanzi import viterbi

hmmparams = DefaultHmmParams()

# 2个候选
pinyin = (
   "si","dao","luan","le","ma","xiong","hai","zi")

result = viterbi(hmm_params=hmmparams, observations=pinyin,
                 path_num=2)

print(pinyin)
for item in result:
    print(item.score, item.path)
```
输出
```
('si', 'dao', 'luan', 'le', 'ma', 'xiong', 'hai', 'zi')
5.950955778865384e-20 ['是', '捣', '乱', '了', '吗', '熊', '孩', '子']
1.7656844345456464e-20 ['是', '捣', '乱', '了', '嘛', '熊', '孩', '子']
```
更多示例见example
## 训练
原始数据和训练代码在`train`目录下。数据来自[jpinyin](https://github.com/stuxuhai/jpinyin)、[pinyin](https://github.com/overtrue/pinyin)、[搜狗语料库-互联网词库](http://www.sogou.com/labs/dl/w.html)等。处理数据时用到了汉字转拼音
工具[ChineseTone](https://github.com/someus/ChineseTone)。

## 原理

在[如何实现拼音与汉字的互相转换](http://www.letiantian.me/2016-02-08-pinyin-hanzi/)的基础上，我们将常见易发错的拼音作为多音字用于模型训练,见train下processTrain.py

## License
MIT



