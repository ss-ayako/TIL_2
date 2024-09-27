# グローバルとローカル
confirmで「はい」「いいえ」のダイアログを出す
```
jikoshokai.html
<script>
  var name = prompt("おなまえは？");
  confirm(name + "でいいですか？");
  alert("こんにちは！" +  name + "さん");
</script>
```
```
tasu.js
function tasu(A,B){
  return A + B;
}
```
```
suuji.html
<html>
  <script t src = "tasu.js"></script>
  <script>
    C = tasu(5,2);
    alert("5 + 2 =" + C);
  </script>
</html>
```
```
mojiretsu.html
<html>
  <script src="tasu.js"></script>
  <script>
    D = tasu("アップル","パイ");
    alert("アップル + パイ =" + D );
  </script>
</html>
```
```
tasu2.js
var C;
function tasu(A,B){
  C = A + B;
}
```
```
suuji2.html
<html>
  <script src="tasu.js"></script>
  <script>
    tasu(5,2);
    alert("5 + 2 ="+ C);
  </script>
</html>
```
グローバル変数  
returnを使って戻り値を受け取っていない  
メリット：呼び出しして利用できて便利  
デメリット：どこからでも書き換えできる  
```
hiku.js
var C;
function hiku(A,B){
  C = A - B;
}
```
```
suuji3.html
<html>
  <script src ="tasu2.js"></script>
  <script src ="hiku.js"></script>
  <script>
    tasu(5,2);
    hiku(10,5);
    alert("5 + 2 =" + C);
    alert("10 - 5 =" + C);
  </script>
</html>
```
これだと5 + 2 = 5  
のあと10 - 5 =５  
となる。  
同じ変数Cを使っているから  
```
hiku2.js
var D;
function hiku(A,B){
  D = A - B;
}
```
```
<html>
  <script src ="tasu2.js"></script>
  <script src ="hiku2.js"></script>
  <script>
    tasu(5,2);
    hiku(10,5);
    alert("5 + 2 =" + C);
    alert("10 - 5 =" + D);
  </script>
</html>
```
変数Dを設定  
これだと5 + 2 = 7   
のあと10 - 5 =５  
となる。  
