## 關於 scanf / printf

基本上只是一個可以接受不同數量參數的 function，若我們上網搜尋這個 function 的原型，它們長得像這個樣子：

```c++
int scanf ( const char * format, ... );
int printf ( const char * format, ... );
```

第一個參數要傳入一個__格式字串__，然後後面按照順序傳入每一個變數。有一點點像是「挖洞填空」的輸入方式，根據格式字串之中留下的「洞」從輸入中讀取我們要的資料。

### 基本的格式字串

| 參數 | 意義 | 舉例 | 輸入 | 得到的值 |
| -- | -- | -- | -- | -- | -- |
| `%d` | 整數 | ```scanf("%d", &n);``` | `-3.123abc` | $$n = -3$$ |
| `%lld` (`%I64d`) | 長整數 | ```scanf("%lld", &a);``` | `-3.123abc` | $$a = -3$$ |
| `%f` | 浮點數 | ```scanf("%f", &v);``` | `-3.123abc` | $$v = -3.123$$ |
| `%lf` | 雙倍精確浮點數 | ```scanf("%lf", &v);``` | `-3.123abc` | $$v = -3.123$$ |
| `%s` | 字串(不含空白與換行) | ```scanf("%s", s);``` | `-3.123abc` | $$s =$$ `-3.123abc` |

舉例來說，若我們想要依照以下格式讀入座標 $$(x, y, z)$$，那麼考慮以下程式，我們可以寫成：

```c++
#include <cstdio>

int main(void) {
    int x, y, z;
    scanf("(%d,%d,%d)", &x, &y, &z); //格式輸入
    printf("x = %d, y = %d, z = %d\n", x, y, z); //格式輸出
    return 0;
}
```

#### 輸入範例

```
(1,2,3)
(4,5,6)
(7,8,9)
```

#### 輸出範例

```
x = 1, y = 2, z = 3
```

### ☁ 類似正規表達式的支援

我們可以利用中括弧內放置可接受的字元集來當做篩選：

| 參數 | 意義 |
| -- | -- |
| `%[a-z0-9]` | 只接受小寫英文數字的字串 |
| `%[_A-Za-z0-9]` | 只接受底線、大小寫英數字串 |
| `%[^\n]` | 這個字串接受除了換行字元以外的任意字元 |
| `%[^ABC]` | 除了 A, B, C 這三個字元以外的任意字元(包括換行！) |

### 使用 printf 輸出

如果我們想要輸出固定長度的字串、或者是數字的話，在這裡提供一個常用的方式：透過「欄寬」來進行調整。請參考以下範例：

```c++
printf("----5----5----5\n");
printf("%5d%5d%5d\n", 123, 45, 6789);
```

那麼你的輸出結果將會每五個字元置右對齊：

```
----5----5----5
  123   45 6789
```

如果超過怎麼辦？就會直接撐過去，不會受限於 5 欄的寬度限制。如果想要置左對齊怎麼辦？把寬度設成負的即可。請看另一個範例：

```c++
printf("----5----5----5\n");
printf("%-5d%5d\n", 123, 1234567);
```

輸出結果如下：

```
----5----5----5
123  1234567
```

字串和其他型態的資料輸出也會有類似的效果！

### 整數的補零

```c++
printf("%05d\n", 123);
```

這個輸出會是

```
00123
```

### 浮點數的輸出

我們也可以指定小數點輸出到幾位數。

```c++
double x = 5.1;
printf("----5----5----5\n");
printf("%.3f\n", x);
printf("%10.3f\n", x);
printf("%-10.3f\n", x);
```

這個輸出會是

```
5.100
     5.100
5.100
```

## 關於回傳值

### 取得格式化輸出的長度

printf 的回傳值基本上等於輸出的長度。

### 得知成功輸入的資料數

scanf 的回傳值，如果是 `EOF` 的話代表輸入結束（遇到檔尾）；否則的話會回傳這次呼叫成功讀取了幾項資料。比方說，如果有三個 `%d`，三個整數都成功讀到了，那就會回傳 3。