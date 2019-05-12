pytorch可以使用cpu 和gpu

CUDA（Compute Unified Device Architecture），是显卡厂商NVIDIA推出的运算平台。
CUDA™是一种由NVIDIA推出的通用并行计算架构，该架构使GPU能够解决复杂的计算问题。

查看显卡支持的

(https://jingyan.baidu.com/article/d169e1861b759f436611d882.html)

查看cuda是否安装
命令行nvcc -V

![image](https://github.com/jiaxingxx/SOM-pytorch/blob/master/1.jfif)

安装pytorch
https://pytorch.org/


国内安装conda方式太慢，基本会失败，所以用pip安装比较好

Anaconda是一个用于科学计算的Python发行版，支持 Linux, Mac, Windows系统，
提供了包管理与环境管理的功能，可以很方便地解决多版本python并存、切换以及各
种第三方包安装问题。
Anaconda利用工具/命令conda来进行package和environment的管理，并且已经包含
了Python和相关的配套工具anaconda 集成了很多科学计算中所需要的包，如numpy，
scipy等等，具体查看anaconda中已经预先安装配置好的包有哪些，可以通过cmd命令，
输入conda list 查看

conda可以理解为一个工具，也是一个可执行命令，其核心功能是包管理与环境管理。
包管理与pip的使用类似，环境管理则允许用户方便地安装不同版本的python并可以快速切换。
Anaconda则是一个打包的集合，里面预装好了conda、某个版本的python、众多packages、
科学计算工具等等，所以也称为Python的一种发行版。

但是，因为实际需求，我们会需要导入列表中没有的第三方包，如gemsim，在anaconda中，
我们可以参考以下步骤安装所需要的第三方包：
1、启动anaconda 命令窗口：

         开始 > 所有程序 > anaconda >anaconda prompt
2、安装gensim包

     在anaconda命令窗口中，输入pip install gensim

使用conda命令安装总是报http错误，在anaconda prompt下使用pip安装，完美解决了我的问题

电脑里只有anaconda时，cmd的pip也可以安装pytorch到anaconda环境中
