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
  
