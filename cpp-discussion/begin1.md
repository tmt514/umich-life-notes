# C++與程式邏輯訓練(1)

## 1. 關於程式解題

* 電腦可以幫助計算，但是電腦厲害的不只是幫助你計算。
  * 參考 Wolfram 兄弟的演講：關於「知識的計算」以及如何教孩子數學
  * http://www.ted.com/talks/stephen_wolfram_computing_a_theory_of_everything
  * http://www.ted.com/talks/conrad_wolfram_teaching_kids_real_math_with_computers
* Computation 和 Problem Solving 之間的差別為何?
* 低階語言 vs 高階語言
  * 我手寫我口
  * 在你教電腦如何變聰明之前，電腦是不會變聰明的。
* What is a program?
  * A sequence of explicit instructions
  * 程式 = 演算法 + 資料結構
    * http://en.wikipedia.org/wiki/Algorithms_%2B_Data_Structures_%3D_Programs
  * 題外話：Computer Programming v.s. Mathematical Programming


## 2. 程式的運作

要寫得一手好程式，就必須了解你寫的程式是怎麼被電腦解讀的。

### 高階程式語言

基本上就是在一般人以明確地方式定義每一個計算步驟，所撰寫出的程式。

Q: 什麼是明確的計算步驟？

### 低階程式語言

其實就是與硬體直接相關的語言，例如
[組合語言 (Assembly Code)](http://en.wikipedia.org/wiki/Assembly_language)和機器碼 (Machine Code)

> **Comment** 把程式從高階語言轉換成其他低階語言，或者是機器看得懂的機器語言的程式，叫做<b>編譯器 (Compiler)</b>，現在的編譯器已經做得很好了，所以特別強調「我手寫我口」，可以避免過多不必要自以為的增加效率。

根據不同的機器會定義出不同的組合語言，有些專門的運算單元(CPU)會提供特別的指令集，特化程式的運算能力。例如 GPU、FPU。

> **Note** 把低階語言用高階程式語言來描述的過程叫做<b>抽象化 (Abstraction)</b>，最高境界就是：你看得懂程式在做什麼，但是你不懂程式實際上在做什麼。


## 3. 基本邏輯與計算模型

要回答「明確的」計算步驟是什麼，就要知道電腦到底可以做哪些事。計算機科學之父 [Alan Turing](http://zh.wikipedia.org/wiki/%E8%89%BE%E5%80%AB%C2%B7%E5%9C%96%E9%9D%88) 就以數學角度定義了什麼東西是「可計算的」、以及定義出什麼問題是「可被決定的」問題 (Decision Problem)。有趣的是，在電腦之父 [Von Neumann](http://zh.wikipedia.org/zh-tw/%E7%B4%84%E7%BF%B0%C2%B7%E9%A6%AE%C2%B7%E8%AB%BE%E4%BC%8A%E6%9B%BC) 定義了什麼是電腦以後，大家發現這個 Von Neumann 結構，跟 Turing Machine 結構在計算能力是等價的 (當然這個什麼是「等價」也需要去定義)。

### 記憶體 Memory


