```
$(function() {
  // 「.list-item」要素に対するclickイベントを作成してください
  $('li').click(function(){
    $(this).css('color','red');
 });
  
});
```
ライブラリー
```
$(function() {
  // 「#language-wrapper」にhoverしたときのhoverイベントを作成してください
 $('#language-wrapper').hover(
    function() {
      $('.language-text').fadeIn();
    },
    function() {
      $('.language-text').fadeOut();
    }
  );
  
});
```
```
  <!-- scriptタグを用いて、script.jsを読み込んでください -->
  <script src="script.js"></script>
```
```
$(function() {
  // 「#login-show」要素に対するclickイベントを作成してください
  $('#login-show').click(function(){
   $('#login-modal').fadeIn(); 
  });
  
});
```
