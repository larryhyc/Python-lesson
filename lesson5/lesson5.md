### lambda表达式

### 基本语法

```python
lambda 参数1,参数2...:表达式
```
```python
# 普通函数
def add(x,y):
  return x + y

# 等价的lambda

add_lambda = lambda x,y:x+y
```

特点
* 只能包含一个表达式，不能写多条语句
* 表达式的计算结果会自动返回
* 通常不命名，即用即走
* 往往是一个纯函数

### 应用场景
使用lambda表达式来调用高阶函数

```python
nums = [1,2,3,4,5]

new_nums = map(lambda x : x*2,nums)
```
#### 一些高阶函数
`map()` --映射

`filter` --过滤

`sorted()` --排序

`max()/min()` --极值

`reduce()` --积累值