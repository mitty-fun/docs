---
title: 輸入與輸出
sidebar_position: 1
---

這裡的**輸入與輸出**是使用者與程式之間的**文字**溝通方式。  
輸出就像程式的「嘴巴」，用來發送訊息給使用者。  
輸入則像程式的「耳朵」，用來接收使用者的訊息。

在 Python 中
- **輸出**使用 `print` 函式
- **輸入**使用 `input` 函式

### 輸出 print

執行後會在主控台印出文字「你好」。

```python
print('你好')
```

在程式中我們會用一對單引號包住文字 `'你好'` 來表示字串。

### 輸入 input

執行後會在主控台跳出輸入框讓你輸入文字。

```python
input('請輸入名字')
```

### 字串合併

執行這段程式會印出 `王大明你好`。

```python
print('王大明' + '你好')
```

在 Python 中我們可以使用 `+` 將兩段文字串起來。

### 輸出與輸出

現在我們把 `王大明` 取代成 `input('請輸入名字')`  
電腦就接收到我們輸入名字，並用名字向我們打招呼。

```python
print(input('請輸入名字') + '你好')
```