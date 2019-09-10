




pytorch可以使用cpu 和gpu

# CUDA（Compute Unified Device Architecture），
是显卡厂商NVIDIA推出的运算平台。
CUDA™是一种由NVIDIA推出的通用并行计算架构，该架构使GPU能够解决复杂的计算问题。

查看显卡支持的

(https://jingyan.baidu.com/article/d169e1861b759f436611d882.html)

查看cuda是否安装
命令行nvcc -V

![image](https://github.com/jiaxingxx/SOM-pytorch/blob/master/1.jfif)

安装pytorch
https://pytorch.org/


# 国内安装conda方式太慢，基本会失败，所以用pip安装比较好

anaconda prompt可以敲pip安裝，但会安装到系统python3的安装路径中，要想安装在anaconda中，还是用conda

# pip 将 某包指定到某目录  

安装：

pip install --target=d:\somewhere\other\than\the\default package_name

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

# miniconda

是简化版anaconda，下载安装后自带base环境，一般创建项目环境，然后激活项目环境，使每个项目之间不干扰，

命令行默认一开始在base环境操作，此时conda install 会安装在base环境中，需要cd 到自己建的项目环境中，指定环境中conda install

详细官方文档(https://conda.io/projects/conda/en/latest/user-guide/getting-started.html#managing-packages)

## 如何防止打开终端Conda默认激活基本环境

当你安装好Anaconda，每次打开终端都会自动帮你激活基本环境（base），有时候确实自己不需要激活Conda环境（因为打开终端不一定要用到 Python），而且该项操作还会拖慢打开的终端的响应速度，十分烦人，经过网上查找方案，直接在终端输入：

	conda config --set auto_activate_base false

第一次运行它时，它将在主目录中创建./condarc，并使用该设置覆盖默认值。




# 1.卸载Pytorch

使用conda卸载Pytorch

conda uninstall pytorch

conda uninstall libtorch

使用pip卸载Pytorch

pip uninstall torch

安装问题详细(https://blog.csdn.net/aa3615058/article/details/89339790#condavitualenvpipenv__10)


# 安装PyG

步骤

miniconda安装，anaconda prompt创建项目环境，激活项目环境

	conda install numpy
	conda install pytorch torchvision cpuonly -c pytorch
	pip install --verbose --no-cache-dir torch-scatter
	pip install --verbose --no-cache-dir torch-sparse
	pip install --verbose --no-cache-dir torch-cluster
	pip install --verbose --no-cache-dir torch-spline-conv
	pip install plyfile
	pip install rdflib
	pip install torch-geometric
详细参考 (https://github.com/rusty1s/pytorch_geometric/issues/633#issuecomment-523323111)
