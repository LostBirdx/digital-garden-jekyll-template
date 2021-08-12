## 基础的数据类型
### dataframe
pandas 的最基本的数据类型对象,直接读取进来的都是DataFrame

```python
	
	df = pd.read_excel('rameta.xlsx')
```

### Series
从一个dataframe里面取一个列就是一个Series

```python
s = pd.Series([1, 3, 5, np.nan, 6, 8])
```




### 怎么删除某一行或者某一列  
https://blog.csdn.net/m0_45210226/article/details/108942015  
#数据预处理