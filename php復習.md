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

    // この下に連想配列を作ってください
    $scores = array(
      "数学" => 70,
      "英語" => 90,
      "国語" => 80,
    );
    $scores["国語"]+=5;
    echo $scores["国語"];
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

    // この下にfor文を書いてください
    for($i=51;$i<=100;$i++){
      echo $i;
      echo '<br>';
    }
    
  ?>

</body>
</html>
```
- これまでの変数が一つしか値を扱えなかったのに対し、配列を用いると複数の値をまとめて保存することができます。
- 配列は仕切りのある箱のようなもので、それぞれのスペースにデータが入っており、0, 1, 2...というインデックス番号によってスペースの名前が付けられています。
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

    // 変数$iを定義してください
    $i=2;
    
    // while文を書いてください
    while($i<=100){
      if($i%2==0){
      echo $i;
      echo '<br>';
      }
      $i++;
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

    // この下にfor文を書いてください
    for($i=1;$i<=1000;$i++){
      if($i%3==0){
        continue;
      }
      echo $i;
      echo '<br>';
    }
    
  ?>

</body>
</html>
```
- foreach文とは、配列または連想配列に対して、先頭のデータから順に繰り返し処理を行うための命令です。
- 以下のように配列のデータを１つずつ取り出して処理を行うことが出来ます。
- 「as」の後ろの変数に、ループの度にデータが先頭から順に代入されていきます。
- asの後ろの変数名は何を指定しても大丈夫です。
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

    $scores = array('数学' => 70, '英語' => 90, '国語' => 80);

    // この下にforeach文を書いてください
    foreach($scores as $key => $value){
      echo $key.'は'.$value.'点です。';
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

    $str = 'progate';

    // strlenを用いて$strの長さをechoしてください
    echo strlen($str);
    
    echo '<br>';
    
    $array = array('HTML', 'CSS', 'PHP');

    // countを用いて$arrayの要素数をechoしてください
    echo count($array);
    
    echo '<br>';
    
    // randを用いて10から15までのランダムな数字をechoしてください
    echo rand(10,15);
    
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

    // 関数helloを定義してください
    function hello(){
      echo "Hello, world!";
    }
    
    // 関数helloを呼び出してください
    hello();
    
    echo '<br>';
    // 関数printRectangleAreaを定義してください
     function printRectangleArea($height,$width){
      echo $height*$width;
    }
    
    // 引数を(5, 10)としてprintRectangleAreaを呼び出してください
    printRectangleArea(5,10);
    
  ?>

</body>
</html>
```
```
## PHPでフォームから送信された10個の値を配列で送信する方法と、そのまま送信する方法について解説します。

### 1. 配列で送信する方法

**HTMLのフォーム:**

```html
<form action="process.php" method="post">
  <input type="text" name="values[]" value="">
  <input type="text" name="values[]" value="">
  <input type="submit" value="送信">
</form>
```

**PHPの処理 (process.php):**

```php
<?php
// 送信された値を取得
$values = $_POST['values'];

// 配列の中身を表示 (確認用)
print_r($values);
```

**解説:**

* **HTML:**
  - `name`属性に`values[]`と指定することで、送信された値が`values`という名前の配列に格納されます。
* **PHP:**
  - `$_POST['values']`で、フォームから送信された`values`配列を取得します。
  - `print_r()`関数で、配列の中身を確認できます。

**メリット:**
* 複数の値をまとめて処理できる。
* JavaScriptなど、他の言語との連携がしやすい。

### 2. そのまま送信する方法

**HTMLのフォーム:**

```html
<form action="process.php" method="post">
  <input type="text" name="value1" value="">
  <input type="text" name="value2" value="">
  <input type="submit" value="送信">
</form>
```

**PHPの処理 (process.php):**

```php
<?php
// 送信された値を取得
$value1 = $_POST['value1'];
$value2 = $_POST['value2'];
// 以下、同様の変数を8個定義

// 値を表示 (確認用)
echo $value1;
echo $value2;
// 以下、同様の処理を8個繰り返す
```
<?php
// 送信された値を取得
$value1 = $_POST['value1'];
$value2 = $_POST['value2'];
// 以下、同様の変数を8個定義

// 値を表示 (確認用)
echo $value1;
echo $value2;
// 以下、同様の処理を8個繰り返す

**解説:**

* **HTML:**
  - 各入力要素に異なる`name`属性を指定します。
* **PHP:**
  - 各`name`属性に対応する変数に、送信された値を代入します。

**メリット:**
* シンプルで分かりやすい。
* 特定の値にだけアクセスしたい場合に便利。

### どちらを使うべきか？

* **複数の値をまとめて処理したい場合:** 配列
* **個々の値に頻繁にアクセスする場合:** 個別の変数

**一般的に、複数の値をまとめて処理する場合は、配列を使う方が効率的です。**

### その他

* **配列のメリット:**
  - 繰り返し処理が簡単
  - ソートや検索などの機能が豊富
  - 多次元配列で複雑なデータ構造を表現できる
* **セキュリティ:**
  - ユーザーが入力したデータをそのまま処理すると、セキュリティリスクが生じる可能性があります。
  - 入力値の検証やサニタイジングを必ず行うようにしましょう。

### まとめ

今回は、フォームから送信された10個の値を配列で送信する方法と、そのまま送信する方法について解説しました。どちらの方法を使うかは、処理の内容や、後の処理でどのようにデータを扱いたいかによって決まります。

**より具体的な質問があれば、お気軽にご質問ください。** 例えば、

* 「配列で受け取ったデータをデータベースに保存したい」
* 「JavaScriptで配列のデータをグラフ表示したい」
* 「セキュリティ対策として、どのような点に注意すればよいですか？」

など、具体的な状況ややりたいことを教えていただけると、より具体的なコード例や説明を提供できます。
```
