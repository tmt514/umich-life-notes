## 關於 cin / cout

我們可以把要輸入的東西想像排成一條直線，每一次接收一個我們想要的內容。這樣一個概念叫做「串流」(streaming)，C++ 裡頭的 `<iostream>` 預設的 `std::cin` 以及 `std::cout` 便分別是用作標準輸入與標準輸出的兩個串流物件。所以我們在使用這兩種標準串流的時候要引入 `<iostream>` 這個標頭檔。

### 箭頭的方向

把它想像成串流以後，就可以很簡單地理解 `>>` 跟 `<<` 這兩個運算子重載的用途：若是輸入串流 `istream`，我們就用 `>>` 把東西一個一個拉進來。若為輸出串流 `ostream`，我們就用 `<<` 把東西一個個丟出去。

```c++
std::cin >> a >> b >> c; //先讀 a, 然後讀入 b, 然後讀入 c
std::cout << a + b << b + c << c + a << std::endl; //輸出也是左到右
```

### std::endl

這個就是所謂的「換行」。

### 控制小數點位數

引入 `<iomanip>` 標頭以後就可以使用 `std::setprecision()` 來控制欲輸出的位數。

```c++
std::cout << std::setprecision(5) << value << std::endl;
```

### 控制浮點數的表示法

在 C++ 裡頭通常會很聰明地幫你判斷要怎麼輸出一個浮點數（可能會用科學記號、或者是僅使用小數點的定點表示法）

### 控制欄寬

在 `<iomanip>` 裡頭也有控制輸出字串和數字最小欄寬的方法，使用方法也與設定浮點數位數類似，在輸出的東西之前寫上 `std::setw()`（還可以利用 `std::setfill()` 設定空白處要用什麼字元填滿），然後設定置左或置右（不寫應該是愈設置右）：

```
std::cout << std::setw(10) << std::left << "Test" << endl;
std::cout << std::setw(10) << std::right << "Test" << endl;
```


### 省去 std:: 的程式

可以在宣告函式之前宣告命名空間，這麼一來裡面就不需要額外標註 std 這個 namespace 了。

```c++
using namespace std;
int main() {
  cout << "Hello world!" << endl;
  return 0;
}
```

有的時候很容易撞名，所以若撰寫規模較大的程式，不建議隨意加上 using namespace std; 理由請參考[這幾篇討論](http://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice)。

### 運算子重載 operator overloading

這樣有個方便之處，就是我們可以自定義一個物件的輸入方式（包含輸入與輸出串流），無論是什麼物件就可以直接用想要的方式輸入/輸出了。

舉例而言，我們若有一個叫做平面上座標「點」的類別，我們可以重載它的輸入方式：

```c++
class Point {
    public:
        double x, y;
        friend istream& operator >> (istream& in, Point& p) {
            in >> p.x >> p.y;
            return in;
        }
};
```

這麼一來在輸入的時候就可以直接寫

```c++
Point p;
std::cin >> p;
```

相當方便！