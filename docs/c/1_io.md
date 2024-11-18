---
title: 輸入與輸出
sidebar_position: 1
---

這裡的**輸入與輸出**是使用者與程式之間的**文字**溝通方式。  
輸出就像程式的「嘴巴」，用來發送訊息給使用者。  
輸入則像程式的「耳朵」，用來接收使用者的訊息。  

在 C 語言中：  
- **輸出**使用 `printf` 函式。  
- **輸入**使用 `scanf` 函式。

### 輸出 printf

執行後會在主控台印出文字「你好」。

```c
#include <stdio.h>

int main() {
    printf("你好");
    return 0;
}
```

在程式中我們會用一對單引號包住文字 `"你好"` 來表示字串。

### 輸入 scanf

執行後會在主控台跳出輸入框讓你輸入文字。   
以下程式會接收使用者的輸入，並將結果儲存在變數 `name` 中。  

```c
#include <stdio.h>

int main() {
    char name[50];
    scanf("%s", name);
    return 0;
}
```

### 輸入與輸出

```c
#include <stdio.h>

int main() {
    char name[50];
    printf("請輸入名字: ");
    scanf("%s", name);
    printf("%s你好", name);
    return 0;
}
```

在這裡，`%s` 用於輸出字串，`name` 是要插入的變數。