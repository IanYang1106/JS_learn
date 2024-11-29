### Javascript 執行兩個階段

**variable hoisting(變數提升):主要因為 JS 執行兩階段造成**

- **建立期**：1A 註冊名稱(identifier)先拿名字+進行初始化先 undefined 1B
- **執行期**：執行函數+給值
- **變數提升**：變數與函數的宣告移動到作用域的最頂端做處理，行為解釋可以當成讓變數被實際宣告前就能使用，但是在 var 與 let/const 的狀態不一樣
- **TDZ(Temporal Dead Zone)**:暫時死區，let/const 在建立期先宣告變數，但是如果在宣告之前就進行使用，會直接給 referanceError，意即，宣告在需要作用的區域之前，否則提早進行使用會進入暫時死區

  - 使用 var 進行宣告，console.log 在第一階段可以被讀到 undefined，等第二階段賦值直接產出結果
    ![](/images/chap3/pic1.png)
    ![](/images/chap3/pic2.png)

  - 使用 let/const 進行宣告，宣告完成前使用則進入 TDZ，因此會有 ReferenceError
    ![](/images/chap3/pic3.png)
    ![](/images/chap3/pic4.png)

  - 使用 let 可以重新賦值，使用 const 進行宣告，不能重新賦值，但是陣列元素可以被改變
    let 部分：
    ![](/images/chap3/pic5.png)
    ![](/images/chap3/pic6.png)
    const 部分：
    ![](/images/chap3/pic7.png)
    ![](/images/chap3/pic8.png)
    ![](/images/chap3/pic9.png)
