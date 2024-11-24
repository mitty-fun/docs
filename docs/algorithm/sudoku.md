---
title: 數獨遊戲破解
sidebar_position: 3
---

遞迴在許多程式設計問題中非常有用，特別是需要分解成多個子問題的情況。
例如樹結構遍尋、分治演算法、路徑搜尋、動態規劃等。

接下來我們就用數獨遊戲來做練習挑戰，
我們要使用遞回技巧來解數獨問題。

```python
grid = [
    [0, 0, 0, 0],
    [0, 0, 1, 0],
    [0, 4, 0, 0],
    [0, 1, 0, 2]
]

def get_valid(y, x):
    h = grid[y] #水平
    v = [row[x] for row in grid] #垂直
    b = [] #區塊
    
    cy = (y // 2) * 2
    cx = (x // 2) * 2
    for xx in range(cx, cx + 2):
        for yy in range(cy, cy + 2):
            b.append(grid[yy][xx])
    
    all = h + v + b
    result = []
    for i in range(1, 5):
        if i not in all: result.append(i)

    return result

# 解一個格子的數字
# 成功解開就回傳 True
# 無法解開就回傳 False
def solve(grid):
    for y in range(4):
        for x in range(4):
            if grid[y][x] == 0:
                # 找出 y, x 個字有什麼數字可以解
                # 依序嘗試
                # # 並解下一個格子
                # # 如果下一個格子成功就回傳 True
                # 都嘗試過且不行就回傳 False
                
    return True #成功解開這個格子


print(*grid, sep="\n")
```

### 世紀難題
完成後挑戰改成 9 * 9 並破解史上最難的數獨題
https://www.ettoday.net/news/20120630/68551.htm

```python
grid = [
    [8, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 0, 3, 6, 0, 0, 0, 0, 0],
    [0, 7, 0, 0, 9, 0, 2, 0, 0],
    [0, 5, 0, 0, 0, 7, 0, 0, 0],
    [0, 0, 0, 0, 4, 5, 7, 0, 0],
    [0, 0, 0, 1, 0, 0, 0, 3, 0],
    [0, 0, 1, 0, 0, 0, 0, 6, 8],
    [0, 0, 8, 5, 0, 0, 0, 1, 0],
    [0, 9, 0, 0, 0, 0, 4, 0, 0],
]
```

### 數獨產生器
完成後挑戰改成數獨產生器

1. 找到一個空格
2. 產生可以填入的數字，並隨機填入一個
3. 檢查是否合法填入，不行就擦掉填下一個
4. 如果全部都不行就退回上一層遞回
5. 可以就執行遞回尋找下一個空格
6. 產生解答後先將解答印出