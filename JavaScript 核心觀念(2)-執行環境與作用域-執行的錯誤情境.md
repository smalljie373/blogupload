### 前言

此篇章是要來介紹在JavaScript中會出現的LHS, RHS，這兩個名詞主要與取值及賦值有關。

## LHS

LHS，全名為Left-Hand Side

Left-Hand Side的意思是用來`賦予值`到左側的變數上，如範例
`var name = 'smalljie'`，將字串賦予到變數`name`上。

那什麼時候會發生LHS錯誤，簡單來說，當你賦予的值是JavaScript不正確時就會發生，例如以下字串賦予值的作法就會引發錯誤

```js
'smalljie' = 1;
```

您只需要在瀏覽器的Console頁面輸入上述錯誤的程式碼，便會出現`SyntaxError: invalid assignment left-hand side debugger eval code:1`

使用前一篇所提到的[esprima](https://esprima.org/demo/parse.html)，輸入錯誤的程式碼也會出現相關的錯誤訊息

在這邊還要分享一個特殊狀況，請看以下範例程式碼

```js
var 'smalljie' = 1;
```

如果透過變數宣告的方式賦值，在瀏覽器上你可能不會看到 Left-Hand side 的錯誤訊息

在Chrome瀏覽器上輸入會出現`Uncaught SyntaxError: Unexpected string`

而在Firefox上輸入則會出現`SyntaxError: missing variable name`

兩者提示問題的差異在於瀏覽器提供的執行環境提示訊息的不同，由此我們可以知道執行環境是很重要的觀念。

## RHS

RHS，全名為Right-Hand Side

Right-Hand Side的意思是`取值`來自於右側的變數上，如以下範例

```js
var name = 'smalljie';
console.log(name);
```
在這邊我們可以看到`console.log()`去取得右側的變數 name，並顯示在`devTools`上

換另外一種角度看上述的程式碼，會發現到一開始會先 LHS 賦予值，後續到了`console.log()`時會去查詢、引用`name`的值並顯示出來

那什麼時候會發生RHS錯誤呢?

RHS的錯誤訊息相較於LHS會有稍微的不同，因為RHS並不會直接顯示出 RHS 的錯誤，他只會出現類似`ReferenceError: name is not defined`這種的錯誤訊息。

當然在不同瀏覽器上的錯誤訊息也會有一點點小小差異

基本上如果有遇到上面的任何錯誤，都會建議一定要修正，否則程式碼是無法正常運作的，因為 JavaScript 一旦遇到錯誤就無法往後執行

### 章節重點
- Left-Hand Side(LHS)是用來`賦予值`到左側的變數上
- Right-Hand Side(RHS)是`取值`來自於右側的變數上
- 錯誤訊息會因不同的瀏覽器而有些微的差異
- JavaScript一旦遇到錯誤就無法往後執行，如果有遇到上面的任何錯誤，都會建議一定要修正

## 參考文獻

- [JavaScript 核心篇](https://www.hexschool.com/courses/js-core.html)
- [前端筆記 - JavaScript — LHS 與 RHS](https://gene-toys.medium.com/%E5%89%8D%E7%AB%AF%E7%AD%86%E8%A8%98-javascript-lhs-%E8%88%87-rhs-7385f6fd47fc)
