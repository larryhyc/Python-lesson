### python类和对象

### 定义类
使用 `class` 关键字定义类

```python
class Dog:
  pass

# 创建实例
my_dog = Dog()
```
#### 使用type()动态定义类
类本身也是一个对象，`type()`是创建类的内置函数，可以动态的创建类

```python
# type(类名，(父类元组)，{属性字典})

```

### 构造方法 `__init__`
`__init__`是类的构造方法，在创建对象时自动调用，用于初始化对象的属性

```python
class Dog:
  def __init__(self,name,age):
    self.name = name
    self.age = age

# 创建实例时传入参数
my_dog = Dog("buddy",3)
print(my_dog.name) # buddy
```

### 实例属性
每个独享独立的属性，通过`self`定义

```python
class Dog:
  def __init__(self,name,age):
    self.name = name
    self.age = age


dog1 = Dog("buddy")
dog2 = Dog("max")

```

### 类属性

所有对象共享的属性，在类内部直接定义

```python
class Dog:
  spacies = "Camnis"

  def __init__(self,name):
    self.name = name

dog1 = Dog("buddy")
dog2 = Dog("max")

print(dog1.spacies) # Camnis
print(dog2.spacies) # Camnis


print(dog1.name) # buddy
print(dog2.name) # max
```

访问规则：实例属性通过self访问，类属性通过类名或self访问 

### 实例方法
定义在类中的函数，第一个参数必须时self

```python
class Dog:
  spacies = "Camnis"

  def __init__(self,name):
    self.name = name

  def bark(self):
    print("dog is bark")

dog1 = Dog("buddy")

dog1.bark()
```

### 类方法与静态方法

类方法 `@classmethod`
第一个参数时`cls`,代表类本身，可以访问或修改类属性

```python

class Dog:
  count = 0 # 类属性：记录创建了多少只狗

  def __init__(self,name):
    self.name = name
    Dog.count += 1

  @classmethod
  def get_count(cls):
    return cls.count

dog1 = Dog("buddy")
dog2 = Dog("max")

print(Dog.get_count()) # 2


```

静态方法`@staticmethod`

不接收`self`或`cls`，与普通函数类似，只是定义在类中

```python
class Math:
  @staticmethod
  def add(a,b):
    return a + b

print(Meth.add(3,5))
```

实例成员使用实例调用，类成员使用类调用，静态成员使用类调用

### 继承
子类继承父类的属性和方法，并可以扩展或重写

```python
class Animal:
  pass

# 继承自Animal
class Dog(Animal):
  pass
```

在子类中可以使用`super()`调用父类的方法

```python
class Animal:
  def __init__(self,name):
    self.name = name

# 继承自Animal
class Dog(Animal):
  super().__init__() # 调用Animal的__init__
```

### 多继承
python中支持一个子类同时继承自多个父类

```python
class Flyble:
  pass

class Swim:
  pass

# 同时继承多个父类
class Duck(Flyble,Swim):
  pass
```

### 常见操作
#### 内置属性

|属性|说明|
|--|--|
|__class__|对象所属的类|
|__bases__|类的所有直接父类（元组）|
|__base__|类的第一个直接父类|
|__dict__|对象或类的属性字典|

`type()` --返回地想的类型(对象是通过哪个类创造的)

`isinstance()` --判断对象是否是指定类(或其子类的实例)

`issubclass()` --判断一个类是否是另一个类的子类

`dir()` --返回对象的所有属性和方法列表(包括继承的)

`vars()` --返回对象的 __dict__ 属性,即对象的字典

`getattr()` --获取对象的属性值，属性不存在时返回默认值，会沿着继承链查找属性（包括实例属性、类属性、父类属性）

`setattr()` --设置对象的属性值，属性不存在时会创建。如果父类定义了描述符（如 @property.setter）或__setattr__方法，会遵循继承链上的这些机制

`delattr()` --删除对象属性