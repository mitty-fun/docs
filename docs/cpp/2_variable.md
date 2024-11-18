---
title: 2. 變數
---

在 C++ 中，**變數就像一個容器**，用來幫助電腦**儲存資料**！  
我們可以使用變數來記住程式執行中需要的資訊，並在之後使用。

假設我們要取得使用者輸入的名字，  
並打招呼然後告白說「我愛你」，  
我們可能會直接使用兩次 `std::cin` 來獲取使用者的輸入：  

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name1;
    std::string name2;
    std::cin >> name1;
    std::cout << name1 << " 你好！\n";
    std::cin >> name2;
    std::cout << name2 << " 我愛你\n";
    return 0;
}
```

這樣執行時，程式會詢問兩次名字，  
表示電腦並沒有**記住**輸入的名字。

---

### 使用變數來記住名字

我們可以使用一個**變數**來儲存名字，  
只需詢問一次名字，然後多次使用這個變數：

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name; // 宣告一個變數 name，儲存使用者的名字
    std::cin >> name; // 從使用者那裡獲取名字
    std::cout << name << " 你好！\n";
    std::cout << name << " 我愛你\n";
    return 0;
}
```

這樣，程式執行時只需要詢問一次名字，電腦就記住了！

---

### 變數的宣告與賦值

在 C++ 中，所有變數在使用前都需要先**宣告**，  
也就是告訴電腦變數的**名稱**和**型別**。  

以下是一些基本的變數型別：
- `int`：儲存整數
- `float`：儲存小數
- `char`：儲存單一字元
- `std::string`：儲存字串（C++ 提供的字串類型，取代 C 的字元陣列）

#### 賦值運算

變數宣告後，我們可以用等號 `=` 給變數賦值。

```cpp
#include <iostream>

int main() {
    int a = 10; // 宣告整數變數 a 並賦值為 10
    std::cout << a << '\n'; // 印出變數 a 的值
    a = 20; // 更新變數 a 的值為 20
    std::cout << a << '\n'; // 再次印出變數 a 的值
    return 0;
}
```

在 C++ 中，字串可以使用 `std::string` 來儲存，  
並用 `std::cin` 或 `=` 來賦值。

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cin >> name; // 從輸入中獲取名字
    std::cout << "Hello, " << name << "!\n"; // 印出打招呼訊息
    return 0;
}
```

---

### 變數命名規則

1. 名稱只能由字母、數字、底線組成，不能包含空白或其他符號。
2. 名稱的第一個字元必須是字母或底線，不能是數字。
3. 大小寫視為不同變數，例如 `Apple` 和 `apple` 是兩個不同的變數名稱。
4. 名稱不能與保留字（例如 `int`、`if`、`return` 等）衝突。

以下程式會出錯，因為 `int` 是保留字，不能用作變數名稱：

```cpp
#include <iostream>

int main() {
    int int = 10; // 這裡會出錯
    std::cout << int << '\n';
    return 0;
}
```