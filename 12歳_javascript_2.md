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
```
var kotae = prompt("北海道の県庁所在地は？","");
if (kotae == "札幌"||kotae=="さっぽろ"){
  alert("正解！");
}else{
  alert("残念！");
}
```
- 追記して実行！
```
<html>
  <head>
    <meta charset="UTF-8">
    <title>挨拶ページ</title>
  </head>
  <script src="konichiha.js"></script>
  <script src="sansu.js"></script>
  <script src="kokugo.js"></script>
  <script src="rika.js"></script>
  <script src="shakai.js"></script>
</html>
```
```
var kotae = prompt("7×35=","");
if (kotae == 245){
  alert("正解です！");
}else{
  alert("残念！");
}
var kotae=prompt("112-53=","");
if (kotae == 59){
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
var kotae = prompt("「細魚」の読み仮名は？","");
if (kotae == "さより"){
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
var  kotae = prompt("光合成では空気中の二酸化炭素を吸収し⚪︎⚪︎を放出しています、それは何でしょうか？","");
if(kotae == "酸素"||kotae == "さんそ"){
  alert("正解！");
}else{
  alert("残念！");
}
```
```
var seikai= 0;
var kotae = prompt("7×35=","");
if (kotae == 245){
  alert("正解です！");
  seikai = seikai + 1;
}else{
  alert("残念！");
}
var kotae=prompt("112-53=","");
if (kotae == 59){
  alert("正解です！");
  seikai = seikai + 1;
}else{
  alert("残念！");
}
alert("点数は"+ seikai +"点です");
```
```
<script>
  var heiretsu = [];
  heiretsu[0] ="算数";
  heiretsu[1] ="国語";
  heiretsu[2] ="理科";
  heiretsu[3] ="社会";
  heiretsu[4] ="英語";
  heiretsu[4] ="体育";
  for(var i = 0;i < 6 ;i++){
    alert(hairetsu[i]);
  }
</script>
```
```
var tensu = [0,0,0,0];
```
- tensu という配列
- 4つの初期値（すべて 0）を持っています。
- 配列の要素には、インデックス番号（0から始まる）でアクセスして値を取得・変更できます。
```
var seikai= 0;
var kotae = prompt("7×35=","");
if (kotae == 245){
  alert("正解です！");
  seikai = seikai + 1;
}else{
  alert("残念！");
}
var kotae=prompt("112-53=","");
if (kotae == 59){
  alert("正解です！");
  seikai = seikai + 1;
}else{
  alert("残念！");
}
tensu[0]= seikai;
```
- tensu[0]= seikai;を足した。
```
var kotae = prompt("「芬蘭」の読み仮名は？","");
if (kotae == "フィンランド" || kotae == "ふぃんらんど"){
  alert("正解！");
}else{
  alert("残念！");
}
var kotae = prompt("「細魚」の読み仮名は？","");
if (kotae == "さより"){
  alert("正解！");
}else{
  alert("残念！");
}
tensu[1]= seikai;
```
```
var  kotae = prompt("昆虫の足は何本？","");
if(kotae == "6"||kotae == "６"){
  alert("正解！");
}else{
  alert("残念！");
}
var  kotae = prompt("光合成では空気中の二酸化炭素を吸収し⚪︎⚪︎を放出しています、それは何でしょうか？","");
if(kotae == "酸素"||kotae == "さんそ"){
  alert("正解！");
}else{
  alert("残念！");
}
tensu[2]= seikai;
```
```
var kotae = prompt("北海道の県庁所在地は？","");
if (kotae == "札幌"||kotae=="さっぽろ"){
  alert("正解！");
}else{
  alert("残念！");
}
var kotae = prompt("日本で一番高い山は？","");
if (kotae == "富士山"){
  alert("正解！");
}else{
  alert("残念！");
}
tensu[3]= seikai;
```
- 算数の点数を０、国語の点数を１、理科の点数を２、社会の点数を３に
- 平均点というのは全教科の点数÷教科の数
- 算数の点数＋国語の点数＋理科の点数＋社会の点数÷４となる
  ```
  var goukei =0;
for(var i = 0;i < 4;i++){
  goukei = goukei + tensu[i];
}
var heikin = goukei / 4;

alert("合計点は"+goukei+"点、"+"平均点は"+ heikin + "点でした。");
```
- これでもOK
```
var goukei = tensu[0] + tensu[1] + tensu[2] + tensu[3];
var heikin = goukei / 4;
```
