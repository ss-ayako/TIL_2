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
