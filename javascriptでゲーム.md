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
