---
title : "python: magic methods"
feed : show
date : 02-04-2024
tags: ["python"]
summary: By implementing magic methods, your objects can behave like the built-in types
---

**reference**: fluent python

---

### **magic methods**

- Magic methods or **dunder methods**, allow objects to change behaviour of methods like `len()` or `[]` notation. For example if you declare `⁠__len__`⁠ method of a class, when you use `⁠len(obj)`⁠ of that class, the interpreter will call `⁠__len__`⁠ mehtod you defined in the class.
- They are useful because when you use that class, you don’t have to memorize random method names for standart operations. it’s not ._size_, *.length* or smht, you will know that it’s *len()*
- Special methods are meant to be called by python interpreter, not by you

### **bool represantation**

- Any object can be used in a boolean context, because interpreter uses `⁠bool(obj)`⁠ method and it uses `⁠__bool__`⁠ method ot the obj.
    - `⁠if a_string or 5:`⁠

in this contenxt, python will check `⁠bool(a_string)`⁠ and `⁠bool(5)`⁠

```
- Basically, `bool(x)` calls `x.__bool__()` and uses the result
- By default, user defined classes are truthy, unless `⁠__bool__` ⁠or `⁠__len__`⁠ is implemented.
```

### **why `len()` is not a method?**

- In Python, builtin types (like list) are C structs containing a field called `⁠ob_size`⁠, which contains the element number in the collection. When `⁠len(x)`⁠ is used, instead of calling `⁠x.__len__`⁠, interpreter gets the value of `⁠x.ob_size`⁠, which is much faster than calling a method.
- *“No method is called for the built-in objects of CPython: the length is simply read from a field in a C struct.
Getting the number of items in a collection is a common operation and must work efficiently for such basic and diverse types as str, list, memoryview, and so on.”*

---