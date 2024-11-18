---
title: 輸入與輸出
sidebar_position: 1
---

這裡的**輸入與輸出**是使用者與程式之間的**文字**溝通方式。  
輸出就像程式的「嘴巴」，用來發送訊息給使用者。  
輸入則像程式的「耳朵」，用來接收使用者的訊息。

在 C++ 中： 
- **輸出**使用 `std::cout` 函式
- **輸入**使用 `std::cin` 函式

### 輸出 std::cout

執行後會在主控台印出文字「你好」。

```cpp
#include <iostream>

int main() {
    std::cout << "你好\n";
    return 0;
}
```

注意：`<<` 用來傳遞資料到輸出流，而 `\n` 表示換行。

### 輸入 std::cin

以下程式會接收使用者的輸入，並將結果儲存在變數中。  

```cpp
#include <iostream>

int main() {
    std::string name;
    std::cout << "請輸入名字: ";
    std::cin >> name;
    return 0;
}
```

執行後，程式會等待使用者輸入資料，並將輸入的內容儲存在變數 `name` 中。  

### 輸入與輸出

這段程式會接收使用者輸入的名字，並用名字向我們打招呼。

程式中 `<<` 是輸出流運算子，它不僅用於輸出單一資料類型，  
還能將多個資料類型合併在一起輸出。

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cout << "請輸入名字: "; // 提示使用者輸入
    std::cin >> name; // 接收輸入並儲存到變數 name
    std::cout << name << " 你好！\n"; // 使用輸入的名字進行輸出
    return 0;
}
```

在這裡，`<<` 用於將資料傳送到輸出流，而變數 `name` 是要輸出的內容。