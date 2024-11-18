---
title: 3. 資料型態
---

**資料型態**是程式中用來描述變數或資料的種類。在 C++ 中，不同的資料型態用於表示不同的數值或內容，並決定資料的儲存方式與操作方式。

---

### 基本資料型態

C++ 的基本資料型態如下：

| 型態       | 範例                      | 說明                       |
|------------|---------------------------|----------------------------|
| `int`      | `1`, `2`, `10`, `-20`     | 整數類型，不帶小數點的數值    |
| `float`    | `0.1`, `1.0`, `-10.5`     | 浮點數類型，帶有小數點的數值    |
| `char`     | `'A'`, `'b'`, `'3'`       | 單一字元，使用單引號包裹       |
| `double`   | `0.123456`, `-1234.56`    | 雙精度浮點數，精度比 `float` 高 |
| `bool`     | `false`, `true`           | 布林值，表示 `false` 和 `true`|

---

### 輸出資料型態

C++ 使用 `std::cout` 來輸出資料，對應的格式化符號如下：

| 型態    | 格式化符號 | 範例                          |
|---------|------------|-------------------------------|
| `int`   | `%d`       | `printf("%d", 10);`           |
| `float` | `%f`       | `printf("%f", 1.23);`         |
| `char`  | `%c`       | `printf("%c", 'A');`          |
| `double`| `%lf`      | `printf("%lf", 0.123456);`    |
| `bool`  | `%d`       | `printf("%d", 1);`            |

範例：

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    float b = 3.14;
    char c = 'X';
    bool d = true;

    cout << "整數：" << a << endl;
    cout << "浮點數：" << b << endl;
    cout << "字元：" << c << endl;
    cout << "布林值：" << d << endl;

    return 0;
}
```

執行結果：
```
整數：10
浮點數：3.14
字元：X
布林值：1
```

---

### 輸入資料型態

C++ 使用 `std::cin` 接收輸入，對應的格式化符號如下：

| 型態    | 格式化符號 | 範例                        |
|---------|------------|-----------------------------|
| `int`   | `%d`       | `scanf("%d", &變數);`         |
| `float` | `%f`       | `scanf("%f", &變數);`         |
| `char`  | ` %c`      | `scanf(" %c", &變數);`        |
| `double`| `%lf`      | `scanf("%lf", &變數);`        |

範例：

```cpp
#include <iostream>
using namespace std;

int main() {
    int a;
    float b;
    char c;

    cout << "輸入一個整數：";
    cin >> a;

    cout << "輸入一個浮點數：";
    cin >> b;

    cout << "輸入一個字元：";
    cin >> c;

    cout << "您輸入的整數是：" << a << endl;
    cout << "您輸入的浮點數是：" << b << endl;
    cout << "您輸入的字元是：" << c << endl;

    return 0;
}
```

---

### 型態之間的轉換

C++ 語言允許型態轉換，分為**隱式轉換**與**顯式轉換**：

#### 隱式轉換

當不同型態的資料進行運算時，C++ 會自動將它們轉換為相容的型態，例如：

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    float b = 3.14;
    float c = a + b; // a 被自動轉換為 float
    cout << c << endl; // 輸出 13.140000
    return 0;
}
```

#### 顯式轉換（強制轉型）

使用 `(型態)` 來強制轉換資料型態，例如：

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    int b = 3;
    float c = (float)a / b; // 將 a 強制轉換為 float
    cout << c << endl; // 輸出 3.333333
    return 0;
}
```

---

### 挑戰練習

設計一個程式，接收民國年份，將其轉換為西元年份並印出結果。

以下程式有一個錯誤，請修正它：

```cpp
#include <iostream>
using namespace std;

int main() {
    int year;
    cout << "輸入民國年：";
    cin >> year;

    cout << "西元年為：" << year + "1911" << endl; // 錯誤：應該將字串改為數字
    return 0;
}
```

修正後的程式應該是：

```cpp
#include <iostream>
using namespace std;

int main() {
    int year;
    cout << "輸入民國年：";
    cin >> year;

    cout << "西元年為：" << year + 1911 << endl; // 正確：將 1911 以數字形式加上
    return 0;
}
```