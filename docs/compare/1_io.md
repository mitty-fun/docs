---
title: 1. 輸入輸出
sidebar_position: 1
---

## 輸入

### python 語法

```py
print('你好')
```

### javascript 語法

```js
console.log('你好');
```

### C 語法

```c
#include <stdio.h>

int main() {
    // highlight-start
    printf("你好\n");
    // highlight-end
    return 0;
}
```

### c++ 語法

```cpp
#include <iostream>
using namespace std;

int main() {
    // highlight-start
    cout << "你好";
    // highlight-end
    return 0;
}
```

## 輸出

### python 語法

```py
input('請輸入名字')
```

### javascript 語法

```js
prompt('請輸入名字');
```

### C 語法

```c
#include <stdio.h>

int main() {
    char name[50];
    printf("請輸入名字: ");
    // highlight-start
    scanf("%s", name);
    // highlight-end
    return 0;
}
```

### c++ 語法

```cpp
#include <iostream>
using namespace std;

int main() {
    string name;
    cout << "請輸入名字: ";
    // highlight-start
    cin >> name;
    // highlight-end
    return 0;
}
```

## 輸入與輸出

### python 語法

```py
print(input('請輸入名字') + '你好')
```

### javascript 語法

```js
console.log(prompt('請輸入名字') + '你好');
```

### C 語法
```c
#include <stdio.h>

int main() {
    char name[50];
    // highlight-start
    printf("請輸入名字: ");
    scanf("%s", name);
    printf("%s你好\n", name);
    // highlight-end
    return 0;
}
```

### c++ 語法

```cpp
#include <iostream>
using namespace std;

int main() {
    string name;
    // highlight-start
    cout << "請輸入名字: ";
    cin >> name;
    cout << name << "你好" << endl;
    // highlight-end
    return 0;
}
```