# グローバルとローカル
confirmで「はい」「いいえ」のダイアログを出す
```
<script>
  var name = prompt("おなまえは？");
  confirm(name + "でいいですか？");
  alert("こんにちは！" +  name + "さん");
</script>
```
```
function tasu(A,B){
  return A + B;
}
```
```
<html>
  <script t src = "tasu.js"></script>
  <script>
    C = tasu(5,2);
    alert("5 + 2 =" + C);
  </script>
</html>
```
