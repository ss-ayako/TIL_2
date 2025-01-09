PHPでファイルをzipにまとめて一括ダウンロード  
```
// Zipクラスロード
$zip = new ZipArchive();
// Zipファイル名
$zipFileName = "file_" . date("Ymds") .'.zip';
// Zipファイル一時保存ディレクトリ
$zipTmpDir = '/tmp/zip/';
```
- コードの流れについておさらい

### 1. ユーザーがダウンロードボタンをクリック

* ブラウザがサーバーにリクエストを送信します。
* リクエストには、どのファイルをダウンロードしたいかなどの情報が含まれています。

### 2. サーバー側でPHPスクリプトが実行

1. **ZIPライブラリの読み込み:**
   * PHPには標準でZIPを扱う機能はありません。ZipArchiveクラスなどのライブラリを組み込みます。
2. **ZIPアーカイブの作成:**
   * ZipArchiveクラスのインスタンスを作成し、新しいZIPアーカイブを作成します。
3. **ファイルの追加:**
   * ダウンロードしたい動画ファイルのパスを指定し、ZIPアーカイブに追加していきます。
4. **ZIPアーカイブの保存:**
   * 作成したZIPアーカイブをサーバー上の任意の場所に保存します。
5. **ダウンロード処理:**
   * ヘッダー情報を設定し、ブラウザにZIPファイルをダウンロードさせるように指示します。

### 3. ブラウザでのダウンロード

* サーバーから送られてきたZIPファイルの情報を元に、ブラウザがダウンロード処理を開始します。
* ユーザーが指定した場所にZIPファイルが保存されます。

### コードの例 (簡易版)

```php
<?php
// ダウンロードするファイルのパスを配列に格納
$files = ['video1.mp4', 'video2.mp4', 'video3.mp4'];

// ZipArchiveクラスのインスタンスを作成
$zip = new ZipArchive();

// 一時的に保存するZIPファイル名
$zip_filename = 'videos.zip';

// ZIPアーカイブを作成
if ($zip->open($zip_filename, ZipArchive::CREATE) === TRUE) {
    foreach ($files as $file) {
        $zip->addFile($file, basename($file)); // ファイルを追加
    }
    $zip->close();

    // ダウンロード処理
    header('Content-Description: File Transfer');
    header('Content-Type: application/zip');
    header('Content-Disposition: attachment; filename=' . $zip_filename);
    header('Content-Length: ' . filesize($zip_filename));
    readfile($zip_filename);

    // 一時ファイルの削除（任意）
    unlink($zip_filename);
} else {
    echo 'ZIPアーカイブの作成に失敗しました。';
}
?>
```

### コード解説

* **ZipArchiveクラス:** PHPの標準ライブラリに含まれるZipArchiveクラスを使用することで、簡単にZIPファイルを作成できます。
* **addFileメソッド:** ZIPアーカイブにファイルを追加するメソッドです。
* **header関数:** HTTPヘッダーを設定し、ブラウザにファイルの情報を伝えます。
* **readfile関数:** ファイルの内容をブラウザに直接出力します。

### 注意点

* **セキュリティ:**
  - ダウンロードするファイルのパスを外部から直接入力させないように注意が必要です。
  - サーバーのセキュリティ設定も適切に行い、不正アクセスを防ぎましょう。
* **パフォーマンス:**
  * 大量のファイルをZIPに圧縮する場合、処理時間がかかることがあります。
  * サーバーの負荷に注意し、必要であれば非同期処理などを検討しましょう。
* **エラー処理:**
  * ZIPアーカイブの作成に失敗した場合など、エラーが発生する可能性も考慮し、適切なエラー処理を行いましょう。


