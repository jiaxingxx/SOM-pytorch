yield函数：
1.生成器，一种高效操作，生成SOM所有神经元位置
2.return

super（）
调用基类的一个方法，解决多继承的问题,super寻找type的父类
用法：
super(type[,object-or-type])

lambda
匿名函数，不用命名的简短函数
用法：lambda x:do_something x
表示lambda前输入为x，输出do_something x
例如：
min([i for i in range(len(self.weights))],
                            key=lambda x: np.linalg.norm(vect - self.weights[x]))


enumerate()
将可遍历的对象（如列表、元组或字符串）组合为一个索引序列，列出数据和数据下标，一般在for循环里
用法:
enumerate(sequence,[start=0])
sequence支持迭代的对象，序列，迭代器
start下标起始位置
返回对象
例如：
>>>seq = ['one', 'two', 'three']
>>> for i, element in enumerate(seq):
...     print i, element
... 
0 one
1 two
2 three

创建list
a=list()
然后添加值要用append
a.append()


# python 函数定义后的箭头什么意思？函数参数和返回值的注解形式

def isValid(s: 'str') -> 'bool':

    return s

这里的参数：‘注解内容’ 和 箭头‘注解内容’的用法是为标注了参数和返回值的类型，使代码更具有阅读性

和 def isValid(s):

        return s

效果上其实没有区别

  def twoSum(num1: int, num2: int=100) -> int:
  
    sum = num1 + num2
    
    return sum
    
注释内容后可以跟等号"=",意思为未传入实参时，该参数获得的默认值


# python自定义函数中什么是*args和**kwargs？

      def foo(*args, **kwargs):
          print 'args = ', args
          print 'kwargs = ', kwargs
          print '---------------------------------------'

    if __name__ == '__main__':
        foo(1,2,3,4)
        foo(a=1,b=2,c=3)
        foo(1,2,3,4, a=1,b=2,c=3)
        foo('a', 1, None, a=1, b='2', c=3)

输出结果如下：

    args =  (1, 2, 3, 4) 
    kwargs =  {} 
    --------------------------------------- 
    args =  () 
    kwargs =  {'a': 1, 'c': 3, 'b': 2} 
    --------------------------------------- 
    args =  (1, 2, 3, 4) 
    kwargs =  {'a': 1, 'c': 3, 'b': 2} 
    --------------------------------------- 
    args =  ('a', 1, None) 
    kwargs =  {'a': 1, 'c': 3, 'b': '2'} 
    ---------------------------------------

可以看出实际上，args传递任意多个无名参数就是tuple类型，kwargs传递关键字参数就是dict类型。
所以实际上*参数1传递的就是tuple，而**参数2传递的就是dict。


# Python中“if __name__=='__main__':”理解与总结

https://www.cnblogs.com/chenhuabin/p/10118199.html


# Python如何忽略warning的输出

  import warnings

  warnings.filterwarnings('ignore')

命令行下：

  python -W ignore file.py
  
https://blog.csdn.net/xiaodongxiexie/article/details/65646239

# Python os.rename() 重命名目录和文件

概述

os.rename() 方法用于重命名文件或目录，从 src 到 dst,如果dst是一个存在的目录, 将抛出OSError。

语法

rename()方法语法格式如下：

  os.rename(src, dst)
  
参数

src – 要修改的目录名
dst – 修改后的目录名

返回值

该方法没有返回值

该方法 可以重命名 文件 和目录，
如果 src参数 对应文件或目录，不存在，会保错，
如果 dst 参数 对应文件或目录，已经存在，也会报错

https://blog.csdn.net/wowocpp/article/details/79460407
