---
title: 6. for 迴圈
---

在學習 `while` 迴圈後我們知道，

一個標準的迴圈通常會有三個要素：`開始`、`條件` 和 `變化`。

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0; // 開始
    while (i < 10) { // 條件
        cout << i << endl; // 變化
        i++;
    }
    return 0;
}
```

在程式設計中，經常需要執行「指定次數」的操作，因此設計 `for` 迴圈的語法。

```
for (初始化; 條件; 變化) {
    // 執行的程式碼
}
```

我們可以把上面的 `while` 迴圈改用 `for` 語法來精簡它：

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 10; i++) {
        cout << i << endl;
    }
    return 0;
}
```

### 印出數列

例如，將條件改為 `< 100`，程式會印出 `0, 1, 2, 3, 4, ... 98, 99`。

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 100; i++) {
        cout << i << endl;
    }
    return 0;
}
```

再將 `i` 改為 `50`，程式會印出 `50, 51, 52, 53, ... 98, 99`。

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 50; i < 100; i++) {  // 起始值：i = 50
        cout << i << endl;
    }
    return 0;
}
```

如果再將 `i += 1` 改為 `i += 2`，程式會印出 `50, 52, 54, 56, ... 96, 98`。

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 50; i < 100; i += 2) {  // 變化：i += 2
        cout << i << endl;
    }
    return 0;
}
```

### 實作挑戰

請將以印出數列 `100, 97, 94, 91, ... 7, 4, 1` 的程式，  
改用 `for` 迴圈語法改寫它：

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 100; i > 0; i -= 3) {  // 起始值：i = 100, 變化：每次減 3
        cout << i << endl;
    }
    return 0;
}
```