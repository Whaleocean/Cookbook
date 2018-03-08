# Cookbook
## 保留最后N个元素
'''
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
'''
## 保留最大N个元素，保留最小N个元素
'''
#headpq模块
import headpq
#headpq.nlargest(maxlen,sequence[,key])
nums = [1, 8, 2, 23, 7, -4, 18, 23, 42, 37, 2]
print(headpq.nlargest(3,nums))#*Prints [42, 37, 23]*
print(headpq.nsmallest(3,nums))#*Prints [-4, 1, 2]*
