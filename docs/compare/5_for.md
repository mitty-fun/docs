---
title: 5. for 迴圈
sidebar_position: 5
---

:::info 重點比較
- Python 語法結構 `for i in range(開始, 結束, 變化): 要做的事`
- JavaScript、C、C++ 語法結構 `for (初始化; 條件; 變化) { 要做的事 }`
- 都使用 `break` 語法強制結束迴圈
- 都使用 `continue` 語法結束當前的迴圈執行下一個
:::

底下是各種語言使用 `while` 迴圈印出數列 `0, 2, 4, 6, 8`

### Python 函式

```python
for i in range(0, 10, 2):
    print(i)
```

### JavaScript 函式

```javascript
for (let i = 0; i < 10; i += 2) {
    console.log(i);
}
```

### C 函式

```c
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 10; i += 2) {
        cout << i << endl;
    }
    return 0;
}
```

### C++ 函式

```cpp
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i += 2) {
        printf("%d\n", i);
    }
    return 0;
}
```