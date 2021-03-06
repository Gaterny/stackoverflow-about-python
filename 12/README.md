| rank | ▲ | ✰ | vote | url |
|:-:|:-:|:-:|:-:|:-:|
|  12  |  851 | 228 | 1287 | [url](http://stackoverflow.com/questions/423379/using-global-variables-in-a-function-other-than-the-one-that-created-them) |

***

## 如何在一个函数里用全局变量?

如果我在一个函数里建了一个全局变量,那么我怎么在另一个函数里使用这个全局变量?

我需要把这个全局变量赋值给这个函数的局部变量吗?

***

如果你要在别的函数里使用全局变量,只要在被调用全局变量函数的里事先用`global`声明一下:

```python
globvar = 0

def set_globvar_to_one():
    global globvar    # 需要用global修饰一下globvar
    globvar = 1

def print_globvar():
    print globvar     # 如果要读globbar的值的话不需要用global修饰

set_globvar_to_one()
print_globvar()       # 输出 1
```

我猜正是因为全局变量比较危险,所以Python为了确保你真的知道它是全局变量,所以需要加一个`global`关键字.
