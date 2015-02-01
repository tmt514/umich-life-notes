# C++與程式邏輯訓練(1)

## 5. C++ 語法複習

這邊只是很概要地講過我覺得知道一下比較好的東西，所以若需要更全面的語法學習請找參考書～或者是參考網站，例如[這裡](http://openhome.cc/Gossip/CppGossip/)。

### 5.1 變數宣告與計算

#### 宣告一個整數
```
int a;
```

#### 宣告一個(雙倍精確)浮點數
```
double a;
```

#### 計算兩個數的算數平均
````
average = (a + b) / 2.0;
````

看到分號就要喘氣一下，如果憋氣憋太久沒喘的話就不太對了。(Python和Ruby基本上不需要喘氣...，因為會氣喘)

Q: 為什麼要宣告變數？

#### [ 練習] [CF 50A - 放置骨牌](http://codeforces.com/problemset/problem/50/A)

下面是一個錯誤的程式碼，請把空白處(或錯誤處)補齊或修正：

```cpp
#include <iostream>
#include <string>
using namespace std;

int solve(int m, int n) {

    /* 請在這邊填上你的程式碼 */

    return 0; //這個可能是錯誤的
}

int main(void) {
    int m, n;
    cin >> m >> n;
    cout << solve(m, n) << endl;
    return 0;
}
```

### 5.2 條件判斷

簡單來說就是 `if ... else ...` 啦，有誰不會呢？

#### [ 練習] [CF 4A - 分西瓜問題](http://codeforces.com/problemset/problem/4/A)

下面是一個錯誤的程式碼，請把空白處(或錯誤處)補齊或修正：

```cpp
#include <iostream>
#include <string>
using namespace std;

string solve(int w) {

    /* 請在這邊填上你的程式碼 */

    return "NO"; //這個可能是錯誤的
}

int main(void) {
    int w;
    cin >> w;
    cout << solve(w) << endl;
    return 0;
}
```

#### 三元運算子

大絕招（好孩子不要學？）

```cpp
cout << (n == 1 ? "YES" : "NO") << endl;
        ^^^^^^^   ^^^^^   ^^^^
        條件判斷   True    False
```

### 5.3 迴圈

#### For Loops

也沒什麼好說的，就只是 `for (起始條件; 終止條件; 遞增操作) { 迴圈內容 }`

#### While Loops

`while (迴圈條件) { 迴圈內容 }`

#### Do...While

`do { 迴圈內容 } while (繼續條件)`

Visual Basic 會有 Do...Until 這種語句，要非常小心不要混淆...

#### [ 練習] [CF 82A - Double Cola](http://codeforces.com/problemset/problem/82/A)

```cpp
#include <iostream>
#include <string>
using namespace std;

string solve(int n) {
    int result = -1;

    /* 請在這邊填上你的程式碼 */


    if (result == 0) {
        return "Sheldon";
    } else if (result == 1) {
        return "Leonard";
    } else if (result == 2) {
        return "Penny";
    } else if (result == 3) {
        return "Rajesh";
    } else if (result == 4) {
        return "Howard";
    }    
    return "Kakaen"; //這個可能是錯誤的
}

int main(void) {
    int n;
    cin >> n;
    cout << solve(n) << endl;
    return 0;
}
```

> **Danger** 永遠不要用 `goto`。不知道那是什麼的話，最好。

### 5.4 陣列

#### 宣告一個陣列
```cpp
int a[100];
```

#### 宣告一個二維陣列
```cpp
int a[100][100];
```

#### 賦予陣列維度比較有意義的字句
```cpp
#define WIDTH 50
#define HEIGHT 50
int grid[WIDTH][HEIGHT];
```

#### Define macros 其實不太好用，用 Const
```cpp
const int WIDTH = 50, HEIGHT = 50;
int grid[WIDTH][HEIGHT];
```

#### 陣列的初始值

* 如果宣告的是靜態變數，那麼初始值會幫你清成 0。
* 如果宣告的是動態變數，請設定初始值再使用。

```
int a[5] = {};        //[0, 0, 0, 0, 0]
int b[3] = {0, 1, 2}; //[0, 1, 2]
int c[7] = {1, 2, 3}; //[1, 2, 3, 0, 0, 0, 0]
```

### 5.5 函式宣告與呼叫

傳值(call by value)、傳址(call by value of pointer)、傳參考(call by reference) 三者是不同的！請參考[這裡](http://wp.mlab.tw/?p=176)。

* Java 世界萬物都是參考。

### 5.6 習題

#### [ 習題 5.6.1] [CF 110A - Nearly Lucky Number](http://codeforces.com/problemset/problem/110/A)

#### [ 習題 5.6.2] (!) [CF 158B - Taxi](http://codeforces.com/problemset/problem/158/B)

#### [ 習題 5.6.3] [CF 459A - Pashmak and Garden](http://codeforces.com/problemset/problem/459/A)









