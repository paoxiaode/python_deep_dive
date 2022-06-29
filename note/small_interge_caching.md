# small integer cache

Python中整数、浮点数都是immutable，也就是创建以后不能改变内存空间的值，对变量重新赋值以后，相当于变量重新指向了另外一处内存空间。

<img src="..\image\img1.png" style="zoom:40%;">


```python
a = 300
b = 300
a is b //False
a = 200
b = 200
a is b //True
```
CPython 会保存小整数:

Python caches small integers, which are integers between -5 and 256. These numbers are used so frequently that it’s better for performance to already have these objects available. So these integers will be assigned at startup. Then, each time you refer to one, you’ll be referring to an object that already exists.