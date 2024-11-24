---
title: 7. 函式
sidebar_position: 7
---

設計一個函式 `add` 可以傳入 2 個參數，並計算總和後回傳結果。  
底下範例使用不同的程式語言實作。

:::info 重點比較
- 執行函式時都是打上函式名稱 `add` 加上一對小括號 `()` 表示執行
- 小括號 `()` 中填入要輸入的資料
- 回傳資料時都會使用 `return` 語法
:::

### Python 函式

```python
def add(a, b):
    c = a + b
    return c

result = add(3, 5)
print(result)
```

### JavaScript 函式

```javascript
function add(a, b) {
  let c = a + b;
  return c;
}

let result = add(3, 5);
console.log(result);
```

### C 函式

```c
#include <stdio.h>

int add(int a, int b) {
    int c = a + b;
    return c;
}

int main() {
    int result = add(3, 5);
    printf("%d\n", result);
    return 0;
}
```

### C++ 函式

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) {
    int c = a + b;
    return c;
}

int main() {
    int result = add(3, 5);
    cout << result << endl;
    return 0;
}
```

### 匿名函式

#### Python 匿名函式

```python
add = lambda a, b: a + b
result = add(3, 5)
print(result)
```

#### JavaScript 匿名語法

```javascript
const add = (a, b) => a + b;
let result = add(3, 5);
console.log(result);
```

#### C++ 匿名語法

```cpp
#include <iostream>
using namespace std;

int main() {
    auto add = [](int a, int b) { return a + b; };
    int result = add(3, 5);
    cout << result << endl;
    return 0;
}
```