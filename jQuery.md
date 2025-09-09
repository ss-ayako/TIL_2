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
hasClassメソッドは、引数に指定したクラスを、オブジェクトが持っているか判定するときに使用  
```
// FAQのアコーディオン
  $('.faq-list-item').click(function() {
    var $answer = $(this).find('.answer');
    if($answer.hasClass('open')) { 
      $answer.removeClass('open');
      // slideUpメソッドを用いて、$answerを隠してください
      $answer.slideUp();

      // 子要素のspanタグの中身をtextメソッドを用いて書き換えてください
       $(this).find('span').text('+');
      
    } else {
      $answer.addClass('open'); 
      // slideDownメソッドを用いて、$answerを表示してください
     $answer.slideDown();
      
      // 子要素のspanタグの中身をtextメソッドを用いて書き換えてください
       $(this).find('span').text('-');
      ```
```
.text-active {            
 display: block;            
 }
```
```
 $('.faq-list-item').click(function() {
  var $answer = $(this).find('.answer');
    if ($answer.hasClass('open')) {
      $answer.removeClass('open');
    } else {
      $answer.addClass('open');
    }
  }); 
  ```
```
$(function() {
  $('#second-btn').click(function() {
    // 「.active」要素からactiveクラスを取り除いてください
    $('.active').removeClass('active')
    
    // 2つ目の「.slide」要素にactiveクラスをつけてください
    $('.slide').eq(1).addClass('active')
    
  });
});
```
```
$(function() {
  $('.index-btn').click(function() {
    $('.active').removeClass('active');
    
    // 変数clickedIndexを定義し、クリックしたボタンのインデックス番号を代入してください
     var clickedIndex = $('.index-btn').index($(this));
    
    // eqの引数をclickedIndexに書き換えてください
    $('.slide').eq(clickedIndex).addClass('active');
    
  });
});
```
```
$(function() {
  $('.index-btn').click(function() {
    $('.active').removeClass('active');
    var clickedIndex = $('.index-btn').index($(this));
    $('.slide').eq(clickedIndex).addClass('active');
  });
  
  $('.change-btn').click(function() {
    // 変数$displaySlideを定義してください
    var $displaySlide = $('.active');
    
    // 変数$displaySlideからactiveクラスを取り除いてください
    $displaySlide.removeClass('active');
    
    // ifとelseを用いて、$displaySlideの前もしくは次の要素に
    // activeクラスをつけてください
    if ($(this).hasClass('next-btn')) {
      $displaySlide.next().addClass('active');
    } else {
      $displaySlide.prev().addClass('active');
    }
  });
});
```
```
$(function() {
  $('.index-btn').click(function() {
    $('.active').removeClass('active');
    var clickedIndex = $('.index-btn').index($(this));
    $('.slide').eq(clickedIndex).addClass('active');
    
    // 1. 変数slideIndexに「.active」要素のインデックス番号を代入してください
    var slideIndex = $('.slide').index($('.active'));
    
    // 3. change-btn要素を表示してください
    $('.change-btn').show();
    
    // 2. ifとelse ifを用いて、「.change-btn」の表示/非表示をおこなってください
     if (slideIndex == 0) {
      $('.prev-btn').hide();
    } else if (slideIndex == 3) {
      $('.next-btn').hide();
    }
    
  });
  
  $('.change-btn').click(function() {
    var $displaySlide = $('.active');
    $displaySlide.removeClass('active');
    if ($(this).hasClass('next-btn')) {
      $displaySlide.next().addClass('active');
    } else {
      $displaySlide.prev().addClass('active');
    }
    
    // 「.index-btn」のクリックイベントと同様の処理を記述してください
     var slideIndex = $('.slide').index($('.active'));
    $('.change-btn').show();
    if (slideIndex == 0) {
      $('.prev-btn').hide();
    } else if (slideIndex == 3) {
      $('.next-btn').hide();
    }
    
  });
});
```
```
$(function() {
  
  // 「#form」要素のsubmitイベントを作成してください
  $('form').submit(function(){
    
  var textValue = $('#text-form').val();
  $('#output-text').text(textValue);
  return false;
  });
    
});
```
```
$(function() {
  $('#form').submit(function() {
    // 変数selectValueを定義してください。
    var selectValue = $('#select-form').val();
    
    var textValue = $('#text-form').val();
    // 「#output-select」要素のテキストを変数selectValueの値で書き換えてください。
    $('#output-select').text(selectValue);
    
    $('#output-text').text(textValue);
    return false;
  });
});
```
```
$(function() {
  $('#form').submit(function() {
    var selectValue = $('#select-form').val();
    var textValue = $('#text-form').val();
    
    // textValueが空のとき、エラー文を表示してください
    if(textValue == '') {
      $('#error-message').text('理由を記入してください');
 } else {
      $('#error-message').text('');
    }
    $('#output-select').text(selectValue);
    $('#output-text').text(textValue);
    return false;
  });
});
```
