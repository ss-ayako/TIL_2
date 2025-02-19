***
写経第二弾
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>みんなの料理</title>
  </head>
  <body>
    <h1>今日のレシピ</h1>
    <p>定番料理や旬の食材を使った料理をご紹介しています。
      きょうの料理はタケノコご飯です。
    </p>
  </body>
</html>
```
htmlの基礎  
変数  
演算  
比較と条件式  
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function check(){
        let a =document.getElementById("i0").value;
        let b =document.getElementById("i1").value;
        document.getElementById("r0").textContent = a == b;
        document.getElementById("r1").textContent = a != b;
        document.getElementById("r2").textContent = a < b;
        document.getElementById("r3").textContent = a > b;
        document.getElementById("r4").textContent = a <= b;
        document.getElementById("r5").textContent = a >= b;
      }
    </script>
  </head>
  <body>
    a:<input id="i0" value="3">
    b:<input id="i1" value="5">
    <button onclick="check()">check</button>
    <ul>
      <li>a == b : <span id="r0"></span></li>
      <li>a != b : <span id="r1"></span></li>
      <li>a < b : <span id="r2"></span></li>
      <li>a > b : <span id="r3"></span></li>
      <li>a <= b : <span id="r4"></span></li>
      <li>a >= b : <span id="r5"></span></li>
    </ul>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function calcBMI(){
        let height = document.getElementById("i0").value;
        let weight = document.getElementById("i1").value;
        let bmi = weight / (height * height);
        if(bmi < 18.5){
          document.getElementById("result").textContent = "痩せすぎ";
        }else if(bmi >= 25){
          document.getElementById("result").textContent = "肥満気味";
        }else{
          document.getElementById("result").textContent = "標準";
        }
      }
    </script>
  </head>
  <body>
    <h2>BMI計算機</h2>
    身長(m):<input id="i0" value="1.7">
    体重(kg):<input id="i1" value="65">
    <button onclick="calcBMI()">check</button>
    <p id ="result"></p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function update(){
        let a = document.getElementById("a").checked;
        let b = document.getElementById("b").checked;
        let c = document.getElementById("c").checked;
        document.getElementById("r0").textContent = a && b && c;
        document.getElementById("r1").textContent = a || b || c;
      }
    </script>
  </head>
  <body>
    <h2>AND/ORテスト</h2>
    A:<input id ="a" type="checkbox" onchange="update()">
    B:<input id ="b" type="checkbox" onchange="update()">
    C:<input id ="c" type="checkbox" onchange="update()">
    <p>
      A && B && C =><span id="r0"></span><br>
      A || B || C =><span id="r1"></span><br>
    </p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      window.onload = function(){
        let str = "";
        let day = new Date().getDay();
        if(day == 0){
          str = "日";
        }else if (day == 1){
          str = "月";
        }else if (day == 2){
          str = "火";
        }else if (day == 3){
          str = "水";
        }else if (day == 4){
          str = "木";
        }else if (day ==5){
          str = "金";
        }else if (day == 6){
          str = "土";
        }
        document.getElementById("day").textContent = str;
      };
    </script>
  </head>
  <body>
    <h1>今日は<span id="day"></span>曜日</h1>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      window.onload = function(){
        let str = "";
        let day = new Date().getDay();
        switch(day){
          case 0:
            str = "日";
            break;
          case 1:
            str = "月";
            break;
          case 2:
            str = "火";
            break; 
          case 3:
            str = "水";
            break;
          case 4:
            str = "木";
            break;
          case 5:
            str = "金";
            break;
          case 6:
            str = "土";
            break;   
        }
        document.getElementById("day").textContent = str;
      };
    </script>
  </head>
  <h1>今日は<span id="day"></span>曜日</h1>
</body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function jikkan(year){
        let str;
        switch(year % 10){
          case 0:
            str = "庚";
            break;
          case 1:
            str = "辛";
            break;
          case 2:
            str = "壬";
            break; 
          case 3:
            str = "癸";
            break;
          case 4:
            str = "甲";
            break;
          case 5:
            str = "乙";
            break;
          case 6:
            str = "丙";
            break;  
            case 7:
            str = "丁";
            break;
          case 8:
            str = "戊";
            break;
          case 9:
            str = "己";
            break;
        }
        return str;
      }

      function junishi(year){
        let str;
        switch(year % 12){
          case 0:
            str = "申";
            break;
          case 1:
            str = "酉";
            break;
          case 2:
            str = "戌";
            break; 
          case 3:
            str = "亥";
            break;
          case 4:
            str = "子";
            break;
            case 5:
            str = "丑";
            break;
          case 6:
            str = "寅";
            break;
          case 7:
            str = "卯";
            break;
          case 8:
            str = "辰";
            break;
          case 9:
            str = "巳";
            break;
          case 10:
            str = "午";
            break;
          case 11:
            str = "未";
            break;
        }
        return str;
      }

      function calc(){
        let year = document.getElementById("year").value;
        let tenkan = jikkan(parseInt(year, 10));
        let chizhi = junishi(parseInt(year, 10));
        document.getElementById("e").textContent = tenkan + chizhi;
        document.getElementById("y").textContent = year;
      }
    </script>
  </head>
  <body>
    <h2><span id="y"></span>年の干支は<span id="e"></span></h2>
    <p>
      <input id="year" value="2023">
      <button onclick="calc()">計算</button>
    </p>
  </body>
</html>
```
三項演算子
```
let subjects = ["数学","国語","社会","理科"];
let week = ["月","火","水","木","金","土"];
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function calcSum(){
        let max = document.getElementById("max").value;
        let total = 0;
        for (let i = 1; i <= max; i++) {
          total += i; 
        }
        document.getElementById("val").textContent = max;
        document.getElementById("sum").textContent = total;
      }
    </script>
  </head>
  <body>
    <h2>1から<span id="val">10</span>の合計は<span id="sum"></span></h2>
    <input id ="max" value="10">
    <button onclick="calcSum()">合計</button>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function calcSum(){
        let max = document.getElementById("max").value;
        let total = 0;
        let i = 1;
        while(i <= max) {
          total += i; 
          i++;
        }
        document.getElementById("val").textContent = max;
        document.getElementById("sum").textContent = total;
      }
    </script>
  </head>
  <body>
    <h2>1から<span id="val">10</span>の合計は<span id="sum"></span></h2>
    <input id ="max" value="10">
    <button onclick="calcSum()">合計</button>
  </body>
</html>
```
while文でcontinueが呼び出されると、条件式１に戻る  
braekでループ抜ける  
for文の場合、continueが呼び出されるとそれ以降の処理は実行されない  
braekでループ抜ける  
while文 は回数が決まっていない時に便利  
for文は事前に回数が決まっている時に便利  
```
<!DOCTYPE html>
<html>
  <head></head>
  <meta charset="UTF-8">
  <script>
    function kaibun(){

       // 入力された文字列を取得
        let source = document.getElementById("source").value;
        
        // 逆順の文字列を生成
        let reversed = "";
        for (let i = source.length - 1; i >= 0; i--) {
          reversed += source.charAt(i); // 1文字ずつ追加
        }
        
        // 結果を表示（逆順文字列のみ）
        document.getElementById("result").textContent = reversed;
    }
  </script>
  </head>
  <body>
    <input id ="source">
    <button onclick="kaibun()">回文</button>
    <p id="result"></p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
  <meta charset="UTF-8">
  <script>
    function c2f(c){
      return c * 9/5 + 32;
    }

    function convert(){
      let c = document.getElementById("celsius").value;
      let f = c2f(c);
      let s = "摂氏："+c+"度　華氏："+ f +"度";
      document.getElementById("result").textConcent = s;
    }
  </script>
  </head>
  <body>
    <input id="celsius" type="range" min="0" max="100" onchenge="convert()">
    <p id="reslt"></p>
  </body>
</html>
```
```
<script>
  let count = 0;

  function test(e){
    let a ="hello";
    for(let i =0; i < 3;i++){
      console.log("count=" + count + "i=" + i);
      console.log(a)
    }
    count++;
  }
  function inti(){
    count = 10;
  }
</script>
```
***
デバック  
F12  
ブレークポイント  
***
オブジェクトもの   
プロパティ個々の特徴  
メソッド個々の操作  
インターフェース操作方法のまとまり
カプセル化中で起きていることを隠すこと  
***
```
let car = {
  color:"white",
  speed:30,
  fuel:100
}
```
オブジェクト.プロパティ名
***
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      let pen ={
        color: "red",
        length: 5,
      };
      function checkLength(){
        document.getElementById("length").textContent = pen.length;
      }
    </script>
    </head>
  <body>
    <button onclick="checkLength()">長さチェック</button>
    <p>鉛筆の長さは<span id="length"></span>cm</p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      let car ={
        speed: 100,
        oil: 50,
      };
      function checkSpeed(){
        document.getElementById("speed").textContent = car.speed;
      }
      function checkOil(){
        document.getElementById("oil").textContent = car.oil;
      }
    </script>
    </head>
  <body>
    <button onclick="checkSpeed()">スピードチェック</button>
    <p>スピードは<span id="speed"></span>km</p>
    <button onclick="checkOil()">ガソリンチェック</button>
    <p>ガソリンの量は<span id="oil"></span>L</p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      let pen  ={
        color:"red",
        length:5,
        draw:function(){
          this.length -=0.01;
        }
      };
      function stroke(){
        pen.draw();
        document.getElementById("length").textContent = pen.length;
      }
    </script>
  </head>
  <body>
    <button onclick="stroke()">書く</button>
    <p>鉛筆の長さは<span id="length"></span>cm</p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function Pen(color,length){
        this.color = color;
        this.length = length;
        this.draw = function(){
          this.length -=0.01;
        };
      }
      let penR = new Pen("red",5);
      let penG = new Pen("green",15); 
      let penB = new Pen("blue",7); 
      let pen = penR;

      function stroke(){
        pen.draw();
        document.getElementById("color").textContent = pen.color;
        document.getElementById("length").textContent = pen.length;
      }

      function pickR(){
        pen = penR;
      }

      function pickG(){
        pen = penG;
      }

      function pickB(){
        pen = penB;
      }
    </script>
  </head>
  <body>
    <button onclick="pickR()">赤を選ぶ</button>
    <button onclick="pickG()">緑を選ぶ</button>
    <button onclick="pickB()">青を選ぶ</button>
    <button onclick="stroke()">書く</button>
    <p>
      えんぴつの色は<span id="color"></span>、長さは<span id="length"></span>cm
    </p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      class Pen{
        constructor(color,length){
          this.color = color;
          this.length = length;
        }
        draw(){
          this.length-=0.01;
        }
      }
      let penR = new Pen("red",5)
      let penG = new Pen("green",15)
      let penB = new Pen("blue",7)
      let pen = penR;

      function stroke(){
        pen.draw();
        document.getElementById("color").textContent = pen.color;
        document.getElementById("length").textContent = pen.length;
      }

      function pickR(){
        pen = penR;
      }
      function pickG(){
        pen = penG;
      }
      function pickB(){
        pen = penB;
      }
    </script>
  </head>
  <body>
    <button onclick="pickR()">赤を選ぶ</button>
    <button onclick="pickG()">緑を選ぶ</button>
    <button onclick="pickB()">青を選ぶ</button>
    <button onclick="stroke()">書く</button>
    <p>
      鉛筆の色は<span id ="color"></span>、長さは<span id="length"></span>cm
    </p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function Pen(color,length){
        this.color = color;
        this.length = length;
        this.draw = function(){
          this.length -= 1;
        };
      }
      let penR = new Pen("red",15);
      let penG = new Pen("green",15);
      let penB = new Pen("blue",8);
      let pen = penR
    </script>
  </head>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      function Pen(color,length){
        this.color = color;
        this.length = length;
        this.draw = function(){
          this.length -= 1;
        };
      }
      let penR = new Pen("red",15);
      let penG = new Pen("green",15);
      let penB = new Pen("blue",8);
      let pen = penR;

      function stroke(){
        pen.draw();
        let pencil = document.getElementById("pencil");
        pencil.style.width = pen.length + "cm";
        pencil.style.backgroundColor = pen.color;
        pencil.textContent = "色=" + pen.color + "長さ="+pen.length;
      }

      function pickR(){
        pen = penR;
      }
      function pickG(){
        pen = penG;
      }
      function pickB(){
        pen = penB;
      }
    </script>
  </head>
  <body>
    <button onclick="pickR()">赤を選ぶ</button>
    <button onclick="pickG()">緑を選ぶ</button>
    <button onclick="pickB()">青を選ぶ</button>
    <button onclick="stroke()">書く</button>
    <p id="pencil" style="background-color:red; width:5cm"></p>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <script>
      let colors = ["red","blue","green","yellow","purple"];
      let index = 0;
      function insert(){
        let parent = document.getElementById("mylist");
        let item = document.createElement("li");
        item.textContent = colors[index];
        item.style.color = colors[index];
        index = ++index % colors.length;
        parent.appendChild(item);
      }
    </script>
  </head>
  <body>
    <button onclick="insert()">挿入</button>
    <ol id ="mylist"></ol>
  </body>
