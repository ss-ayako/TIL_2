- 文字列表示　window.document.write()  
- ダイアログボックス表示 window.alert()  
- クリックされた時のイベントハンドラ onclick
- マウスカーソルが通過した時のイベントハンドラ onmouseover
- 複数の文を指定することもできる
- 例えば、
  ```
  <input type="button" value="ボタン"
  onclick="alert('いらっしゃいませ');alert('ご注文は？')">
  ```
- オブジェクトの状態を表すプロパティ
- オブジェクトに対する処理メソッド
- HTMLファイルから外部Javascriptファイルを読み込む
- Javascriptファイルを別に作成しておき<script>タグでそのファイルの場所指定
- 呼び出す方法３選　bodyタグの間に記述、<input>などの属性に記述、headタグの間に関数を記述
