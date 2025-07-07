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
```
$(function() {
  $('#login-show').click(function(){
    $('#login-modal').fadeIn();
  });
  
  $('.signup-show').click(function(){
    $('#signup-modal').fadeIn();
  });
  
  // 「.close-modal」要素にclickイベントを設定してください
    $('.close-modal').click(function(){
    $('#signup-modal').fadeOut();
     $('#signup-modal').fadeOut();
  });
      
  
  
});
```
```
$(function() {
  
  $('#login-show').click(function() {
    $('#login-modal').fadeIn();
  });
  
  $('.signup-show').click(function() {
    $('#signup-modal').fadeIn();
  });

  $('.close-modal').click(function() {
    $('#login-modal').fadeOut();
    $('#signup-modal').fadeOut();
  });
  
  // 「.lesson-hover」がhoverされたときのhoverイベントを作成してください
   $('.lesson-hover').hover(
     function() {
     },
    function() {
     }
  ); 
  
  
});
```
```
$(function() {
  
  $('#login-show').click(function() {
    $('#login-modal').fadeIn();
  });
  
  $('.signup-show').click(function() {
    $('#signup-modal').fadeIn();
  });

  $('.close-modal').click(function() {
    $('#login-modal').fadeOut();
    $('#signup-modal').fadeOut();
  });
  
  // 「.lesson-hover」がhoverされたときのhoverイベントを作成してください
   $('.lesson-hover').hover(
     function() {
     },
    function() {
     }
  ); 
  
  
});
```
