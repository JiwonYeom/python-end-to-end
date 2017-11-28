(ref:https://www.packtpub.com/mapt/book/all_books/9781785888038/1/ch01lvl1sec09/major-aspects-of-object-oriented-programming)
### Encapsulation
* In Python, encapsulation is NOT implicit.
    - no keywords like public, private, protected... etc
    - accessibility can be made private with `_` prefix.

### Polymorhpism
- Provides different implementation depending on input args OR
- Different types of object shares same interface
- Python has this feature as built-in. 
```python
name = 'Jiwon'
tup = (1,2,3,4,5)
lis = [3,4,5,6,7]
print(name[1], tup[2], lis[3])
```

### Inheritance
- Class derives most of its functionality from its parent
- An option to reuse functionality defined in base functionality & allow independent extensions
- create hierarchy via relationship among objects of different classes (Python alllows multiple inheritance)

```python
class Parent:
    def parentM(self):
        print("parent")
class Child(Parent):
    def childM(self):
        print("child")

child = Child()
child.parentM()
```

### Abstraction
```python
"""
Internal details of Adder class are abstracted with add() method
(initialization of self, addtion, etc.)
"""
class Adder:
    def __init__(self):
        self.sum = 0
    def add(self, value):
        self.sum += value

acc = Adder()
for i in range(99):
    acc.add(i)

print(acc.sum)
```

### Composition
```python
class A(object):
    def a1(self):
        print("a1")

class B(object):
    def b(self):
        print("b")
        # class A compositioned under B
        A().a1()

objectB = B()
objectB.b()
```