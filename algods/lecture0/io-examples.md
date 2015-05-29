# 輸入與輸出

基本上，在 C/C++ 裡面的輸出入方式有兩種。第一種是使用 scanf/printf 系列的輸出入函式庫，第二種是使用 C++ 才有的 cin/cout 串流物件將資料導入/導出。

## 標準輸入與標準輸出

通常一個程序 (process) 開始執行的時候，作業系統會幫你把鍵盤（視作標準輸入 Standard Input）和螢幕（視作標準輸出 Standard Output）以某些形式連接到你的程序中。在 C 語言裡頭，會以檔案 (File descriptor) 的方式讓你可以存取。若是在 C++ 裡頭則是透過串流 (Standard I/O Streams) 進行輸入/輸出。

![](http://upload.wikimedia.org/wikipedia/commons/thumb/7/70/Stdstreams-notitle.svg/440px-Stdstreams-notitle.svg.png)

(圖片引用自[維基百科](http://en.wikipedia.org/wiki/File:Stdstreams-notitle.svg))

## 學習重點

1. 理解並使用 scanf / printf。
2. 理解並使用 cin / cout。

## 參考資料

* [cin 與 scanf 的差異到底在哪裡?](http://www.cplusplus.com/forum/beginner/34165/)
* [Standard Streams (Wikipedia)](http://en.wikipedia.org/wiki/Standard_streams)
