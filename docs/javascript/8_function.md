---
title: 函式
sidebar_position: 8
---

函式就像工廠裡的加工機器，你可以傳入一些原物料，經過處理後它會返回一個成品。  
例如，你可以設計一個果汁機的函式，傳入水果作為原物料，經過一番加工後，它就會輸出製作好的果汁。

### 定義函數

- 使用 `function` 關鍵字來定義函數
- `function` 後面接的是函數的名稱，例如我們命名為 `juicer`
- 接著加上一對小括號 `()`，括號內可以設計變數來接收輸入的參數
- 然後是函數內的操作邏輯，使用 `return` 關鍵字返回結果。

```javascript
function juicer(fruit) {
  let drink = fruit + "汁";
  return drink;
}
```

### 執行函數

- 呼叫函數時直接寫函數名稱
- 加上一對小括號 `()` 表示執行
- 在括號內放入需要傳遞的資料

```javascript
let a = juicer("香蕉");
let b = juicer("榴蓮");
console.log(a, b); // 輸出：香蕉汁 榴蓮汁
```

### return 返回結果

執行到 `return` 時，函數會返回結果並結束運行。後續的程式碼將不會執行。

```javascript
function sing() {
  console.log("蝴蝶呀蝴蝶");
  console.log("生得真美麗");
  return;
  console.log("頭戴真金絲");
  console.log("身穿花花衣");
}

sing();
```

執行上方 `sing` 函數，由於遇到 `return`，所以後續程式碼未被執行。

### 函數不一定要有參數或返回值

#### 只有返回值的函數

```javascript
function test() {
  return "你好";
}

let r = test();
console.log(r); // 輸出：你好
```

#### 只有參數的函數

```javascript
function test(count) {
  for (let i = 0; i < count; i++) {
    console.log("嗨");
  }
}

test(10); // 輸出 10 次「嗨」
```

#### 沒有參數和返回值的函數

```javascript
function test() {
  console.log("嗨嗨");
}

test(); // 輸出：嗨嗨
```

### 預設參數

設計函數時，如果沒有提供足夠的參數或多傳參數，會導致錯誤或意外結果。

```javascript
function sum(a, b) {
  return a + b;
}

console.log(sum(10, 20)); // 輸出：30
// console.log(sum(10)); // 執行錯誤，因為少傳一個參數
```

使用預設參數可以避免少傳參數時的錯誤。如下所示：

```javascript
function sum(a, b = 10) {
  return a + b;
}

console.log(sum(10, 20)); // 輸出：30
console.log(sum(10));     // 輸出：20
```

### 常見的內建函數

JavaScript 提供了許多內建函數，以下是一些常見的例子：

```javascript
Number("10");         // 將字串轉為數字 10
parseFloat("10.5");   // 將字串轉為浮點數 10.5
String(123);          // 將數值轉為字串 "123"
[10, 20, 30].length;  // 計算陣列的長度，結果是 3
"今天天氣真好！".length; // 計算字串長度，結果是 7
```

### 挑戰練習

撰寫一個函數 `middleValue(a, b, c)`，
接收三個數字 `a`、`b` 和 `c` 作為參數，並返回這三個數字中的中間值。
如果三者相同或任兩個相同，則返回相同的數值。

題目要求：
1. 實作 `middleValue` 函數。
2. 確保函數在以下測試案例中正確執行。

以下是需完成的程式：

```javascript
function middleValue(a, b, c) {
  // 實作邏輯在這裡
}

// 測試範例
console.log(middleValue(5, 2, 8));    // 輸出：5
console.log(middleValue(10, 10, 5));  // 輸出：10
console.log(middleValue(1, 3, 2));    // 輸出：2
console.log(middleValue(7, 7, 7));    // 輸出：7
console.log(middleValue(5, 5, 3));    // 輸出：5
```