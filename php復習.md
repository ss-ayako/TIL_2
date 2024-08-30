- HTMLでは決められたテキストしか表示することができません。
- PHPを使うと、見る人や状況に応じて、表示するテキストを変えることができます。
- PHPはHTMLに埋め込んで使うことができます。
- <?php 〜 ?>の中にPHPの命令を書いていきます。
- <?php 〜 ?>の部分がHTMLに変換された上で表示されます。
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <?php
    // 'Hello, world!'をechoしてください
    echo"Hello, world!";
  ?>
  
  <br>

  <?php
    // 7 * 2をechoしてください
   echo 7 * 2; 
  ?>

  <br>

  <?php
    // 8 % 3をechoしてください
    echo 8 % 3;
  ?>

</body>
</html>
```
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <!-- この下で5 + 7を出力しましょう -->
  <?php
    echo 5 + 7;
  ?>

  <br>

  <!-- この下で'5 + 7'を出力しましょう -->
  <?php
     echo '5 + 7';
  ?>

</body>
</html>
```
- 変数とは、データの入れ物です。
- 頭に「$」記号をつけることによって変数を定義します。
- 「$変数名 = 値;」で様々な値を変数に入れることが出来ます。
- 「＝」はプログラミングの世界では、右辺を左辺に代入するという意味
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <!-- この下に変数$fruitを書いていきましょう！ -->
  <?php
    $fruit = "りんご";
    echo $fruit;
  ?>

  <br>

  <!-- この下に変数$sumを書いていきましょう！ -->
  <?php
    $sum = 8 + 9;
    echo $sum;
  ?>

</body>
</html>
```
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <?php

    $x = 5;
    $y = 2;
    $a = 8;
    $b = 4;
    
  ?>

  <!-- この下で$xの計算をしていきましょう -->
  <?php
    $x = $x + 10;
    echo $x;
  ?>

  <br>

  <!-- この下で$yの計算をしていきましょう -->
  <?php
    $y = $y * 5;
    echo $y;
    
  ?>

  <br>

  <!-- この下で$aの計算をしていきましょう -->
  <?php
    $a = $a + 1;
    echo $a;
    
  ?>

  <br>
  
  <!-- この下で$bの計算をしていきましょう -->
  <?php
    $b = $b - 1;
    echo $b;
    
    
  ?>

</body>
</html>
```
「.=」を用いると変数と文字列の連結を省略して書くことが出来ます。
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <?php
  
    $x = 1071;
    
    // 以下にif-elseif-else文を書いてください
    if($x % 3 == 0&&$x % 7 == 0){
      echo "xは3の倍数かつ7の倍数です。";
    }elseif($x % 3 == 0){
      echo "xは3の倍数ですが7の倍数ではありません。";
    }elseif($x % 7 == 0){
      echo "xは7の倍数ですが3の倍数ではありません。";
    }else{
      echo"xは7の倍数でも3の倍数でもありません。";
    }
    
  ?>

</body>
</html>
```
- if, elseifによる分岐が多く複雑な場合、switch文で書き換えるとシンプルで読みやすいコードに
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <?php

    // 変数$numを定義し、好きな数字を代入してください
    $num = 9;
  
    // 変数$remainderを定義し、変数$numを3で割った時の余りを代入してください
    $remainder = $num % 3;
 
    // switch文を用いてください
    switch($remainder){
      case 0:
        echo "大吉です。";
        break;
      case 1:
        echo "中吉です。";
        break;
      case 2:
        echo "小吉です。";
        break; 
      default:
        echo "凶です。";
        break; 
    }
  
  ?>

</body>
</html>
```
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
</head>
<body>

  <?php

    // この下に配列を作ってください
    $colors = array("赤","青","黄");
    echo $colors[0];
    $colors [] ="白";
    echo $colors[3];
  ?>

</body>
</html>
```
- これまでの変数が一つしか値を扱えなかったのに対し、配列を用いると複数の値をまとめて保存することができます。
- 配列は仕切りのある箱のようなもので、それぞれのスペースにデータが入っており、0, 1, 2...というインデックス番号によってスペースの名前が付けられています。
