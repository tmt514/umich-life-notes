# 輸入與輸出

基本上，在 C/C++ 裡面的輸出入方式有兩種。第一種是使用 scanf/printf 系列的輸出入函式庫，第二種是使用 C++ 才有的 cin/cout 串流物件將資料導入/導出。

## 關於 scanf / printf

基本上只是一個可以接受不同數量參數的 function，若我們上網搜尋這個 function 的原型，它長得像這個樣子：

```
int scanf ( const char * format, ... );
```

第一個參數要傳入一個__格式字串__，然後後面按照順序傳入每一個變數。

## 參考資料

* [cin 與 scanf 的差異到底在哪裡?](http://www.cplusplus.com/forum/beginner/34165/)
