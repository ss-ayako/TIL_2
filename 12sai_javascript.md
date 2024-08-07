hello,worldというダイアログ  
```
<html>
</head>
  <title>hello</title>
</head>
<body>
  <script>
    alert("hello,world");
  </script>
</body>
  </html>
```
- prompt　文字入力ダイアログ
- confirm 確認ダイアログ
- 受け付けた入力は変数を使って蓄える
- 変数、というけれど数字だけじゃない
- 変数使うぞ var　
- 変数の名前は自由に決める　var name
- 変数の内容 var name = " なになに";
- 以後　なになに　と書く必要なし、nameでOK
- 名前はなんでもOK
- でも、javascriptで使う言葉は使えないif varなど
prompt,confirm,alert使ったhtml
```
<script>
  var name = prompt("おなまえは？");
  confirm(name + "でいいですか？");
  alert("こんにちは！"+ name + "さん");
</script>
```
もし雨だったら、家でゲームする　を表現すると、
```
if(天気が雨）{
家でゲームする
}
```
```
if(条件){
処理１
}
```
```
<script>
var kakunin = confirm("太郎は、おとこのこでしょうか？");
if (kakunin == true){
  alert("正解！");
}
</script>
```
- 「==」は右と左が同じことを示している  
- 「!=」は異なるときを示している  
```
if(条件){
処理１
}else{
処理２
}
trueじゃないかtrueか
```
```
<script>
  var name = prompt("おなまえは？？");
  var kakunin = confirm(name + "でいいですか？？");
  if (kakunin == true){
    alert("こんにちは！"+ name + "さんよろしくねーーっ");
  }
  else{
    alert("こんにちは！、て、、え？？"+ name + "さんじゃないのね。。。");
  }
</script>
```

