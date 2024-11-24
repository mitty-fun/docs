---
title: 2. 條件判斷
sidebar_position: 2
---

## if 語法

如果分數大於等於 60 分及格，以下是各種語言的實作

### python 語法

```python
score = int(input())
if score >= 60:
    print('及格')
```

### javascript 語法

```javascript
let score = Number(prompt())
if (score >= 60) {
    console.log('及格');
}
```

### C 語法

```cpp
#include <stdio.h>

int main() {
    int score;
    scanf("%d", &score);
    if (score >= 60) {
        printf("及格\n");
    }
    return 0;
}
```

### C++ 語法

```cpp
#include <iostream>
using namespace std;

int main() {
    int score;
    cin >> score;
    if (score >= 60) {
        cout << "及格\n";
    }
    return 0;
}
```

## else 語法

根據輸入的成績，判斷是否及格。以下是三種語言的程式語法：

### python 語法

```python
score = int(input('成績：'))
if score >= 60:
    print('你及格了！')
else:
    print('你不及格！')
```

### javascript 語法

```javascript
let score = prompt('成績：');
if (score >= 60) {
    console.log('你及格了！');
} else {
    console.log('你不及格！');
}
```

### C 語法

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);
    if (score >= 60) {
        printf("你及格了！\n");
    } else {
        printf("你不及格！\n");
    }
    return 0;
}
```

### C++ 語法

```cpp
#include <iostream>
using namespace std;

int main() {
    int score;
    cout << "成績：";
    cin >> score;
    if (score >= 60) {
        cout << "你及格了！\n";
    } else {
        cout << "你不及格！\n";
    }
    return 0;
}
```

## else if 語法

根據輸入的成績，判斷對應的等級。以下是三種語言的程式語法：

### python 語法

```python
score = int(input('成績：'))

if score >= 90:
    print('A 級')
elif score >= 80:
    print('B 級')
elif score >= 70:
    print('C 級')
elif score >= 60:
    print('D 級')
else:
    print('E 級')
```

### javascript 語法

```javascript
let score = prompt('成績：');

if (score >= 90) {
    console.log('A 級');
} else if (score >= 80) {
    console.log('B 級');
} else if (score >= 70) {
    console.log('C 級');
} else if (score >= 60) {
    console.log('D 級');
} else {
    console.log('E 級');
}
```

### C 語法

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);

    if (score >= 90) {
        printf("A 級\n");
    } else if (score >= 80) {
        printf("B 級\n");
    } else if (score >= 70) {
        printf("C 級\n");
    } else if (score >= 60) {
        printf("D 級\n");
    } else {
        printf("E 級\n");
    }
    return 0;
}
```

### C++ 語法

```cpp
#include <iostream>
using namespace std;

int main() {
    int score;
    cout << "成績：";
    cin >> score;

    if (score >= 90) {
        cout << "A 級\n";
    } else if (score >= 80) {
        cout << "B 級\n";
    } else if (score >= 70) {
        cout << "C 級\n";
    } else if (score >= 60) {
        cout << "D 級\n";
    } else {
        cout << "E 級\n";
    }
    return 0;
}
```