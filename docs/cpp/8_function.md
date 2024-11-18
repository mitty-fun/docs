---
title: 函式
sidebar_position: 7
---

函式就像工廠裡的加工機器，你可以傳入一些原物料，經過處理後它會返回一個成品。  
例如，你可以設計一個果汁機的函式，傳入水果作為原物料，經過一番加工後，它就會輸出製作好的果汁。

### 定義函式

1. 指定函式的**返回類型**（例如 `int`, `float`, `char*` 等）。
2. 接著是函式的名稱，例如我們命名為 `juicer`。
3. 在函式名稱後加上一對小括號 `()`，括號內可以設計參數以接收輸入。
4. 然後用 `{}` 包住函式內的邏輯。
5. 使用 `return` 語法來返回結果。

```cpp
char* juicer(char fruit[]) {
    static char drink[50];
    strcpy(drink, fruit);
    strcat(drink, "汁");
    return drink;
}
```

### 執行函數

- 呼叫函數時直接寫函數名稱
- 加上一對小括號 `()` 表示執行
- 在括號內放入需要傳遞的資料


```cpp
#include <iostream>
#include <cstring>
using namespace std;

char* juicer(char fruit[]) {
    static char drink[50];
    strcpy(drink, fruit);
    strcat(drink, "汁");
    return drink;
}

int main() {
    cout << juicer("香蕉") << endl;  // 輸出：香蕉汁
    cout << juicer("榴蓮") << endl;  // 輸出：榴蓮汁
    return 0;
}
```

### return 返回值

執行到 `return` 時，函數會返回結果並結束運行。後續的程式碼將不會執行。

```cpp
#include <iostream>
using namespace std;

void sing() {
    cout << "蝴蝶呀蝴蝶" << endl;
    cout << "生得真美麗" << endl;
    return;
    cout << "頭戴真金絲" << endl;
    cout << "身穿花花衣" << endl;
}

int main() {
    sing();
    return 0;
}
```

執行上方 `sing` 函數，由於遇到 `return`，所以後續程式碼未被執行。

### 函式不一定要有參數或返回值

#### 只有返回值的函式

```cpp
#include <iostream>
using namespace std;

int test() {
    return 42;
}

int main() {
    int result = test();
    cout << result << endl;  // 輸出：42
    return 0;
}
```

#### 只有參數的函式

```cpp
#include <iostream>
using namespace std;

void test(int count) {
    for (int i = 0; i < count; i++) {
        cout << "嗨" << endl;
    }
}

int main() {
    test(10);  // 輸出 10 次「嗨」
    return 0;
}
```

#### 沒有參數和返回值的函式

```cpp
#include <iostream>
using namespace std;

void test() {
    cout << "嗨嗨" << endl;
}

int main() {
    test();  // 輸出：嗨嗨
    return 0;
}
```

### 挑戰練習

撰寫一個函式 `middle_value`，接收三個整數 `a`, `b`, 和 `c`，並返回這三個數中的中間值。  
如果三者相同或任兩個相同，則返回相同的數值。

**挑戰目標：**
1. 實作 `middle_value` 函式。
2. 確保以下測試案例中執行正確。

以下是需完成的程式範例：

```cpp
#include <iostream>
using namespace std;

int middle_value(int a, int b, int c) {
    if ((a >= b && a <= c) || (a <= b && a >= c)) {
        return a;
    }
    if ((b >= a && b <= c) || (b <= a && b >= c)) {
        return b;
    }
    return c;
}

int main() {
    cout << middle_value(5, 2, 8) << endl;   // 輸出：5
    cout << middle_value(10, 10, 5) << endl; // 輸出：10
    cout << middle_value(1, 3, 2) << endl;   // 輸出：2
    cout << middle_value(7, 7, 7) << endl;   // 輸出：7
    cout << middle_value(5, 5, 3) << endl;   // 輸出：5
    return 0;
}
```