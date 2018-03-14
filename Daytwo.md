## 创建实例时减少内存占用
__slots__ = ["value1","value2","value3","value4"]
但是限制了类的属性数量

**关于 __slots__ 的一个常见误区是它可以作为一个封装工具来防止用户给实例增加新的属性。 尽管使用slots可以达到这样的目的，但是这个并不是它的初衷。 __slots__ 更多的是用来作为一个内存优化工具。**

## 在类中封装属性名
使用双下划线开始会导致访问名称变成其他形式。 比如，在前面的类B中，私有属性会被分别重命名为 _B__private 和 _B__private_method 
继承——这种属性通过继承是无法被覆盖的
```
class B:
  def __private_method(self):
    pass
class C(B):
  def __private_method(self):
    pass
#这不会覆盖前者的private_method，因为实际操作时名称不同 变成 _class__private_method
```

调用父类方法,尤其是已经被覆盖的方法

```
class A:
    def spam(self):
        print('A.spam')

class B(A):
    def spam(self):
        print('B.spam')
        super().spam()  # Call parent spam()
```
super(),并且在多重继承中有重要作用.MRO排序