</html>
```
```
 <ol> (順序付きリスト) 
DOM JavascriptからHTML文書を更新する方法  
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <style>
      #board{
        background-color: black;
      }
      /* #board → <table>（盤面）の背景色を黒に設定 */

      td.cell{
        background-color: green;
        width: 30px;
        height: 30px;
      }
      /* .cell（各マス）→ 背景を緑 (green)、サイズを 30px × 30px に指定 */

    </style>
    <script>
      function init(){
  let b = document.getElementById("board"); // <table> を取得
  for(let i = 0; i < 8; i++){ // 8行を作成
    let tr = document.createElement("tr"); // <tr> (行) を作成
    for(let j = 0; j < 8; j++){ // 各行に8個のセルを追加
      let td = document.createElement("td"); // <td> (セル) を作成
      td.className = "cell"; // クラスを "cell" に設定
      td.id = "cell" + i + j; // 各セルにユニークなIDを設定 (例: "cell00", "cell07", ...)
      td.onclick = clicked; // クリック時に `clicked` 関数を実行
      tr.appendChild(td); // <tr> に <td> を追加
    }
    b.appendChild(tr); // <table> に <tr> を追加
  }
}
      function clicked(e){
        // e.target.id → クリックしたセルのIDを取得

        document.getElementById("info").textContent = e.target.id + " clicked";
      }
      // <h2 id="info"> のテキストを "cellXX clicked" に更新

    </script>
  </head>
  <body onload="init()">
    <!-- ページ読み込み時に init() を自動実行 し、盤面を生成 -->
    <table id="board"></table>
    <h2 id="info"></h2>
  </body>
