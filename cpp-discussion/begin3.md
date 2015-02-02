# C++與程式邏輯訓練 (1)

<!-- toc -->

## 6. 遞迴方法

> **Quote** "To iterate is human, to recurse divine." -- L. Peter Deutsch
>
>「遞迴只應天上有，凡人應當用迴圈」--P老師

基本上，遞迴就是在同一個函式裡頭經過若干輾轉再次呼叫自己(but with 不同的參數)，就叫做遞迴。如果你去 google search 遞迴，它就會問你說「你要找的是不是遞迴？」

### 6.1 遞迴兩件事

#### 1
遞迴最重要的就是「遞迴關係」和「終止條件」。有了可靠的這兩個東西之後，我們就不用考慮全局，只要關心我們目前關心的部份就好。

#### 2
遞迴方法、數學歸納法、動態規劃其實是一體三面。Keep this in mind.

### 6.2 所有教科書上都有的死板例子

#### [ 練習] 計算階乘

##### 題目敘述
給你一個整數 $$0\le n \le 12$$，請輸出 $$n!$$ 的值。

##### 提示
利用 $$n! = n \times (n-1)!$$ 來解題。初始條件 $$0! = 1$$。

##### 測試輸入
```
3
```

##### 測試輸出
```
6
```

##### 延伸思考
1. 萬一輸入條件的 $$0\le n\le 20$$ 怎麼辦？
2. (!) 萬一輸入條件的 $$0\le n\le 100$$ 怎麼辦？

#### [ 練習] 費事數列

##### 題目敘述
費式數列的定義是 $$F_0 = 0, F_1 = 1, F_{n+2} = F_{n+1} + F_n$$。現在給你一個整數 $$0\le n \le 45$$，請輸出 $$F_n$$ 的值。

##### 測試輸入
```
8
```

##### 測試輸出
```
21
```

##### 延伸思考
1. 萬一輸入條件的 $$0\le n\le 90$$ 怎麼辦？
2. (!)萬一輸入條件的 $$0\le n\le 10^{12}$$，只要輸出前 5 位數，怎麼辦？
3. (!)萬一輸入條件的 $$0\le n\le 10^{12}$$，只要輸出最末 5 位數，怎麼辦？
4. (!)萬一輸入條件改成 $$0\le n\le 10^{100000}$$，但是要輸出 $$F_{F_n}$$ 的最末 5 位數，怎麼辦？
5. (!) [ 習題 6.2.1] [CF 126D - Fibonacci Sums](http://codeforces.com/problemset/problem/126/D)

#### 快速排序法 Quick Sort

這東西就是「分而治之法 Divide and Conquer」的基本應用。

### 6.3 有些教科書會有的死板例子

#### [ 練習] 河內塔問題

##### 題目敘述

你有一疊 $$n$$ 個圓盤(編號由小到大分別是 $$1, 2, \cdots, n$$)，以及三根柱子 $$A, B, C$$。這些圓盤一開始由小到大排好在 $$A$$ 柱上面，如下圖所示。每一次我們可以將某一根柱子上的最上面圓盤，移動到相鄰的柱子上，但是移動後，仍須保證圓盤在每一根柱子上由小到大排列。請你給出一系列如下面格式的指令：`move disk i from A to B`，使得我們可以將所有圓盤從 $$A$$ 柱搬到 $$C$$ 柱。

![](http://yazilimportal.com/wp-content/uploads/2013/08/Tower.Hanoi_.Cropped.jpg)

##### 程式碼範本

```cpp
#include <iostream>
using namespace std;

void hanoi( /* 請定義你想要的參數 parameters */ ) {
    
    /* 請在這邊填上遞迴終止條件 */
    
    /* 請在這邊寫上你的遞迴關係 */
    
    return;
}

int main(void) {
    int n;
    cin >> n;
    
    hanoi( /* 請傳入你想要的引數 arguments */ );
    
    return 0;
}
```

##### 延伸練習

1. [ 習題 6.3.1] [UVa 10017 - The never ending towers of Hanoi](http://uva.onlinejudge.org/external/100/10017.html)
2. (!)[ 習題 6.3.2] [UVa 254 - Towers of Hanoi](http://uva.onlinejudge.org/external/2/254.html)
3. (!)[ 習題 6.3.3] [CF 392B - Towers of Hanoi](http://codeforces.com/problemset/problem/392/B)

#### [ 練習] L形鋪磚問題

#### [ 練習] 求最大公因數

### 6.4 基本上教科書不會提及的例子

#### [ 練習] 摺紙問題

#### [ 練習] 行列式問題

### 6.5 習題







