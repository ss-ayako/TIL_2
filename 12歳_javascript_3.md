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
 # 引数がご飯、体が関数、うんこが戻り値
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
# そこで関数を使おう！
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
# 引数に文字を入れて渡す
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
# 引数に数字を入れる
```
function tasu(a,b){
  alert(a+b);
}
```
```
hikisuu.html
<html>
  <meta charset="UTF-8" />
  <script type="text/javascript" src="tashizan.js"></script>
  <script>
    tasu(5,7);
  </script>
</html>
```
- tasu(5,7);こっちは数字
- tasu("5","7");こっちは文字
- 引数という形で関数に数字を渡しました
- 関数の処理の結果を戻り値、返り値という
***
 function 関数の名前（引数）{  
 関数の中身  
return 戻り値;  
 }  
***
```
suujimodorichi.js
function suujikaesu(){
  return 100; //suujikaesu 関数は呼び出されると、常に 100 を返す
}
```
```
modorichi.html
<html>
  <meta charset="UTF-8" />
  <script type="text/javascript" src="suujimodorichi.js">
  </script>
  <script>
    var suuji = suujikaesu();
    alert(suuji+10);
  </script>
</html>
```
- suujimodorichiを読み込み
- suujikaesu()関数呼び出し　これの戻り値１００
- これを変数suujiに代入
- １０足して表示
- １００＋１０で１１０が表示される
# 戻り値で文字を返す  
```
tensai.js
function tensai(){
  return "天才！";
}
```
```
tento.js
function tento(){
  return "テントくん";
}
```
```
mojiretsu.js
function mojitasu (a,b){
alert(a + b);
}
```
```
<html>
  <meta charset="UTF-8" />
  <script type="text/javascript" src="tensai.js"></script>
  <script type="text/javascript" src="tento.js"></script>
  <script type="text/javascript" src="mojiretsu.js"></script>
  <script>
    var b = tensai();//戻り値：天才！
    var a = tento();//戻り値：テントくん
    mojitasu(a + b);
  </script>
</html>
```
# クイズプログラムをすっきりと！！
```
mondai.js
function mondai(question,answer){
  var kotae = prompt(question,"");
  if(kotae == anser){
    alert("正解！");
    return true;
  }else{
    alert("ざんねん！");
    return false;
  }
}
```
```
sansu2.js
var seikai= 0;
if (mondai("7 × 35 = ",245) == ture){
  seikai = seikai + 1;
}
if (mondai("112 - 53 = ",59) == ture){
  seikai = seikai + 1;
}
tensu[0]= seikai;
```
- 正解の戻り値を１、不正解の戻り値を０
- mondaiの戻り値を、変数seikaiに足すプログラムを作る
```
function mondai(question,answer){
  var kotae = prompt(question,"");
  if(kotae == anser){
    alert("正解！");
    return 1;//正解なら１を返す
  }else{
    alert("ざんねん！");
    return 0;//不正解なら０を返す
  }
}
```
```
sansu2.js
すっきり書き換え
var seikai= 0; //変数を用意する

/* 
すっきり書き換え
if (mondai("7 × 35 = ",245) == ture){
  seikai = seikai + 1;
}
if (mondai("112 - 53 = ",59) == ture){
  seikai = seikai + 1;
}
*/

seikai = seikai + mondai("7 × 35 = ",245);
seikai = seikai + mondai("112 - 53 = ",59);
tensu[0]= seikai; //点数を保存する
```
答えが２パターンの場合に備えて書き換え  
```
function mondai(question,answer){
  var kotae = prompt(question,"");
  if(kotae == anser){
    alert("正解！");
    return 1;//正解なら１を返す
  }else{
    alert("ざんねん！");
    return 0;//不正解なら０を返す
  }
}
//answer1,answer2のどちらかと同じなら正解と表示するように
function mondai2(question,answer1,answer2){
  var kotae = prompt(question,"");
  if(kotae == answer1||kotae == answer2){
    alert("正解！");
    return 1;
  } else {
    alert("ざんねん！");
    return 0;
  }
}
```
```
kokugo2.js書き換え
var seikai= 0;
seikai= seikai + mondai2("「芬蘭」の読み仮名は？","フィンランド","ふぃんらんど");
  alert("正解！");
seikai = seikai + mondai("「細魚」の読み仮名は？","さより");
tensu[1]= seikai;
```
```
rika2.js書き換え
var seikai= 0;
seikai = seikai + mondai2("昆虫の足は何本？","6","６");
seikai = seikai + mondai2("光合成では空気中の二酸化炭素を吸収し⚪︎⚪︎を放出しています、それは何でしょうか？","酸素","さんそ");
tensu[2]= seikai;
```
```
shakai2.js書き換え
var seikai= 0;
seikai = seikai + mondai2("北海道の県庁所在地は？","札幌","さっぽろ");
seikai = seikai + mondai("日本で一番高い山は？","富士山");
tensu[3]= seikai;
```
```
newquiz2.html書き換え
<html>
  <head>
    <meta charset="UTF-8">
  </head>
  <script src="hairetsu.js"></script>
  <script src="konichiwa.js"></script>
  <script src="mondai.js"></script>
  <script src="sansu2.js"></script>
  <script src="kokugo2.js"></script>
  <script src="rika2.js"></script>
  <script src="shakai2.js"></script>
  <script src="goukei.js"></script>
  <script src="zenmonseikai.js"></script>
</html>
```
```
fukuzatsu.js
var n = prompt("おなまえは？","");while(ture){
var k = prompt("3.14 * 2 =","");if(k !="6.28"){alert("はずれ。");continue;}alert("正解。");
var k = prompt("では、南半球でクリスマスの時の季節は？","");if(k !="夏"){alert("はずれ。");continue;}alert("正解。");
var k = prompt("楽譜で、音の一時的な休止を表す記号は？","");if (k !="休符"){alert("はずれ。");continue;}alert("正解。");
var k = prompt("夏の大三角といえば、ベガとデネブと何？","");if (k !="アルタイル"){alert("はずれ。");continue;}alert("正解。");
var k = prompt("2020年に予定されているオリンピック開催地は？","");if(k !="東京"){alert("はずれ。");continue;}alert("正解。");break;}alert("全問正解おめでとう！！すごいね"+ n +"さん");
```
```
fukuzatsu.html
<html>
  <meta charset = "UTF-8" />
  <script src = "fukuzatsu.js"></script>
</html>
```
```
kantan.js
var tento = prompt("おなまえは？","");
while(true){
  var keisan = prompt("3.14 * 2 =","");
  if(keisan !="6.28"){
  alert("はずれ。");
  continue;
  }alert("正解。");

  var kisetsu = prompt("では、南半球でクリスマスの時の季節は？","");
  if(kisetsu !="夏"){
  alert("はずれ。");
  continue;
  }alert("正解。");

  var ongaku = prompt("楽譜で、音の一時的な休止を表す記号は？","");
  if (ongaku !="休符"){
  alert("はずれ。");
  continue;
  }
  alert("正解。");

  var seiza = prompt("夏の大三角といえば、ベガとデネブと何？","");
  if (seiza !="アルタイル"){
  alert("はずれ。");
  continue;
  }
  alert("正解。");

  var sports = prompt("2020年に予定されているオリンピック開催地は？","");
  if(sports !="東京"){
  alert("はずれ。");
  continue;
  }
  alert("正解。");
  break;
}
alert("全問正解おめでとう！！すごいね"+ tento +"さん");
```
mondai(mondaibun,kotae)関数でまとめた  
問題と答えは引数で渡す  
```
sukkiri.js
/*出題プログラム*/
function mondai(mondaibun,kotae){
  var answer = prompt(mondaibun,"");
  if (answer != kotae){
    alert("はずれ。");
    return false;
  }
  alert("正解！");
  return true;
}
/*問題全５問*/
var tento = prompt("おなまえは？","");
while(true){
  if (mondai("3.14 * 2 =","6.28")== false||
mondai("では、南半球でクリスマスの時の季節は？","夏")== false||
mondai("夏の大三角形といえば、ベガとデネブと何？","アルタイル")== false||
mondai("2020年に予定されているオリンピック開催地は？","東京")== false)
  
  continue;
  break;
}
alert("全問正解おめでとう！！すごいね！"+ tento +"さん");
```
```
sukkiri.html
<html>
  <meta charset="UTF-8" />
  <script type="text/javascript" src ="sukkiri.js"></script>
</html>
```
