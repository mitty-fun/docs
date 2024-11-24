---
title: 5. while 迴圈
sidebar_position: 5
---

:::info 重點比較
- 迴圈都使用 `while` 語法
- `while` 語法後是條件，當條件成立迴圈就會不斷執行
- 都使用 `break` 語法強制結束迴圈
- 都使用 `continue` 語法結束當前的迴圈執行下一個
- 除了 Python 外都可以使用 `i++` 語法替代 `i += 1`
:::

底下是各種語言使用 `while` 迴圈印出數列 `0, 1, 2, 3, 4, 5, 6, 7, 8, 9`

### Python 函式

Python 使用簡單且直觀的語法來設置 `while` 迴圈。  
每次迴圈結束時，`i` 都會增加 `1`，直到 `i` 不再小於 `10`。

```python
i = 0
while i < 10:
    print(i)
    i += 1
```

### JavaScript 函式

在 JavaScript 中，`while` 迴圈的語法結構與 Python 類似。  
`let` 用來聲明變數 `i`，並且可以使用 `i++` 用來增加 `1`。

```javascript
let i = 0;
while (i < 10) {
    console.log(i);
    i++;
}
```

### C 函式

在 C 中，使用 `printf` 來輸出變數 `i` 的值。
變數 `i` 被定義為 `int`，並且透過 `i++` 增加其值。

```c
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 10) {
        cout << i << endl;
        i++;
    }
    return 0;
}
```

### C++ 函式

在 C++ 中使用 `cout` 來輸出結果。  
變數 `i` 被聲明為 `int`，並可以使用 `i++` 來增值。

```cpp
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 10) {
        printf("%d\n", i);
        i++;
    }
    return 0;
}
```