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
```
shitsumon.js
var kotae = prompt("好きな食べ物は？","");
if(kotae == ""){
  alert("?");
}else{
  alert (kotae + "ですか！僕と同じですね。");
}

var kotae = prompt("嫌いな食べ物は？","");
if(kotae == ""){
  alert("?");
}else{
  alert ("え？！" + kotae + "ぼくは好きだよ.");
}

var kotae = prompt("行きたい国は？","");
if(kotae == ""){
  alert("?");
}else{
  alert (kotae + "かぁ。行けるといいね！！");
}

var kotae = prompt("明日の予定は？","");
if(kotae == ""){
  alert("?");
}else{
  alert (kotae + "？それって美味しいの？");
}

var kotae = prompt("今年の目標は？","");
if(kotae == ""){
  alert("?");
}else{
  alert ("ふーん" + kotae + "ね、頑張ってね");
}

var kotae = prompt("休みの日は何するの？","");
if(kotae == ""){
  alert("?");
}else{
  alert (kotae + "はいいね、今度一緒にやろう。");
}
```
- 一問ごとにプログラム書くの大変
- そこで関数を使おう！
```
shitsumon2.js
function shitsumon(question,answer1,answer2){
  var kotae = prompt(question,"");
  if(kotae == ""){
    alert("?");
  }else{
    alert(answer1 + kotae + answer2);
  }
}function shitsumon(question,answer1,answer2){
  var kotae = prompt(question,"");
  if(kotae == ""){
    alert("?");
  }else{
    alert(answer1 + kotae + answer2);
  }
}
```
- 追記した
- 引数に文字を入れて渡す
```
function shitsumon(question,answer1,answer2){
  var kotae = prompt(question,"");
  if(kotae == ""){
    alert("？");
  }else{
    alert(answer1 + kotae + answer2);
  }
}
shitsumon("すきな食べ物は？","","ですか！ぼくと同じですね。");
shitsumon("嫌いな食べ物は？","え〜！","ぼくは好きだよ。");
shitsumon("行きたい国は？","","かあ〜 行けるといいねえ〜");
shitsumon("明日の予定は？","","?それっておいしいの？");
shitsumon("今年の目標は？","ふーん。","ね。がんばってね。");
shitsumon("休みの日は何するの？","","は、いいね。こんどいっしょにしよう。");
```
```
aisatsu3.html
<html>
  <meta charset="UTF-8" />
  <script src = "shitsumon2.js"></script>
</html>
```
- 引数に数字を入れる
```
function tasu(a,b){
  alert(a+b);
}
```
