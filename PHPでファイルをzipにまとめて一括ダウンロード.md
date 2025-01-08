PHPでファイルをzipにまとめて一括ダウンロード  
```
// Zipクラスロード
$zip = new ZipArchive();
// Zipファイル名
$zipFileName = "file_" . date("Ymds") .'.zip';
// Zipファイル一時保存ディレクトリ
$zipTmpDir = '/tmp/zip/';
```
