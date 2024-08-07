# 変数 
様々な値を入れる器のようなもの  
$の後、数字はダメ  
大文字小文字は別物  

```
<?php
$a = 10;
$b = 2;
$c = $a + $b;
echo $a . "+" . $b . "=" . $c;
?>

ブラウザで確認すると
10+2=12
```
***
```
<?php
$hensu = 5;
echo "1回目の変数の値:{$hensu}<br>";
$hensu = 10; //値変更
echo "2回目の変数の値:{$hensu}<br>";
$hensu = $hensu+3; //変数に３たす
echo "3回目の変数の値:{$hensu}<br>";
$hensu += 3 ; //変数に３たす
echo "4回目の変数の値:{$hensu}<br>";
?>

ブラウザで確認すると
1回目の変数の値:5
2回目の変数の値:10
3回目の変数の値:13
4回目の変数の値:16
```
文字列の中に{$hensu}を入れて変数の値を表示させることを「変数の展開」という  

複合代入演算子  
```
$hensu = $hensu+3  
$hensu += 3
```
同じ意味  
他にも、
```
+=
-=
*=
/=
%=
.= 連結して代入 $a=$a.$b
```

# インクリメント   
変数に１足す  
$n++; ++$n;  

# デクリメント   
変数から１を引く  
$n--; --$n;  

```
<?php
$n = 10;
echo "\$n=$n<br>";
$n++; //インクリメント 
echo "\$n=$n<br>";
++$n; //インクリメント 
echo "\$n=$n<br>";
$n--; //デクリメント 
echo "\$n=$n<br>";
--$n; //デクリメント 
echo "\$n=$n<br>";
?>

$n=10
$n=11
$n=12
$n=11
$n=10
```
エスケープシーケンス  
文字れるで表示できないような文字列を表示したいときに使用  
オプション￥でバックスラッシュ\  
\nで改行  
\rでキャッジリターン  
などなど  

```
<?php
$variable = 0.25;  //小数代入
var_dump($variable);
echo "<br>";
$variable = PHP;  //文字列代入
var_dump($variable);
echo "<br>";
$variable = true;  //論理値代入
var_dump($variable);
echo "<br>";
$variable = null;  //null代入
var_dump($variable);
echo "<br>";
unset($variable);//消去
# var_dump($variable);
?>


ブラウザ
float(0.25)
string(3) "PHP"
bool(true)
NULL
```
var_dumpは関数   
()内の変数の型や値の情報を返すもの    
unset関数  
変数そのものを削除  


ビットとバイト  
0と１のどちらかでしか表現できない情報の単位をビット  
このビットが８つ集まった単位をバイト  
0と１のみで数値を表す表現方法を２進数という  
```
<!DOCTYPE html>
<html>

<head>
  <title>例題3-1</title>
  <meta charset="UTF-8">
</head>

<body>
  <h1>文字列変数へのデータの追加</h1>
  <p>
    <?php

    //$sに初期値を代入
    $str = "Hello";
    //$strの末尾に”World"を追加
    $str =  $str. "World";  //ここ、$str.="World";でもOK 
    //結果を表示
    echo $str;

    ?>
  </p>
</body>

</html>
 
```
# 条件分離  
if(条件式）{  
処理  
}  
# " "と' 'の違い  
""は、変数が展開される  
''は、変数名が文字として表示される  
```
$a = 20

echo "$a";
echo '$a';

とすると

20
$a
と出力される
```
```
<?php
$a = 9;
echo '$aの値による処理の分岐NO2<br>';
if ($a === 10) {
  echo '$aの値は10です。';
} else {
  echo '$aの値は10ではありません。';
}
```
```
<?php
$a = 1;
echo '$aの値による処理の分岐NO 3<br>';

if ($a === 1) {
  echo '$aの値は1です。';
} else if ($a === 2) {
  echo '$aの値は2です。';
} else if ($a === 3) {
  echo '$aの値は3です。';
} else {
  echo '$aの値は1,2,3以外の値です。';
}
?>
```
# 比較演算子  

```
<?php
$a = 10;
$b = "10";

if ($a == $b) {
  echo '$a == $bです。';
} else {
  echo '$a == $bではありません。';
}

echo "<br>";

if ($a === $b) {
  echo '$a === $bです。';
} else {
  echo '$a === $bではありません。';
}
```
===は型も含めて同じでないと同じと判断されない  
# 型変換  
あらかじめ型を指定した上で、変数に値を代入  
値の先頭に（型名）をつける  
```
<?php
$a = (string)10;
$b = (int)"10";

var_dump($a);
echo"<br>";
var_dump($b);

?>
```
実行結果   
string(2)"10"  
int(10)  

(string)10は文字列10に  
(int)"10"は整数10に
# switch文  
```
<?php
$a = 1;
echo '$aの値による処理の分岐 switch文の場合<br>';

switch ($a) {

  case 1:
    echo '$aの値は1です。';
    break;

  case 2:
    echo '$aの値は2です。';
    break;

  case 3:
    echo '$aの値は3です。';
    break;

  default://省略可能
    echo '$aの値は1,2,3以外の値です。';
}
```
```
<?php
$temp = 10;
echo "水の温度{$temp}度<br>";

if ($temp >= 100) {
  echo '水蒸気（気体）です。';
} elseif ($temp <= 0) {
  echo '氷（固体）です。';
} else {
  echo '水（液体）です。';
}
```
# 複雑な条件分岐  
```
<?php

$a = "PHP";
$b = "PHP";
$c = "Hello";

echo "\$a=$a \$b=$b \$c=$c<br> ";
//$a、$bともに”PHP"か調べる
if ($a == "PHP" and $b == "PHP") {
  echo '$a、$bともに”PHP"です。<br>';
}
//$a、$cともに”PHP"か調べる
if ($a == "PHP" and $c == "PHP") {
  echo '$a、$cともに"PHP"です。<br>';
}
//$a、$bいずれかが”PHP"か調べる
if ($a == "PHP" or $b == "PHP") {
  echo '$a、$bいずれかが”PHP"です。<br>';
}
//$a、$cいずれか”PHP"か調べる
if ($a == "PHP" or $c == "PHP") {
  echo '$a、$cいずれかが"PHP"です。<br>';
}
```
結果
```
$a=PHP $b=PHP $c=Hello
$a、$bともに”PHP"です。
$a、$bいずれかが”PHP"です。
$a、$cいずれかが"PHP"です。
```
論理積　AかつBというように複数の条件を満たしているかどうかの判定に用いる  
使う演算子はandもしくは&&です  
論理和　AもシクはBというように複数の条件のうち１つ以上条件を満たしているかどうかの判定に用いる  
使う演算子はorもしくは||です  