</html>
```
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <style>
      #board{
        background-color: black;
      }
      /* #board → <table>（盤面）の背景色を黒に設定 */

      td.cell{
        background-color: pink;
        width: 30px;
        height: 30px;
      }
      /* .cell（各マス）→ 背景を緑 (green)、サイズを 30px × 30px に指定 */

    </style>
    <script>
      function init(){
  let b = document.getElementById("board"); // <table> を取得
  for(let i = 0; i < 3; i++){ // 8行を作成
    let tr = document.createElement("tr"); // <tr> (行) を作成
    for(let j = 0; j < 3; j++){ // 各行に8個のセルを追加
      let td = document.createElement("td"); // <td> (セル) を作成
      td.className = "cell"; // クラスを "cell" に設定
      td.id = "cell" + i + j; // 各セルにユニークなIDを設定 (例: "cell00", "cell07", ...)
      td.onclick = clicked; // クリック時に `clicked` 関数を実行
      tr.appendChild(td); // <tr> に <td> を追加
    }
    b.appendChild(tr); // <table> に <tr> を追加
  }
}
let turn = 0; // 0: ○, 1: ×
// turn 変数を宣言し、0で初期化
// この変数は、○と×のどちらのターンであるかを管理

function clicked(e) {
  const cell = e.target; // クリックされたセル要素

  // セルが空の場合のみ処理を行う
  if (cell.textContent === "") {
    if (turn === 0) {
      cell.textContent = "○";
      turn = 1;// 次のターンを×にする
    } else {
      cell.textContent = "×";
      turn = 0;// 次のターンを○にする
    }
  }
}

    </script>
  </head>
  <body onload="init()">
    <!-- ページ読み込み時に init() を自動実行 し、盤面を生成 -->
    <table id="board"></table>
    <h2 id="info"></h2>
  </body>
</html>
```
