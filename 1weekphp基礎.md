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
```
