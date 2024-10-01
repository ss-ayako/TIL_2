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
グローバル変数の欠点：思わぬところで書き換えられる  
```
local.js
function local(){
  var hensu = "へんすう";
  alert(hensu);
}
```
hensuは関数localの中にある  
関数の中で定義しているので  
関数の中でしか使われない  
これがローカル変数！！  
```
local.html
<html>
  <script src="local.js"></script>
  <script>
    local();
  </script>
</html>
```
```
locallocal.js
function local(){
  var hensu = "へんすう";
  local2();
  alert(hensu);
}
function local2(){
  var hensu = "2つ目のへんすう";
  alert(hensu);
}
```
```
local.html書き換え
<html>
  <script src="locallocal.js"></script>
  <script>
    local();
  </script>
</html>
```
これを実行  
local() 関数を呼び出すと、最初に local() 内で hensu = "へんすう"; が定義  
次に local2() が呼び出し  
その中で hensu = "2つ目のへんすう"; という別のローカル変数が定義  
この変数は local2() の中だけで使われる  
ここで "2つ目のへんすう" というアラートが表示  
local2() の実行が終わり  
local() に戻り  
次に local() 内で定義された hensu = "へんすう"; がアラート  
ここでは "へんすう" というアラートが表示  
***
ゲームでは    
キャラクターのライフポイントやエネルギーはローカル変数  
そのキャラクターが出ている時にだけ必要な限定された情報だから  
ゲームの点数や残り時間などはグローバル変数  
***
# ミスを見つけよう  
```
local2.js
function local(){
  var hensu = "へんすう";
}
alert(hensu);
```
```
<html>
  <meta charset = "UTF-8" />
  <script src = "local2.js"></script>
  <script>
    local();
  </script>
</html>
```
真っ白  
検証ツールで確認  
関数の外でalert(hensu);としたため  
***
```
tento.html
<html>
  <head>
    <title>テントくんだ！</title>
    <style>
      h1,div{
        text-align:center;
      }
    </style>
  </head>
  <body>
    <h1>テントくんだ！</h1>
    <div><img src="tento.png"></div>
  </body>
</html>
```
```
tento.html書き換え
<html>
  <head>
    <title>大きくする</title>
    <title>テントくんだ！</title>
    <style>
      body{
        text-align:center;
      }
    </style>
    <script>
      function big(){
        document.getElementById("gazo").style.width = "400px";
      }
    </script>
  </head>
  <body>
    <h1>テントくんだ！</h1>
    <div><img id="gazo" src="IMG_8163.JPG" style="width:200px;"></div>
    <br>
    <button onClick="big()">大きくする</button>
  </body>
</html>
```
```
tento.html書き換え
<html>
  <head>
    <title>大きくする</title>
    <style>
      body{
        text-align:center;
      }
    </style>
    <script>
      function big(){
        var ookii;
        ookii = document.getElementById("gazo");
        ookii.style.width = "600px";
      }
    </script>
  </head>
  <body>
    <h1>テントくんだ！</h1>
    <div><img id="gazo" src="IMG_8163.JPG" style="width:200px;"></div>
    <br>
    <button onClick="big()">大きくする</button>
  </body>
</html>
```
```
var mouse;

window.onload = function(){
  ite();
};

function ite(){
  mouse = document.getElementById("tento");
  mouse.onclick = function(){
    alert("いてっ！");
  };
}
```
```
<html>
  <head>
    <title>たたけ！</title>
    <script type="text/javascript" src="shaberu.js"></script>
    <style>
      body{
        text-align:center;
      }
    </style>
  </head>
  <body>
    <h1>たたけ！</h1>
    <div><img id="tento" src="tento.png"></div>
    <br>
  </body>
</html>
```
