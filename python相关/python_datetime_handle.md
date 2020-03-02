# 数据清洗-常用方法
## 时间数据
### pandas 处理方法
#### 转化为时间对象
```python
#传入数据框
df = pd.to_datatime({'year': [2015, 2016],   
...                 'month': [2, 3],
...                 'day': [4, 5]})
pd.to_datetime(df)

output：
0   2015-02-04
1   2016-03-05


# 传入字符串 + 格式控制
pd.to_datetime('1700-01-01'     # 年份过早的情况下不能转化
                , format="%Y-%m-%d"
                , errors='ignore') 
#

# 传入时间戳
pd.to_datetime(1490195805, unit='s')
```
####  时间特征提取
```python 
Series.dt.date      # 日期
Series.dt.time      # 时间
Series.dt.year      # 年
Series.dt.month     # 月
Series.dt.day       # 日
Series.dt.hour      # 时
Series.dt.minute    #分
Series.dt.second    #秒

```

#### 简单操作
```python 
Series.dt.round("H")         # 取整（四舍五入）
Series.dt.ceil("D")          # 向上取整
Series.dt.floor("M")         # 向下取整
# S 秒、H 小时、D 天、M 月、 Y 年........ 


```
#### 时间序列创建及操作
```python
# 创建时间序列 
pd.date_range('2012-10-08 18:15:05', periods=4, freq='D')

['2012-10-08 18:15:05', '2012-10-09 18:15:05',
'2012-10-10 18:15:05', '2012-10-11 18:15:05']

# 两个时间年份差
# 两个时间月份差
# 两个日期周数差
# 两个日期天数差


```

### numpy 处理方法
### datetime 处理方法
### 相互转换