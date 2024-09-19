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
- function 関数の名前(引数){
- 関数の中身
- }という構造。
- 引数がご飯、体が関数、うんこが戻り値
```
konichiwa.js書き換え
function konichiwa(tento){
  alert("こんにちは！"+ tento +"さん");
}
```
```
aisatsu.html書き換え
<html>
  <meta charset="UTF-8" />
  <script type ="text/javascript"src="konichiwa.js"></script>
  <script>
    konichiwa("テント");//引数に”テント”を渡す
  </script>
</html>
```
```
shitsumon.js
var kotae = prompt("好きな食べ物は？","");
if(kotae == ""){
  alert("?");
}else{
  alert (kotae + "ですか！僕と同じですね。");
}
```
