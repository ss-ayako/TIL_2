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
