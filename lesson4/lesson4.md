### python函数

### 定义函数
使用 def 关键字定义函数

```python
def fn():
  print('hello')

fn()
```

### 参数

#### 位置参数
按照定义时的顺序传递参数

```python
def add(a,b):
  return a + b

res = add(3,5)
print(res)
```

#### 默认参数
为参数指定默认值，指定默认值的参数必须要在最后面

```python
def fn(name,greeting="hello"):
  print(f"{greeting},{name}")

fn("larry")
fn("bob","hi")
```

#### 关键字参数
通过参数名传递，顺序可以任意

```python
def fn(name,age,city):

fn(age=25,name="larry",city="南宁")
```

#### 可变参数
`*args`--接收任意数量的参数

```python
def fn(*args):
  tootal = 0
  for num in args:
    total += num
  return total

print(fn(1,2,3))
print(fn(1,3,5,6,7,8))
```
args的本质，函数内部是一个元组

`**kwargs`--接收任意数量的关键字参数

```python
def fn(**kwargs):
  for key,value in kwargs.items():
    print(f"{key}:{value}")
```
kwargs 的本质，函数内部是一个字典

### 文档注释

```python
def fn(a,b):
  """
  计算xxx
  参数：
    a:xxx
    b:xxx

  返回 xxx
  """
  return a + b
```