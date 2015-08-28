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

![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/816px-Singly-linked-list.svg.png)

## 0.3 鏈結串列與陣列的比較

## 0.4 單向鏈結串列

## 0.5 雙向鏈結串列

## 0.6 其他變種結構

## 0.7 實戰例題

### 基本實作題

* 0002 - Insert into a linked list
* 0003 - Delete from a linked list
* 0004 - Insertion/Deletion of a doubled linked list

### 挑戰題

* 0005 - String Pad
* 0006 - Sparse Matrix Multiplication
* 0007 - Hare and Hound's Algorithm