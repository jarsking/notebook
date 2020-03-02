# 容易出错的细节总结
## 逻辑运算
### python
```python 
# 纯python下的与、或、非只能对单个逻辑值进行操作
# 使用函数实现
print(not(True))
print((False)and(True))
print((False)or(True))

output:
    False
    False
    True

# 使用按位运算
print(~(True))
print((False)&(True))
print((False)|(True))

output:
    -2
    False
    True
```
> 纯python的模式下按位取反不能使用
### pandas
```python 
# pandas 没有提供对应的API，或者函数，这里使用python按位取反
S_test1 = pd.Series([True,True,True,False])
S_test2 = pd.Series([False,False,False,True,])
print(S_test1)
print(S_test2)

output:
    0     True
    1     True
    2     True
    3    False
    dtype: bool
    0    False
    1    False
    2    False
    3     True
    dtype: bool
# 与
S_test1 & S_test2

output:
    0    False
    1    False
    2    False
    3    False
    dtype: bool
# 或
S_test1 | S_test2

output:
    0    True
    1    True
    2    True
    3    True
    dtype: bool
# 非
~S_test1

output:
    0    False
    1    False
    2    False
    3     True
    dtype: bool
```
### numpy
```python 
###############################################
#  使用numpy提供的逻辑运算函数
A_test1 = np.array([True,True,True,False])
A_test2 = np.array([False,False,False,True,])
print(A_test1)
print(A_test2)

output:
    [ True  True  True False]
    [False False False  True]

# 与
np.logical_and(A_test1 , A_test2)

output:
    array([False, False, False, False])
# 或
np.logical_or(A_test1 , A_test2)

output:
    array([ True,  True,  True,  True])
# 非
np.logical_not(A_test1)

output:
    array([False, False, False,  True])

###############################################
# 使用逻辑运算符

# 与
A_test1 & A_test2

output:
    array([False, False, False, False])
# 或
A_test1 | A_test2

output:
    array([ True,  True,  True,  True])
# 非
~A_test1

output:
    array([False, False, False,  True])


```

```

```