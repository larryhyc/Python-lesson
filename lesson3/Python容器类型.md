### Python容器类型

|类型|名称|是否可变|是否有序|元素是否可重复|示例|
|--|--|--|--|--|--|
|list|列表|可变|有序|可重复|[1,2,3,4,5]|
|tuple|元组|不可变|有序|可重复|(1,2,3)|
|dict|字典|可变|有序|键不可重复|{"a":1,"b":2}|
|set|集合|可变|无序|不可重复|{1，2，3}|
|str|字符串|不可变|有序|可重复|"hello"|

### 列表
列表是python中最常用的可变、有序容器、可以存储任何类型数据

#### 创建列表
```python
# 字面量创建
nums = [1,2,3,4,5]

mixed = [1,"hello",3.14,True,None]

empty = []

# 通过函数创建
chars = list("abc")
nums2 = list(1,2,3,4,5)
```

#### 索引与切片

```python
nums = [1,2,3,4,5]

print(nums[0]) # 1
print(nums[-1]) # 5

# 切片
print(nums[1:4]) # [2,3,4] -- 范围（1，4)
print(nums[:3]) # [1,2,3] -- 返回(0，3)
print(nums[2:]) # [3,4,5] --索引2到末尾
print(nums[::2]) # [1,3,5] --从头到尾，步长为2
print(nums[::-1]) # [5,4,3,2,1] --从头到尾，步长为-1即倒叙
```

### 元组
创建元组

```python
point = (1,2)
point = 1,2 # 等于(1,2)
single = (1,) # 单个元素比较要加逗号
empty = () # 空元组

# 通过tuple()函数创建
t = tuple([1,2,3]) # (1,2,3)
```

#### 基本操作
元组可以使用切片和索引，这跟列表是一样的方式

#### 元组解包
```python

coord = (1,2)

x,y = coord
print(x,y) # 3,4

# 扩展解包
first, *rest = (1,2,3,4,5)
print(first) # 1
print(rest) # [2,3,4,5]

*rest,last = (1,2,3,4,5)
print(rest) # [1,2,3,4]
print(last) # 5
```

### 字典
字典存储的是键值对，相当于哈希表

#### 创建字典
```python
person = {
  "name":"larry",
  "age":21,
  "city": "南宁"
}

empty = {}

# 通过dict函数创建
preson = dict(name="larry",age=21,city="南宁")

preson = dict({"name","larryhyc"},{"age",21})

d = dict(["a","b","c"],0) # {"a":0,"b":0,"c":0}
```

#### 访问与修改
```python
person = {
  "name":"larry",
  "age":21,
  "city": "南宁"
}

print(person["name"]) # larry
print(person.get("name")) # larry

# 添加/修改
person["gender"] = "男" # 添加
person["age"] = 22 # 修改已有

# 批量更新
person.update({"phone":"12345","age":23})

# 删除
del person["phone"] # 删除键值对
value = person.pop("age") # 删除并返回值
last = person。popitem() # 删除并返回赘疣插入的键值对
person.clear() #清空
```

### 集合
集合是无序，不重复的元素集合，支持数学上的集合运算
#### 创建集合

```python
nums = {1,2,3,3,3} # {1,2,3} 自动去重
empty = {} # 空集合

# 通过set()函数创建
nums = set([1,2,3,4])
chars = set("hello") # {"h","e","l","o"}
```

#### 集合操作

```python
s = {1,2,3}

# 添加/删除

s.add(4) # {1,2,3,4}
s.remove(2) # {1,3,4}
s.discard(10) #
s.pop() #随机删除并返回一个元素
s.clear() # set()
```

### 容器操作

#### 通用操作函数
以下函数适用于所有容器类型

`len()`-获取元素个数

`max()/min()`-获取元素最大/最小值

`sum()`-求和(元素必须是数字)

`sorted()`-排序，返回新列表

`reversed()`-反转，返回迭代器

#### 成员运算符 in/not in
判断元素是否存在于容器中

```python
3 in [1,2,3] # True
5 not in [1,2,3] #True

# 字典 -- 检查的是建不是值

"name" in {"name":"larry"} # True
```

#### 连接与重复运算

```python
# + 链接(仅有序容器)

# * 重复(仅有序容器)


```

#### 相等运算符

`==/!=`
比较逻辑：
1. 类型必须相同:不同类型的容器即使看起来一样，也不相同
2. 长度必须相同:长度不同的容器一定不同
3. 逐元素比较:从第一个元素开始，一次比较对应位置的元素
4. 元素使用自身的`==`:容器本身不定义元素如何相等，而是会调用元素自身的`__eq__`方法，因此[1,2] == [1.0,2.0]为True

#### 身份运算符 is/is not
`is`用于判断两个变量是否指向内存中的同一个对象，即他们的地址是否相同

#### 位运算符
`&、|、^、~`

```python
# &交集

# | 并集

# - 差集

# ^ 对称差集

# ~ 按位取反
```

### 遍历容器

#### 基本for循环

python 的for循环是用于遍历可迭代对象的

```python
for item in [1,2,3]:
  print(item)

# 遍历字符串
for ch in "hello":
  print(ch)
```

#### 遍历字典

```python

person = {
  "name":"larry",
  "age":21,
  "city": "南宁"
}

# 遍历键(默认)
for key in person:
  print(key)

# 遍历键值对
for key,value in person.items():
  print(key,value)

# 仅遍历值
for value in person.values():
  print(value)

# 仅遍历键(显示)
for key in person.keys():
  print(key)
```

#### enumerate()函数

遍历容器时，如果需要同时获取索引和值，使用`enumerate()`

```python
fruits = ["苹果","香蕉","橙子"]

for index,furit in enumerate(fruits):
  print(f"{index}:{furit}")


```

#### zip() 函数
并行遍历多个容器，元素按位置一一配对

```python
names = ["larry","bob","charlie"]
ages = [21,30,35]
cities = ["南宁","广州","上海"]

for name,age,city in zip(names,ages,cities):
  print(f"{name}今年{age}岁，住在{city}")
```

