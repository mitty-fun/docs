---
title: while 迴圈
sidebar_position: 5
---

迴圈是一種不斷重複執行某段程式碼的結構。  
它與條件判斷相似，都是根據條件是否成立來決定是否執行程式碼。  
不過，迴圈的特點是：當條件成立時，程式碼會不斷重複執行，直到條件不成立為止。

### 條件 vs 迴圈

讓我們用一個例子說明，假設你要設計一個「自動打怪程式」，

它會偵測怪物血量，如果還活著血大於 0 就發動攻擊直到結束。

如果只用一個 `if`，程式只能發動一次攻擊。

```javascript
let life = 100; // 血量
if (life > 0) {
    console.log('攻擊');
    life -= 30;
}
```

如果使用多個 `if`，可以進行多次攻擊，直到怪物死掉。

```javascript
let life = 100; // 血量
if (life > 0) {
    console.log('攻擊');
    life -= 30;
}
if (life > 0) {
    console.log('攻擊');
    life -= 30;
}
if (life > 0) {
    console.log('攻擊');
    life -= 30;
}
if (life > 0) {
    console.log('攻擊');
    life -= 30;
}
```

但如果怪物血量從 100 改成 200 呢？這樣就得增加更多的 `if` 了。  
我們可以改用 `while` 迴圈來改寫它：

```javascript
let life = 100; // 血量
while (life > 0) {
    console.log('攻擊');
    life -= 30;
}
```

`if` 跟 `while` 語法非常相似，都是條件成立就執行對應的程式。  
但差別在 `if` 只會執行一次，而 `while` 會執行完後再重新判斷條件，直到條件不成立。

### 無限迴圈

如果條件永遠成立，就會變成無限迴圈，也就是停不下來的迴圈。

以下是一個無限迴圈的範例，因為條件 `0 < 10` 永遠成立，  
程式會無限次地印出「哈囉」，導致後續的程式無法執行。

這種無法停止的迴圈稱為**無限迴圈**，在程式設計中應該特別避免，  
否則可能會導致程式卡住並癱瘓掉。

```javascript
let i = 0;
while (i < 10) {
    console.log('哈囉！');
}
```

### 有限迴圈

為了避免無限迴圈，我們可以設計一個**計數器**，限制迴圈執行的次數。

以下範例示範了一個有限迴圈，迴圈會執行 10 次，然後停止。

```javascript
let i = 0;
while (i < 10) {
    console.log('哈囉！');
    i += 1;
}
```

### 印出數列

以下程式會印出 0 到 10 的數字。

我們可以透過修改變數 `i` 的起始數值、結束條件和變化方式來改變印出的數列。

```javascript
let i = 0; // 開始
while (i < 10) { // 結束
    console.log(i);
    i += 1; // 變化
}
```

例如，將條件改為 `< 100`，程式會印出 `0, 1, 2, 3, 4, ... 98, 99`。

```javascript
let i = 0;
while (i < 100) {
    console.log(i);
    i += 1;
}
```

再將 `i` 改為 `50`，程式會印出 `50, 51, 52, 53, ... 98, 99`。

```javascript
let i = 50;
while (i < 100) {
    console.log(i);
    i += 1;
}
```

如果再將 `i += 1` 改為 `i += 2`，程式會印出 `50, 52, 54, 56, ... 96, 98`。

```javascript
let i = 50;
while (i < 100) {
    console.log(i);
    i += 2;
}
```

### 實作挑戰

請修改以下程式，印出數列： `100, 97, 94, 91, ... 7, 4, 1`

```javascript
let i = 0;
while (i < 100) {
    console.log(i);
    i += 1;
}
```