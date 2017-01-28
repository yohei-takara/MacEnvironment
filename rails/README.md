# Mac Rails 開発環境構築手順

1. 事前準備

  Homebrew の install

  ```
  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

  path設定

  ```
  echo 'export PATH=/usr/local/bin:$PATH' >> .bash_profile
  source .bash_profile
  ```

  最新パッケージリスト取得

  ```
  brew update
  ```

  MySQL の install

  ```
  brew install mysql
  ```

2. rbenv の install  

  _rbenv で ruby を 複数バージョン共存させられるようにする_

  ```
  brew install rbenv
  brew install ruby-build
  brew install rbenv-gemset
  brew install rbenv-gem-rehash
  ```

  必要があればPATHを通す

  ```
  echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
  echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
  ```

  rbenvの確認  

  ```
  rbenv --version          # => バージョン確認
  rbenv install --list     # => インストール可能なバージョン一覧の表示
  rbenv install [バージョン] # => rubyのインストール
  rbenv global [バージョン]  # => defaultで使用するrubyのバージョン
  ```

3. rbenv で ruby を install  
 ```
 rbenv install 2.2.3  # => 最新バージョンのRuby をinstall  
 rbenv global 2.2.3   # => rbenv で 使用する Rubyのversionを指定する  
 ```

4. Gem で Bundler を install  
  _bundler を install する前に、必要のないgemをuninstallしておく_  
  ```
  gem uninstall -axI `gem list --no-versions | egrep -v 'test-unit|rdoc|psych|minitest|io-console|rake|bigdecimal|json'`
  ```
  ```
  gem install bundler
  ```

  >Gemパッケージとは

  >まずはGemパッケージの簡単な解説です。

  >Rubyで使われるライブラリやアプリケーションはGemと呼ばれる形式のパッケージにすることができます。多くのライブラリがGem形式でパッケージされ公開されており、これらはRubyGemsと呼ばれるパッケージ管理ツールを使ってダウンロードを行なったりインストールすることができます。これらのパッケージのことを単にGemとかGemパッケージなどと呼んだりします。

  >Bundlerとは

  >Railsのアプリケーション開発を複数のPCで行なおうとした場合を考えてみます。プログラムファイルはもちろんですが、全てのPCで対象のアプリケーションで使用しているGemパッケージをインストールしておかなければなりません。またGemパッケージのバージョンも揃える必要があります。

  >そこで使われるのがBundlerです。BundlerはRailsアプリケーションに必要となるGemパッケージの種類やバージョンを管理し、複数のPCで必要なGemパッケージをインストールする仕組みを提供してくれます。

5. bundler による gem の管理

 Gemfile の作成

 ```
 bundle init
 ```

 Gemfile に 記載されている gem の install を行う。  
 Project 毎にgem の管理を行えるように、install 先を指定する。

 ```
 bundle install --path vendor/bundle
 ```

6. Rails project の 作成

 使用する DB を MySQL でアプリを作成する。  

 ```
 bundle exec rails new アプリ名 --skip-bundle -d mysql
 ```

7. DB の設定

  config/databases.yml に記載
  
  >adapter: 使用するデータベース種類  
  >encoding: 文字コード  
  >reconnect: 再接続するかどうか  
  >database: データベース名  
  >pool: コネクションプーリングで使用するコネクションの上限  
  >username: ユーザー名  
  >password: パスワード  
  >host: MySQLが動作しているホスト名  
