Python Language
===

---
Object Model
---

Phases

- class definition 

- class object 

- metaclass instrumentation 

- instantiation


important attributes

- `cls.__new__(cls)`

- `cls.__init__(self)`


Instantiation Process
```python
new_obj = cls.__new__(cls, *args)
new_obj = cls.__init__(new_obj, *args)
```

---
Operators
---

`obj.__eq__`
`obj.`

---
Decorator
---

```python
@wapper
def func():
  pass
```

equivalent

```python
def func():
  pass
func = wrapper(func)
```

**usages** :

- function registration e.g. Flask
- preprocess and after-process

---
Metaclass
---

---
Context Manager
---
