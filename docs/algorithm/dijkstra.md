---
title: Dijkstra 最短路徑搜尋
sidebar_position: 5
---

科普：https://www.youtube.com/watch?v=Q7xZ162l5ag  
快速了解：https://www.youtube.com/watch?v=_lHSawdgXpI


```python
inf = 100000

matrix = (
  (0, 2, inf, inf, 10),
  (2, 0, 3, inf, inf),
  (inf, 3, 0, 4, inf),
  (inf, inf, 4, 0, 1),
  (10, inf, inf, 1, 0),
)

start = 0
end = 4

points = [-1, -1, -1, -1, -1]
number = [inf, inf, inf, inf, inf]

q = [start]

number[start] = 0

while len(q) > 0:
  x = q.pop()
  for i in range(5):
    y = matrix[x][i] + number[x]

    if y < number[i]:
      points[i] = x
      number[i] = y
      q.append(i)

print(points)
print(number)
```