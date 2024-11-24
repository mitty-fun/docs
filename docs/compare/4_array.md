---
title: 4. 陣列/串列
sidebar_position: 4
---

### Python 函式

:::info 重點比較
- Python、JavaScript 使用 `[]` 表示
- C、C++ 使用 `{}` 表示
- 都使用 `[編號]` 讀取指定資料，編號從 `0` 開始
- C、C++ 創造陣列時要指定長度，並且陣列長度是固定不能再變更
:::

底下是各種語言使用迴圈將資料取出，並計算總和與平均

```py
# highlight-start
arr = [87, 92, 78, 85, 90]
# highlight-end
total = 0

for num in arr:
    total += num

average = total / len(arr)
print(f"總和：{total}")
print(f"平均：{average}")
```

### JavaScript 函式

```js
// highlight-start
let arr = [87, 92, 78, 85, 90];
// highlight-end
let total = 0;

for (let i = 0; i < arr.length; i++) {
    total += arr[i];
}

let average = total / arr.length;
console.log(`總和：${total}`);
console.log(`平均分數：${average}`);
```

### C 函式

```c
#include <stdio.h>

int main() {
    // highlight-start
    int arr[] = {87, 92, 78, 85, 90};
    // highlight-end
    int total = 0, n = sizeof(arr) / sizeof(arr[0]);

    for (int i = 0; i < n; i++) {
        total += arr[i];
    }

    double average = (double)total / n;
    printf("總和：%d\n", total);
    printf("平均分數：%.2f\n", average);

    return 0;
}
```

### C++ 函式

```cpp
#include <iostream>
using namespace std;

int main() {
    // highlight-start
    int arr[] = {87, 92, 78, 85, 90};
    // highlight-end
    int total = 0, n = sizeof(arr) / sizeof(arr[0]);

    for (int i = 0; i < n; i++) {
        total += arr[i];
    }

    double average = static_cast<double>(total) / n;
    cout << "總和：" << total << endl;
    cout << "平均分數：" << average << endl;

    return 0;
}
```