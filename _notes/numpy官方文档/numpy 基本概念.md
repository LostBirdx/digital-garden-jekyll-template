numpy's ,main object is the homogeneous multidimensional array.
## axes
dimensions are called`axes`in numpy

```
[[ 1., 0., 0.],
 [ 0., 1., 2.]]
```

2axes, first axis length = 2,second axis length = 3

## ndarray
NumPy’s array class is called `ndarray`   it is also known by the alias `array`,`numpy.array`(到底有没有numpy.array这个class呢?)
### ndarray的创建
每个函数输入不同的参数要求.

```python
a = numpy.array()   	#指定object 和dtype
a = numpy.zeros()		#指定shape和dtype
a = numpy.arange()		#1参数,2参数,3参数
a = numpy.linspace()	#指定起点,终点,元素的个数,endpoint是不是包括
a = numpy.ones()		#指定shape和dtype
a = numpy.empty()		#指定shape和dtype

```

以上的这些都可以去numpy 的[官方文档的API手册](https://numpy.org/doc/stable/reference/generated/numpy.empty.html?highlight=numpy%20empty#numpy.empty)里面查到的
#### np.array()
`array` is a function used to create an array.

```Python
>>> import numpy as np
>>> a = np.array([2,3,4]) #这里要理解成一个list 通过array函数转换成了np.array
>>> a
array([2, 3, 4])
>>> a.dtype
dtype('int64')
>>> b = np.array([1.2, 3.5, 5.1])
>>> b.dtype
dtype('float64')
```

```Python
>>> a  = numpy.array([1,2,3])
>>> type(a)
<class 'numpy.ndarray'> #他不会说你是numpy.array的,那么有没有numpy.array呢?
>>> 
```

np.array一般指定两个参数,object 和dytype
```python

c = np.array( [ [1,2], [3,4] ], dtype=complex )
```


#### np.arange()
函数返回一个有终点和起点的固定步长的排列，如[1,2,3,4,5]，起点是1，终点是6，步长为1。
参数个数情况： np.arange()函数分为一个参数，两个参数，三个参数三种情况
1）一个参数时，参数值为终点，起点取默认值0，步长取默认值1。
2）两个参数时，第一个参数为起点，第二个参数为终点，步长取默认值1。
3）三个参数时，第一个参数为起点，第二个参数为终点，第三个参数为步长。其中步长支持小数

```python
#一个参数 默认起点0，步长为1 输出：[0 1 2]
a = np.arange(3)

#两个参数 默认步长为1 输出[3 4 5 6 7 8]
a = np.arange(3,9)

#三个参数 起点为0，终点为3，步长为0.1 输出[ 0.   0.1  0.2  0.3  0.4  0.5  0.6  0.7  0.8  0.9  1.   1.1  1.2  1.3  1.4 1.5  1.6  1.7  1.8  1.9  2.   2.1  2.2  2.3  2.4  2.5  2.6  2.7  2.8  2.9]
a = np.arange(0, 3, 0.1)

```