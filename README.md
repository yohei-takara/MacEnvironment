# Mac環境構築でやる事

## Homebrew の Install

[Homebrew](http://brew.sh/index_ja.html)

```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

~## Homebrew-cask の install~

~[Homebrew Cask](https://caskroom.github.io/)~


```
$ brew tap caskroom/cask
```

## Homebrew Cask で別versionをinstall できるようにする

[homebrew-cask-versions](https://github.com/caskroom/homebrew-versions)

```
$ brew tap caskroom/versions
```

## Homebrew パッケージ情報の更新

Homebrew-cask の パッケージ情報も更新される

```
$ brew update
```

## 下記をbrew で install

```
$ brew install zsh
$ brew install zplug

$ brew install kotlin
```

## 下記をbrew cask で install

```
$ brew cask install iterm2
$ brew cask install atom
$ brew cask install google-chrome
$ brew cask install clipy

$ brew cask install virtualbox
$ brew cask install vagrant
$ brew cask install docker
$ brew cask install docker-edge

$ brew cask install sourcetree
$ brew cask install sequel-pro
$ brew cask install java
$ brew cask install intellij-idea
$ brew cask install rubymine
```

# Homebrew で 配布されていないものについて

[SimpleDiagrams](http://www.simplediagrams.com/)


# ssh 

鍵作成
`-f` optionで、生成する鍵を任意の名前で作成可能
```
$ ssh-keygen -t rsa -f <path>
```

_ssh config_
```
# --- GitHub setting ---
Host github.com
  HostName github.com
  User <user name>
  PreferredAuthentications publickey
  IdentityFile <GitHub に登録している 公開鍵のペアとなる秘密鍵の path>
  UseKeyChain yes
  AddKeysToAgent yes
# ----------------------------

# --- bitbucket setting ---
Host bitbucket.org
  HostName bitbucket.org
  IdentityFile <bitbucket に登録している 公開鍵のペアとなる秘密鍵の path>
  User <User name>
  Port 22
  TCPKeepAlive yes
  IdentitiesOnly yes
# ----------------------------
  
```

_github接続確認_
`$ ssh -T git@github.com`

_bitbucket ssh 接続確認_
`$ ssh -T bitbucket.org`
