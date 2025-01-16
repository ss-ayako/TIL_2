1. 環境構築を始める準備
***
Pythonがインストールされているか？  
```
 % python --version
zsh: command not found: python
```
ターミナルに zsh: command not found: python と表示された人はまだPythonがインストールされていません  
「pyenv」というツールを用いて、「3系」のPythonをインストールする
***
今後の流れ  
「Homebrew」をインストールする  
「Homebrew」を用いて「pyenv パイエンブ」をインストールする  
「pyenv」を用いてPythonをインストールする 
***
「Homebrew」インストールされてるか？
```
brew -v
```
Homebrew 4.2.0  
インストールされてた  
***
pyenvがインストールされていないことを確認  
```
pyenv -v
```
zsh: command not found: pyenv   
インストールされていない 
pyenvをインストール
```
brew install pyenv
```
インストールされたか確認  
```
pyenv -v
```
pyenv 2.5.0  
***
pyenvを使用してPythonをインストールする、その前にインストールしたpyenvの設定  
以下のコマンドを実行すると、pyenvの初期化の設定を.zshrcファイルに書き込むことができる  
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc  
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc  
echo 'eval "$(pyenv init -)"' >> ~/.zshrc  
source ~/.zshrc  
これでpyenvの設定は完了！  
***
インストールしたpyenvを用いてPythonをインストール  
```
pyenv install --list
```
現在インストールが可能なPythonのバージョン  
***
pyenv install 3.10.4インストール  
```
pyenv install 3.10.4
```
