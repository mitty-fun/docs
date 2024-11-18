---
title: while 迴圈
sidebar_position: 5
---

迴圈是一種不斷重複執行某段程式碼的結構。  
它與條件判斷相似，都是根據條件是否成立來決定是否執行程式碼。  
不過，迴圈的特點是：當條件成立時，程式碼會不斷重複執行，直到條件不成立為止。

### 條件 vs 迴圈

讓我們用一個例子說明，假設你要設計一個「自動打怪程式」，  
它會偵測怪物血量，如果怪物還活著，血量大於 0，就會繼續攻擊直到怪物死亡。

如果只用一個 `if` 只會發動一次攻擊，然後程式就結束了：

```cpp
#include <iostream>
using namespace std;

int main() {
    int life = 100; // 血量
    if (life > 0) {
        cout << "攻擊" << endl;
        life -= 30;
    }
    return 0;
}
```

如果改用四個 `if`，則可以剛好將怪物殺死：

```cpp
#include <iostream>
using namespace std;

int main() {
    int life = 100; // 血量
    if (life > 0) {
        cout << "攻擊" << endl;
        life -= 30;
    }
    if (life > 0) {
        cout << "攻擊" << endl;
        life -= 30;
    }
    if (life > 0) {
        cout << "攻擊" << endl;
        life -= 30;
    }
    if (life > 0) {
        cout << "攻擊" << endl;
        life -= 30;
    }
    return 0;
}
```

但如果怪物血量從 100 改成 200 呢？這樣就得增加更多的 `if` 了。  
我們可以改用 `while` 迴圈來改寫它：

```cpp
#include <iostream>
using namespace std;

int main() {
    int life = 100; // 血量
    while (life > 0) {
        cout << "攻擊" << endl;
        life -= 30;
    }
    return 0;
}
```

`if` 跟 `while` 語法非常相似，都是條件成立就執行對應的程式。  
但差別在 `if` 只會執行一次，而 `while` 會執行完後再重新判斷條件，直到條件不成立。

### 無限迴圈

如果條件永遠成立，就會變成無限迴圈，也就是停不下來的迴圈。

以下是一個無限迴圈的範例，因為條件 `0 < 10` 永遠成立，  
程式會無限次地印出「哈囉」，導致後續的程式無法執行。

這種無法停止的迴圈稱為**無限迴圈**，在程式設計中應該特別避免，  
否則可能會導致程式卡住並癱瘓掉。

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 10) {
        cout << "哈囉！" << endl;
    }
    return 0;
}
```

### 有限迴圈

為了避免無限迴圈，我們可以設計一個**計數器**，限制迴圈執行的次數。

以下範例示範了一個有限迴圈，迴圈會執行 10 次，然後停止。

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 10) {
        cout << "哈囉！" << endl;
        i = i + 1; // 計數器，避免無限迴圈
    }
    return 0;
}
```

### 印出數列

以下程式會印出 0 到 10 的數字數列。

我們可以透過修改變數 `i` 起始數值、條件數值和變化來改變印出的數列。

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0; // 開始
    while (i < 10) { // 結束
        cout << i << endl;
        i = i + 1; // 變化
    }
    return 0;
}
```

例如我們只把條件改為 `< 100`，  
以下程式會印出 `0, 1, 2, 3, 4, ... 98, 99` 數列：

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 100) {
        cout << i << endl;
        i = i + 1;
    }
    return 0;
}
```

例如我們再把 `i` 改為 `50`，  
以下程式會印出 `50, 51, 52, 53, ... 98, 99` 數列：

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 50;
    while (i < 100) {
        cout << i << endl;
        i = i + 1;
    }
    return 0;
}
```

例如我們再把 `i = i + 1` 改為 `i = i + 2`，  
以下程式會印出 `50, 52, 54, 56, ... 96, 98` 數列：

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 50;
    while (i < 100) {
        cout << i << endl;
        i = i + 2;
    }
    return 0;
}
```

### 實作挑戰

請修改以下程式，  
改印出以下數列： `100, 97, 94, 91, ... 7, 4, 1`

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    while (i < 100) {
        cout << i << endl;
        i = i + 1;
    }
    return 0;
}
```