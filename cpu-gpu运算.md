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
