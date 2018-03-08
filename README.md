# Cookbook
## 保留最后N个元素
```
**Returns a new deque object initialized left-to-right (using append()) with data from iterable. *If iterable is not specified, the new deque is empty*.**
#deque(maxlen = N) 构建一个固定大小的队列 deque 双端队列
#在文件中搜索一个包含pattern的line，并且显示前五行
for collection import deque
def search(lines,pattern,history = 5):
  previous_lines = deque(maxlen = history)
  for line in lines:
    if line == pattern:
      yeild line,previous_lines
      previous_lines.append(line)

with open(r'...../.../../test.txt') as f:
  for line,previouslines in research(f,pattern,history = 5):
    for prline in previouslines:
      print(prline,end = '')
     print(line,end = '')
     print('-' * 20)
#在队列两端插入或删除元素时间复杂度都是 O(1) ，区别于列表，在列表的开头插入或删除元素的时间复杂度为 O(N) deque - 双端队列
```
## 保留最大N个元素，保留最小N个元素
```
#headpq模块
import headpq
#headpq.nlargest(maxlen,sequence[,key])
nums = [1, 8, 2, 23, 7, -4, 18, 23, 42, 37, 2]
print(headpq.nlargest(3,nums))#*Prints [42, 37, 23]*
print(headpq.nsmallest(3,nums))#*Prints [-4, 1, 2]*
#key 可以作用在sequence里，以处理复杂的数据结构
portfolio = [
    {'name': 'IBM', 'shares': 100, 'price': 91.1},
    {'name': 'AAPL', 'shares': 50, 'price': 543.22},
    {'name': 'FB', 'shares': 200, 'price': 21.09},
    {'name': 'HPQ', 'shares': 35, 'price': 31.75},
    {'name': 'YHOO', 'shares': 45, 'price': 16.35},
    {'name': 'ACME', 'shares': 75, 'price': 115.65}
]
print(headpq.nsmallest(3,portfolio,key = lambda x: x['price]))
#如果你想在一个集合中查找最小或最大的 N 个元素，并且 N 小于集合元素数量，那么这些函数提供了很好的性能。 因为在底层实现里面，首先会先将集合数据进行堆排序后放入一个列表中
```
