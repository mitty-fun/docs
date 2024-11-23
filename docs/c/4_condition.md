---
title: 條件判斷
sidebar_position: 4
---

程式中的條件判斷就像國文課的 `如果 ... 就 ...` 造句。

- **如果**天色變暗，**就**打開車燈。
- **如果**玩家血量歸零，**就**播放慘叫的音效。
- **如果**音樂播放完畢，**就**切換到下一首歌。

轉換成 JavaScript 語法就是把「如果」替換成 `if`，  
把「條件」用 `()` 一對小括號包住，  
把「要做的事情」用 `{}` 一對大括號包住。

- **if** (天色變暗) \{ 打開車燈 \}。
- **if** (玩家血量歸零) \{ 播放慘叫的音效 \}。
- **if** (音樂播放完畢) \{ 切換到下一首歌 \}。

## if 如果

執行底下的程式示範**如果**輸入的成績達到 60 分，**就**印出及格：

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);

    if (score >= 60) {
        printf("及格\n");
    }
    return 0;
}
```

若要在成績不及格時印出「不及格」可以這樣寫：

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);

    if (score >= 60) {
        printf("及格\n");
    }
    if (score < 60) {
        printf("不及格\n");
    }
    return 0;
}
```

## else 否則

程式中的否則條件判斷就像國文課的造句。

- **如果**敵人還活著，**就**發動攻擊，**否則**撿起吊起來的寶物。
- **如果**悠遊卡還有餘額，**就**打開閘門，**否則**發出餘額不足的警告。
- **如果**溫度太高，**就**啟動灑水系統，**否則**打開遮陽板。


延續上一個例子，實際，我們可以使用 `else` 語法來簡化程式碼：

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

## elif 否則如果

如果我們想要讓成績在 50 至 59 之間給予補考，我們可以這樣設計：

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);

    if (score >= 60) {
        printf("你及格了！\n");
    } else {
        if (score >= 50) {
            printf("補考機會！\n");
        } else {
            printf("你不及格！\n");
        }
    }
    return 0;
}
```

我們可以將 `else` 跟裡面的 `if` 合併成 `else if` 否則如果語法：

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);

    if (score >= 60) {
        printf("你及格了！\n");
    } else if (score >= 50) {
        printf("補考機會！\n");
    } else {
        printf("你不及格！\n");
    }
    return 0;
}
```

使用 `elif` 否則如果語法可以減少縮排，讓程式更好閱讀。讓我們來看個例子：

例如，考試分級程式：
- 如果分數高於 90 分，就給 A 級。
- 否則如果分數高於 80 分，就給 B 級。
- 否則如果分數高於 70 分，就給 C 級。
- 否則如果分數高於 60 分，就給 D 級。
- 否則給 E 級。

在只能使用 `if` 跟 `else` 語法下會設計成這樣：

```c
#include <stdio.h>

int main() {
    int score;
    printf("成績：");
    scanf("%d", &score);

    if (score >= 90) {
        printf("A 級\n");
    } else {
        if (score >= 80) {
            printf("B 級\n");
        } else {
            if (score >= 70) {
                printf("C 級\n");
            } else {
                if (score >= 60) {
                    printf("D 級\n");
                } else {
                    printf("E 級\n");
                }
            }
        }
    }
    return 0;
}
```

這種寫法可能會使程式層級過多，導致除錯困難。  
因此，使用 `else if` 語法來簡化結構。

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

這樣的結構不僅簡潔明瞭，還能有效地處理多種條件判斷。

## 實作練習

底下的程式可以輸入 X、Y 座標數值，並根據數值顯示其所在的象限。

但是如果輸入的座標剛好在 X、Y 軸上或是在原點則會錯誤，

因此請修改以下程式，當座標在其他情況時就顯示 `X 軸`、`Y 軸` 或 `原點`。

```c
#include <stdio.h>

int main() {
    int x, y;
    printf("X 座標：");
    scanf("%d", &x);
    printf("Y 座標：");
    scanf("%d", &y);

    if (x > 0) {
        if (y > 0) {
            printf("第一象限\n");
        } else {
            printf("第四象限\n");
        }
    } else {
        if (y > 0) {
            printf("第二象限\n");
        } else {
            printf("第三象限\n");
        }
    }
    return 0;
}
```