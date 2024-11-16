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
