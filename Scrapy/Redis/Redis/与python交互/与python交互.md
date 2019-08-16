# 与python交互

1. 连接

```python
from redis import StrictRedis

sr = StrictRedis(host='localhost', port=6379, db=0)
```

![1558700529126](与python交互.assets/1558700529126.png)

![1558700542340](与python交互.assets/1558700542340.png)

## 增

- `.sadd(self, name, *values)`——给 name 对应的集合中添加元素

![1563596434191](与python交互.assets/1563596434191.png)

## 查

- `.scard(self, name)`——获取 name 对应的集合中的元素个数

![1563596494200](与python交互.assets/1563596494200.png)

![1563596508070](与python交互.assets/1563596508070.png)

- `.smembers(self, name)`——获取 name 对应的集合的所有成员

![1563596576202](与python交互.assets/1563596576202.png)

![1563596519081](与python交互.assets/1563596519081.png)

- `.sdiff(self, keys, *args)`——在第一个 name 对应的集合中且不在其他 name 对应的集合的元素集合

![1563596903350](与python交互.assets/1563596903350.png)

![1563596912823](与python交互.assets/1563596912823.png)

- `.sismember(self, name, value)`——检查 value 是否是 name 对应的集合内的元素

![1563597299480](与python交互.assets/1563597299480.png)

![1563597307415](与python交互.assets/1563597307415.png)

- `.exists(self, name)`——检查 redis 的 name 是否存在

- `.keys(self, pattern='*')`——根据`*?`等通配符匹配获取 redis 的 name

- `.randomkey(self)`——随机获取一个 redis 的 name（不删除）

- `.type(self, name)`——获取 name 对应值的类型

## 改

- `.smove(self, src, dst, value)`——将某个元素从一个集合中移动到另外一个集合

![1563597596559](与python交互.assets/1563597596559.png)

![1563597605210](与python交互.assets/1563597605210.png)

- `.rename(self, src, dst)`——重命名

- `.move(self, name, db))`——将 redis 的某个 name 移动到指定的 db 下

- 

## 删

- `.spop(self, name)`——从集合的右侧移除一个元素，并将其返回

![1563597740528](与python交互.assets/1563597740528.png)

![1563597747761](与python交互.assets/1563597747761.png)

- `.flushdb(self,asynchronous=False)`——清空当前 db 中的数据,默认是同步。若开启异步 asynchronous=True ，会新起一个线程进行清空操作，不阻塞主线程

- `.flushall(self,asynchronous=False)`——清空所有 db 中的数据，默认是同步。异步同flushdb

- `.delete(self, *names)`——根据 name 删除 redis 中的任意数据类型

