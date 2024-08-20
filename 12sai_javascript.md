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
```
<script>
  var name = prompt("おなまえは？？");
  var sippo = prompt("突然ですが、問題です！パンダのしっぽの色は？");
  if (sippo == "白"){
    alert("正解！！さすが"+ name +"さん");
  }else{
    alert(name +"さん、残念。白でした！");
  }
</script>
```
```
<script>
  var name = prompt("おなまえは？");
  var sippo = prompt("突然ですが問題です。パンダのしっぽは何色？");
  if(sippo =="白"){
    alert("正解。");
  } else {
    alert(name + "さん、残念。白でした！！");
  }
  var kuni = prompt("では、世界で一番大きい国は？");
  if(kuni =="ロシア"){
    alert("正解。");
  } else {
    alert(name + "さん、残念。ロシアでした！！");
  }
  var keisan = prompt("最後の問題です。7✖️8 =?");
  if(keisan =="56"){
    alert("正解。");
  } else {
    alert(name + "さん、残念。56でした！！");
  }
  if(sippo =="白"){
    if(kuni =="ロシア"){
      if(keisan =="56") {
        alert("全問正解おめでとう！！すごいよ" + name + "さん");
      }
    }
  }
</script>
```
```
<script>
  if("テントくん" == "テントくん"||"テントくん"!= "パオちゃん"){
    alert("正しいよ");
  }else{
    alert("正しくないよ");
  }
</script>
```
```
<script>
  var menseki = prompt("たて3センチ、よこ4センチの四角形の面積は？");
  var seikai = 3 * 4;
  if(menseki == seikai){
    alert("正解。");
  }else{
    alert("残念。正解は、" + seikai + "平方センチメートルです。");
  }
</script>
```
```
<script>
  var keisan1 = prompt("3 + 52 = ?");
  var seikai1 = 3 + 52;
  if(keisan1 == seikai1){
    alert(keisan1 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai1 + "です。");
  }
  var keisan2 = prompt("596 - 493 = ?");
  var seikai2 = 596 - 493;
  if(keisan2 == seikai2){
    alert(keisan2 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai2 + "です。");
  }
  var keisan3 = prompt("123 × 4 = ?");
  var seikai3 = 123 * 4;
  if(keisan3 == seikai3){
    alert(keisan3 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai3 + "です。");
  }
  var keisan4 = prompt("121 ÷ 11 = ?");
  var seikai4 = 123 / 4;
  if(keisan4 == seikai4){
    alert(keisan4 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai4 + "です。");
  }
  var keisan5 = prompt("100メートルを10秒で走る人の速さは時速？キロメートルですか。");
  var seikai5 = 100 / 10 * 60 *60 / 1000;
  if(keisan5 == seikai5){
    alert(keisan5 + "です。正解。");
  }else{
    alert("残念。正解は、時速" + seikai5 + "キロメートルです。");
  }
</script>
```
名前聞いて、最後褒めちぎるように。  
```
<script>
  var name = prompt("おなまえは？");
  var keisan1 = prompt("3 + 52 = ?");
  var seikai1 = 3 + 52;
  if(keisan1 == seikai1){
    alert(keisan1 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai1 + "です。");
  }
  var keisan2 = prompt("596 - 493 = ?");
  var seikai2 = 596 - 493;
  if(keisan2 == seikai2){
    alert(keisan2 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai2 + "です。");
  }
  var keisan3 = prompt("123 × 4 = ?");
  var seikai3 = 123 * 4;
  if(keisan3 == seikai3){
    alert(keisan3 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai3 + "です。");
  }
  var keisan4 = prompt("121 ÷ 11 = ?");
  var seikai4 = 121 / 11;
  if(keisan4 == seikai4){
    alert(keisan4 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai4 + "です。");
  }
  var keisan5 = prompt("100メートルを10秒で走る人の速さは時速？キロメートルですか。");
  var seikai5 = 100 / 10 * 60 *60 / 1000;
  if(keisan5 == seikai5){
    alert(keisan5 + "です。正解。");
  }else{
    alert("残念。正解は、時速" + seikai5 + "キロメートルです。");
  }
  if(keisan1 == seikai1 && keisan2 == seikai2 && keisan3 == seikai3 && keisan4 == seikai4 && keisan5 == seikai5) {
        alert("全問正解おめでとう！！すごいよ" + name + "さん!!!!");
      }
</script>
```
さて＠＠さん問題です！というダイアログ出すように  
```
<script>
  var name = prompt("おなまえは？");
  alert("さて" + name +"さん。問題です！");
  var keisan1 = prompt("3 + 52 = ?");
  var seikai1 = 3 + 52;
  if(keisan1 == seikai1){
    alert(keisan1 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai1 + "です。");
  }
  var keisan2 = prompt("596 - 493 = ?");
  var seikai2 = 596 - 493;
  if(keisan2 == seikai2){
    alert(keisan2 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai2 + "です。");
  }
  var keisan3 = prompt("123 × 4 = ?");
  var seikai3 = 123 * 4;
  if(keisan3 == seikai3){
    alert(keisan3 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai3 + "です。");
  }
  var keisan4 = prompt("121 ÷ 11 = ?");
  var seikai4 = 121 / 11;
  if(keisan4 == seikai4){
    alert(keisan4 + "です。正解。");
  }else{
    alert("残念。正解は、" + seikai4 + "です。");
  }
  var keisan5 = prompt("100メートルを10秒で走る人の速さは時速？キロメートルですか。");
  var seikai5 = 100 / 10 * 60 *60 / 1000;
  if(keisan5 == seikai5){
    alert(keisan5 + "です。正解。");
  }else{
    alert("残念。正解は、時速" + seikai5 + "キロメートルです。");
  }
  if(keisan1 == seikai1 && keisan2 == seikai2 && keisan3 == seikai3 && keisan4 == seikai4 && keisan5 == seikai5) {
        alert("全問正解おめでとう！！すごいよ" + name + "さん!!!!");
      }
</script>
```
# 繰り返し  
```
<script>
  var tasu = 1 + 2 + 3;
  alert(tasu);
</script>
```
```
<script>
  alert(1+2+3);
</script>
```
# for文  
```<script>
  var tasu = 0;
  for (var i = 1;i<= 10;i=i+1){
    tasu = tasu +i;
  }
  alert(tasu);
</script>
```
for(最初の式;条件の式；繰り返しの式）{  
繰り返すプログラム  
}  

変数用意してゼロ  
1スタートで、10までたす  
iが10より小さいか等しい間、繰り返しの処理を行う  
```
<script>
  var tasu = 0;
  for (var i = 1;i<= 100;i=i+1){
    tasu = tasu +i;
  }
  alert(tasu);
</script>
```
for(最初に変数iを1にする;i画100より小さいか等しい間;毎回１ずつ足す）{  
変数tasuとiを足して、もう一度tasuに入れる  
}  
