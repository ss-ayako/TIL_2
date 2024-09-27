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
