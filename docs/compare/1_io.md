---
title: 1. 輸入輸出
sidebar_position: 1
---

### 輸入

python 語法：
```python
print('你好')
```

javascript 語法：
```javascript
console.log('你好');
```

c++ 語法：
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "你好" << endl;
    return 0;
}
```

### 輸出

python 語法：
```python
input('請輸入名字')
```

javascript 語法：
```javascript
prompt('請輸入名字');
```

c++ 語法：
```cpp
#include <iostream>
using namespace std;

int main() {
    string name;
    cout << "請輸入名字: ";
    cin >> name;
    return 0;
}
```

### 輸入與輸出

python 語法：
```python
print(input('請輸入名字') + '你好')
```

javascript 語法：
```javascript
console.log(prompt('請輸入名字') + '你好');
```

c++ 語法：
```cpp
#include <iostream>
using namespace std;

int main() {
    string name;
    cout << "請輸入名字: ";
    cin >> name;
    cout << name << "你好" << endl;
    return 0;
}
```