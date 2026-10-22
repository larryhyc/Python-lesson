# python 的基础语法

### 语言基本特征
* 解释型
* 强类型
* 动态类型
* 面向对象

### 注释
```python
# 单行注释

"""
多行注释
"""

'''
多行注释
'''
```

### 数据类型


|类别|类型名|字面量|说明|
|--|--|--|--|
|数字类型|int|1，2，-3，0|支持无限大小|
|数字类型|float|1.5,-0.3,2e10|64位双精度|
|数字类型|complex|1+2j,3-4j|j表示-1的平方根|
|数字类型/布尔类型|bool|True,Flase|True是1的别名，False是0的别名|
|字符串|str|"hello","world"|||
|空置|NoneType|None||
|容器类型|多种类型|数组，对象，字典等|||

### 变量
在python中所有的变量都必须赋值，不能创建一个不赋值的变量

|类型|规范|示例|
|--|--|--|
|变量名|小写字母，下划线分隔|user_name|
|常量名|全大写字母，下划线分隔|MAX_SIZE|
|类名|大驼峰命名|UserInfo|
|私有变量|以下划线开头|_internal、__private|

#### 变量值的交换
```python
x,y = 10,20

x,y = y,x
```

#### 变量的类型转换
```python

ange = 10

ange2 = str(ange)
``` 

### 字符串格式化
```python
name = 'larry'
age = 21
print(f"姓名：{name},年龄{age}")
```
变量的值会替换掉输出时候的变量

### 逻辑运算符
|运算符|说明|返回值规则|
|--|--|--|
|and|逻辑与|第一个为False则返回第一个，否则返回第二个|
|or|逻辑或|第一个为True则返回第一个，否则返回第二个|
|not|逻辑非|返回Ture或False|

### 链式比较
python 支持链式比较，可以像数学公式一样连续写比较运算符
```python
x = 5
print(1 < x < 10) #True 
```

### 海象运算符(:=)

同时给变量赋值，并且同时计算表达式的值

```python
while (line := input("输入:")) != "quit":
  print(f"你输入了{line}")
```

### 输入输出
* 输入：print
* 输出：input
```python
name = input("输入你的名字")
print(name)
```