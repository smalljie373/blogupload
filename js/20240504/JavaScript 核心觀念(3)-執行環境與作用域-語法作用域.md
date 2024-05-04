### 前言

JavaScript 所採用的是語法作用域，也就是在宣告時就已經決定好他的作用域

## 語法作用域

語法作用域是JavaScript中，很重要的一個觀念，當你在宣告語法時，就已經決定好他的作用域

那麼語法作用域是什麼呢?

所謂的語法作用域就是它實際存在的位置，例如所謂的全域環境及區域環境。

以下是區域環境的範例

```js
function name() {
    var name = 'smalljie'
    console.lgo(name);
};
console.log(name); // name is not defined;
```
當語法宣告的位置是在函式內，外部無法取得在函式內所宣告的變數

當然函式也會受到語法作用域的影響

```js
function sayHi() {
    function name() {
        var name = 'smalljie'
        console.log(name);
    }
};

name() // name is not defined;
```
## 作用域的種類

講到作用域有分為兩種 :

- 靜態作用域（lexical scope），變數的作用域解析時就已經確定，且不會再改變
- 動態作用域（dynamic scope），變數的作用域再呼叫、調用函式時才決定

其中 JavaScript 就屬於靜態作用域，在語法單元化(Tokenizing)、解析時就已經決定作用域

![靜態作用域]()

而動態作用域則是相反，動態作用域只有在函式呼叫的時候才會決定它的作用域

![重點整理]()

採用靜態作用域的程式語言有

- JavaScript
- C/C++
- Python
- C#
- Java ...

相反的，採用動態作用域的程式語言有
- Pascal
- Emacs Lisp ...

由此可知JavaScript是採用靜態作用域，以下是範例程式碼

```js
var value = 1; // 全域變數
function fnA() {
    console.log(value); // 1
};
function fnB() {
    var value = 2; // 區域變數
    fnA();
};
fnB(); 
 ```

 在前面有講到當程式碼運行時，就已經決定了程式碼的作用域，所以在`fnB`中的`value = 2`就只會存活在`fnB`裡，而`var value = 1`是宣告在最外圍的全域變數，所以在`fnA()`才會出現`1`這個結果，另外還有一個重要的點，當「當前作用域沒有這個變數時 JavaScript 將會一層一層向外查找」，而這就是所謂的範圍鍊，這個觀念後面再提

 ### 章節重點
- 靜態作用域（lexical scope），變數的作用域解析時就已經確定，且不會再改變
- 動態作用域（dynamic scope），變數的作用域再呼叫、調用函式時才決定
- 當前作用域沒有這個變數時 JavaScript 將會一層一層向外查找

## 參考文獻

- [JavaScript 核心篇](https://www.hexschool.com/courses/js-core.html)
- [語法作用域(Lexical scope)](https://hackmd.io/@Co-E5uCjTiSXhCaEXduquA/SJDwemE85)
- [執行環境與作用域-語法作用域](https://israynotarray.com/javascript/20200412/2694164006/)