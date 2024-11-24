---
title: 3. 條件判斷
sidebar_position: 3
---

## if 語法

:::info 重點比較
- Python、JavaScript 使用 `if` 表示
- C、C++、JavaScript 使用 `{}` 表示範圍
- Pyrhon 使用 `:` 並縮排表示範圍
- 如果要執行的程式只有一行，可以省略 `{}` 大括號
:::

如果分數大於等於 60 分及格，以下是各種語言的實作

### python 語法

```python
score = int(input())
# highlight-start
if score >= 60:
# highlight-end
    print('及格')
```

### javascript 語法

```javascript
let score = Number(prompt())
// highlight-start
if (score >= 60) {
// highlight-end
    console.log('及格');
// highlight-start
}
// highlight-end
```

### C 語法

```cpp
#include <stdio.h>

int main() {
    int score;
    scanf("%d", &score);
    // highlight-start
    if (score >= 60) {
    // highlight-end
        printf("及格\n");
    // highlight-start
    }
    // highlight-end
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
    // highlight-start
    if (score >= 60) {
    // highlight-end
        cout << "及格\n";
    // highlight-start
    }
    // highlight-end
    return 0;
}
```

## else 語法

根據輸入的成績，判斷是否及格。以下是三種語言的程式語法：

### python 語法

```python
score = int(input('成績：'))
# highlight-start
if score >= 60:
# highlight-end
    print('你及格了！')
# highlight-start
else:
# highlight-end
    print('你不及格！')
```

### javascript 語法

```javascript
let score = prompt('成績：');
// highlight-start
if (score >= 60) {
// highlight-end
    console.log('你及格了！');
// highlight-start
} else {
// highlight-end
    console.log('你不及格！');
// highlight-start
}
// highlight-end
```

### C 語法

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);
    // highlight-start
    if (score >= 60) {
        // highlight-end
        printf("你及格了！\n");
        // highlight-start
    } else {
        // highlight-end
        printf("你不及格！\n");
        // highlight-start
    }
    // highlight-end
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
    // highlight-start
    if (score >= 60) {
        // highlight-end
        cout << "你及格了！\n";
        // highlight-start
    } else {
        // highlight-end
        cout << "你不及格！\n";
        // highlight-start
    }
    // highlight-end
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