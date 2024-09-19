# 関数
- 複数のファイルに分けたプログラムを使い回す
- 同じようなプログラムを何度も書かずに済む　関数
```
konichiwa.js
alert("こんにちは！");
```
```
aisatsu.html
<html>
  <meta charset="UTF-8" />
  <script type ="text/javascript"src="konichiwa.js"></script>
</html>
```
```
konichiwa.js書き換え
function konichiwa(){
  alert("こんにちは！");
}
```
- function 関数の名前(){
- 関数の中身
- }という構造。
```
aisatsu.html書き換え
<html>
  <meta charset="UTF-8" />
  <script type ="text/javascript"src="konichiwa.js"></script>
  <script>
    konichiwa();　//ここから関数を呼び出す
  </script>
</html>
```
