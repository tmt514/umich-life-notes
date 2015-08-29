# Lecture 0 - 鏈結串列 Linked Lists

## 課程大綱

1. 抽象資料結構 Abstract Data Type (ADT)
2. 什麼是鏈結串列 (Linked lists)
3. 鏈結串列與陣列的比較
4. 鏈結串列的結構與實作
5. 用陣列模擬鏈結串列
6. 實戰例題 (什麼時候該用鏈結串列？什麼時候該用陣列？)

## 0.1 抽象資料結構 Abstract Data Type (ADT)

* 這東西很深很抽象（能吃嗎？）我們只需要最簡單的就可以了。
* 只定義了介面的 (Functional ADT)
* 只要定義出一系列的「功能」、「輸入」、「輸出」即可。

舉例來說，如果我們需要一個叫做「列表」(List) 的資料結構，我們可以定義以下幾種操作介面：

* $$Append(S, x)$$：在列表 $$S$$ 末端增加一個元素 $$x$$。
* $$Insert(S, x, y)$$：在列表 $$S$$ 之中的 $$y$$ 元素**之前**插入 $$x$$，若 $$y$$ 為空則視同 $$Append$$ 操作。
* $$Remove(S, x)$$：在列表 $$S$$ 刪除 $$x$$ 元素。

## 0.2 什麼是鏈結串列 (Linked lists)

(Picture from Wikipedia)
![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/816px-Singly-linked-list.svg.png)

## 0.3 鏈結串列與陣列的比較

1. 資料長度不固定
2. 資料大小不固定
3. 需要插入或刪除資料於特定位置

## 0.4 單向鏈結串列

```c++
struct Element {
    int data;
    Element *next;
} *head;
```

正所謂「牽一髮而動全身」<s>(是這樣用的嗎)</s>，我們只要記住 `head` 就可以把剩下的所有資料取出來了。

## 0.5 雙向鏈結串列

(Picture from Wikipedia)
![](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Doubly-linked-list.svg/1220px-Doubly-linked-list.svg.png)

```c++
struct Element {
    int data;
    Element *prev, *next;
};
```

## 0.6 其他變種結構

### 環狀鏈結串列

(Picture from Wikipedia)
![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/Circularly-linked-list.svg/700px-Circularly-linked-list.svg.png)

### 利用鏈結串列實作 Stack 與 Queue

我們可以將 Linked List 的 head 當做堆疊最上面的元素，每次「push」只要把 head 墊高就可以了。如果是 Queue 的話我們可以用雙向鏈結串列實作，一樣記錄頭跟尾就可以了。

### 利用陣列實作鏈結串列

### 稀疏矩陣

### 雜湊函數

### 跳躍鏈表

### 塊狀鏈表

## 0.7 實戰例題

### 基本實作題

* 0002 - Merge two arrays
* 0002 - Insertion/Deletion of a doubled linked list
* 0004 - Reverse a single linked list

### 挑戰題

* 0005 - String Pad
* 0006 - Sparse Matrix Multiplication
* 0007 - Hare and Hound's Algorithm

### 思考題

* 給你一個 Linked List，它的末端可能接成一圈，請問這個圈的大小為何、以及第一次進到這個圈的元素為何？
* 給你兩個 Linked List，請判斷它們是否有交集？若有交集，請問第一次碰到的元素為何？