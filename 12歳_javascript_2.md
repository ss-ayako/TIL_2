4章！！配列
# ファイルを分ける
```
<html>
  <script src="konichiha.js"></script>
</html>
```
- src souceの略
- konichiha.jsにプログラムが書いてますよという意味。
```
var onamae = prompt("おなまえは？","");
alert("こんにちは!"+ onamae + "さん");
```
- jsいきなり書いてOK
```
<html>
  <head>
    <meta charset="UTF-8">
    <title>挨拶ページ</title>
  </head>
  <script src="konichiha.js"></script>
</html>
```
- これで文字化け解決！！
```
var kotae = prompt("7×35=","");
if (kotae == 245){
  alert("正解です！");
}else{
  alert("残念！");
}
```
```
var kotae = prompt("「芬蘭」の読み仮名は？","");
if (kotae == "フィンランド" || kotae == "ふぃんらんど"){
  alert("正解！");
}else{
  alert("残念！");
}
```
```
var  kotae = prompt("昆虫の足は何本？","");
if(kotae == "6"||kotae == "６"){
  alert("正解！");
}else{
  alert("残念！");
}
```
