# 今回のrails起動までの手順の復習
$ git --version -> 現在使用しているgitのversionの確認、git -vでも一緒の結果が得られる。</br>
$ git clone http:~ -> リモートリポジトリをローカルに複製するためのコマンド</br>
$ ruby -v -> rubyのversion確認</br>
$ rvm -h -> rvmはruby version managerの略。バージョンを管理し切り替えたりしてくれる。-hはヘルプメッセージを表示してくれる。</br>
$ rvm install 3.1.2 -> 特定のRubyバージョンをインストールするためのコマンド</br>
$ rvm user 3.1.2 -> インストールしたRubyバージョンを使用するためのコマンド</br>
$ docker system prune -a -> 空き容量を作るために不要なDockerシステム内の不要なデータを削除するために使用。</br>
* Dockerとはアプリケーションやそれに必要なものをコンテナと呼ばれる軽量なパッケージにまとめ、どこでも同じように実行できるようにするツールです。要するに、アプリケーションとその周辺環境をひとまとめにして、どこでも手軽に動かせる仕組みを提供しています。</br>
$ curl -fsSL https://raw.githubusercontent.com/MasatoshiMizumoto/raisetech_documents/main/aws/scripts/mysql_amazon_linux_2.sh | sh
-> curlコマンドはClient for URLsの略でデータを転送するためのツール。特にURLを使用してデータを取得や送信するのによく使われる。この場合、スクリプトはGitHub上のリポジトリから取得される。最後のshでダウンロードしたスクリプトが実行される。</br>
$ sudo cat /var/log/mysqld.log | grep "temporary password" | awk '{print $13}' -> 初期パスワードの確認
-> sudo は"superuser do"の略で特権（通常は管理者権限やルート権限）が必要なコマンドを一時的に実行するためのコマンド</br>
-> cat は"concatenate"（連結）の略。主にファイルの内容を表示したり、ファイル同士を連結したりするために使用される。</br>
 -> cat example.txt(表示）、cat file1.txt file2.txt > combined.txt（連結）
-> grep は強力なテキスト検索ツール</br>
 -> grep "search" example.txt これはexample.txtの中から"search"を検索</br>
-> awk はデータを受け取り、特定のパターンに一致する行やフィールドを抽出・処理する。</br>
 -> ここでは'{print $13}'　１３行目を抽出</br>
$ mysql -u root -p -> パスワードの設定とログイン。</br>
-> -u root: ユーザー名を指定します。この場合、rootというユーザーでログインしようとしているということ。</br>
-> -p: パスワードを入力するためにプロンプトが表示される。</br>
$ ALTER USER 'root'@'localhost' IDENTIFIED BY '設定するパスワード' -> 初期設定からパスワードを変更</br>
$ FLUSH PRIVILEGES; -> データベースサーバーに対して変更を適用するためにFLUSH PRIVILEGESを実行することにより変更が即座に反映され、ユーザーアカウントが正しく機能する。</br>
$ cd raisetech-live8-sample-app -> アプリのディレクトリへ移動</br>
$ cp config/database.yml.sample config/database.yml -> sampleのymlをコピーしてdatabaseに使うymlを作成</br>
* コピーしたdatabase.ymlに変更したパスワードを入力</br>
$ which mysql -> mysqlコマンドがどの場所にインストールされているかを表示するためのコマンド</br>
* socketを今回の仕様に変更 -> ソケットは、異なるプログラムやコンピュータがネットワークを介して通信するための手段。よくわからない。。。</br>
* node.js はJSのversionみたいなもの</br>
* nvm -> nvmはnode version managerの略。</br>
* yarn -> JavaScriptのパッケージ管理ツール、RubyにおけるbundlerがJSのyarnみたいなもの。</br>
