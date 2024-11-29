### 資料型別:

**基本型別（Primitive Types）如下表**

| 型別名稱 | 解釋                                                                                                                                   |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| number   | 整數型(Integers)、浮點型(Floats)、雙精度型(Doubles) 或 大數型(Bignums)，目前 js 使用的是雙精度型標示所有數字，是 64 位元的二進制編碼器 |
| string   | 標示文字的字元序列，集合就是字串                                                                                                       |
| boolean  | 布林值只提供 true of false 兩種回傳值與機械語言相似，只有 1 與 0                                                                       |
| null     | 代表不存在或是無效的物件、位址                                                                                                         |
| BigInt   | 可以表示任意精度格式的整數，代表的是可以表示的最大數字，例如單精度型就是 2 的 32 次方，雙精度型則是 64 次方，目前 js 使用的是雙精度型  |
| symbol   | 一個對象值的標示符號，回傳的 symbol 的都有自己唯一的回傳值，即使看起來一樣，進行===仍會是 false                                        |
| object   | 包含資料與處理資料指令的資料結構，例如陣列使用 typeof 會被當作 object                                                                  |

**基本型別的關鍵特徵**：

- 不可變性：一旦基本型別的變數被賦值，就無法直接改變該值。例如，對字串進行操作時，會創建一個新的字串，而不會直接修改原字串。基本型別的值始終是固定的。
- 按值傳遞：當基本型別的變數被賦值給另一個變數時，實際上是將其值的副本傳遞過去。因此，修改副本不會影響原始變數

```js
let a = 10
let b = a
b = 20
console.log(a) // 10
console.log(b) // 20
//在這裡，a 和 b 擁有不同的數值，改變 b 不會影響 a。
```

### 變數宣告

**變數可以使用 var、let、const 進行宣告**

- **var**:ES6 之前只有此項宣告，容易產生全域污染，可重複宣告，只有 function scope
- **let**:ES6 新增的宣告，由於 block scope 不會產生全域污染，不可重複宣告，具有 block scope 特性，let 的值可以重新賦值
- **const**:ES6 新增的宣告，由於 block scope 不會產生全域污染，不可重複宣告，具有 block scope 特性，const 的值不可以重新賦值，但是陣列內容可以被改變

![](/images/scope圖.png)

```javascript
let a = 1

function hello() {
  a = 2
  console.log(a)
}

hello()
console.log(a)

//funciton內印出1，a=2只是在給值，所以a往外找let a = 1
hello() //印出2
//外層的console.log(a)印出2
```

```javascript
console.log(a)

const a = function () {}

//此時a是TDZ，第一輪宣告名字，蓋上TDZ，第二輪函數還沒得到值，所以還是TDZ
```

- 函數控制：

```javascript
//函數就是輸入值跟輸出值的關係
function a() {
  //要做的事情
}

abc()
```

- 函數帶入參數與引數

```javascript
//abc(n)帶入的是參數
//abc(123)帶入的是引數

function abc(n) {
  console.log(n)
}

abc(123)
```

```javascript
function eat(food) {
    console.log(i ate,food);
}

eat(fish);
```

- 要回傳值結果需要給 return

```javascript
function f(x) {
  const result = 3 * x + 2
  return result
}
//自己加上console.log顯示
console.log(f(3))
console.log(f(4))
```
