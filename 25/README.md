| rank | ▲ | ✰ | vote | url |
|:-:|:-:|:-:|:-:|:-:|
|  25  |  587 | 87 | 877 | [url](http://stackoverflow.com/questions/6470428/catch-multiple-exceptions-in-one-line-except-block) |

***

## 在一行里获取多个异常

我知道这样:

```python
try:
    # 可能错的地方
except:
    # 如果错了执行这里
```

也知道这样:

```python
try:
    # 可能错的地方
except IDontLikeYourFaceException:
    # 给爷笑一个
except YouAreTooShortException:
    # 踩高跷
```

但是我想在两个不同的异常里做同样的事,我能想到的办法:

```python
try:
    # 可能错的地方
except IDontLIkeYouException:
    # 滚
except YouAreBeingMeanException:
    # 滚
```

有什么方法能像下面那样:

```python
try:
    # 可能错的地方
except IDontLIkeYouException, YouAreBeingMeanException:
    # 滚
```

现在下面的代码根本不好使:

```python
try:
    # 可能错的地方
except Exception, e:
    # 滚
```

所以有什么方法可以完成我的要求吗?

***

用括号扩起来:

```python
except (IDontLIkeYouException, YouAreBeingMeanException) as e:
    pass
```

用逗号分割的方法只能在Python2.6和2.7里好使,在Python3中则无效;现在,你应当使用`as`.

