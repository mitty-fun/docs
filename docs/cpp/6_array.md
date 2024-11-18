---
title: 陣列
sidebar_position: 6
---

陣列可以想像成一排置物櫃，每個格子都有一個編號，並且可以存放不同的資料。  
這些格子的編號從 `0` 開始，也就是第一個格子的編號是 `0`，第二個是 `1`，以此類推。

#### 為什麼需要陣列？

假設老師要紀錄班上 40 位學生的成績，並計算平均、最高、最低分數等。  
在不使用陣列的情況下，必須創建 40 個變數來紀錄每位學生的成績。

```cpp
int a = 90;
int b = 85;
int c = 98;
int d = 76;
int e = 83;
...
```

但如果需要紀錄全校 2000 位學生的成績，創建 2000 個變數顯然不現實。這時候就可以使用陣列，只需要一個陣列變數，就能夠輕鬆管理大量數據。

```cpp
int scores[2000] = {90, 85, 98, 76, 83, /* ... */};
```

### 如何創建陣列

陣列使用類型名稱加上大括號 `{}` 來定義，裡面可以放置初始化的資料。

```cpp
#include <string>
using namespace std;

string fruits[] = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
```

### 讀取陣列

陣列的每個元素可以通過編號（即索引）來讀取。注意，索引從 `0` 開始。

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string fruits[] = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
    cout << fruits[0] << endl;  // 橘子
    cout << fruits[1] << endl;  // 蘋果
    cout << fruits[4] << endl;  // 草莓
    // cout << fruits[5] << endl;  // 超出範圍，會引發錯誤
    return 0;
}
```

### 修改陣列

可以直接通過編號來修改陣列中的元素。

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string fruits[] = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
    fruits[2] = "芭樂";  // 修改元素
    cout << fruits[2] << endl;  // 芭樂
    return 0;
}
```

### 新增資料

在 C++ 中，靜態陣列的大小是固定的，因此不能直接新增資料。  
如果需要增加元素，可以使用動態分配或其他容器（如 `vector`）。

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    vector<string> fruits = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
    // 新增元素
    fruits.push_back("鳳梨");
    fruits.push_back("芒果");

    for (const auto &fruit : fruits) {
        cout << fruit << endl;
    }
    return 0;
}
```

### 移除資料

在 C++ 中，可以使用 `vector` 提供的功能來移除資料。

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    vector<string> fruits = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
    
    // 移除蘋果
    fruits[1] = "";  // 設為空字串表示移除
    for (const auto &fruit : fruits) {
        if (!fruit.empty()) {
            cout << fruit << endl;
        }
    }
    return 0;
}
```

### 計算陣列長度

靜態陣列和動態容器的計算方式不同：

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string fruits[] = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
    int length = sizeof(fruits) / sizeof(fruits[0]);
    cout << length << endl;  // 5
    return 0;
}
```

使用 `vector` 時：

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    vector<string> fruits = {"橘子", "蘋果", "香蕉", "芭樂", "草莓"};
    cout << fruits.size() << endl;  // 5
    return 0;
}
```

### 挑戰題 - 找出最陡峭的山頂

```cpp
#include <iostream>
#include <vector>
#include <cmath>
using namespace std;

vector<int> terrain = {
    91, 18, 69, 29, 15, 99, 74, 44, 13, 83, 
    65, 92, 97, 62, 17, 12, 16, 65, 82, 27, 
    29, 16, 54, 71, 30, 66, 70, 20, 86, 40
};

int main() {
    int maxSlope = 0;
    int peakIndex = -1;

    
    cout << "最陡峭的山頂索引: " << peakIndex << endl;
    return 0;
}
```