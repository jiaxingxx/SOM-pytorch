1.修改CPU版本的pytorch模型到GPU版本
从github上git下来的CNNs程序需要将分类结果在opencv上显示，图片是采用单帧处理，因此每一帧的图片返回类别与置信度的速度需要加快，于是想到该CPU版本的模型到GPU版本。

在参考网上的文档和博客后，发现只要在模型和参数后加.cuda()即可将模型由cpu上的运算调到gpu上运算。

首先需要确定自己的pytorch版本能否进行gpu计算。

print (torch.cuda.is_available())

1
如果结果是True，则可以进行gpu计算，如果是False,就需要安装gpu版本的torch或是CUDA了。还可以通过

print (torch.cuda.device_count())

pytorch中GPU与CPU的相互转化
深度学习中我们默认使用的是CPU，如果我们要使用GPU，需要使用.cuda将计算或者数据从CPU移动至GPU，

如果当我们需要在CPU上进行运算时，比如使用plt可视化绘图, 我们可以使用.cpu将计算或者数据转移至CPU.
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import torch
from torch.autograd import Variable

# 将变量或者数据移到GPU
gpu_info = Variable(torch.randn(3,3)).cuda()
# 将变量或者数据移到CPU
cpu_info = gpu_info.cpu()

2.在PyTorch中使用GPU和TensorFlow中不同，在TensorFlow如果不对设备进行指定时，TensorFlow检测到GPU就会把自动将数据与运算转移到GPU中。而PyTorch类似于MxNet，需要显性的指定数据和运算放在哪里执行，这样的操作比较自由，却也有些繁琐。因为如果哪一步忘记转换了就会运行出错。

3.对于自己创建的模型类，由于继承了torch.nn.Module，则可同样使用.cuda()来将模型中用到的所有参数都存储到显存中去。
