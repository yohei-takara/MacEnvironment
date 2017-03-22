# Mac環境構築でやる事

## Homebrew の Install

[Homebrew](http://brew.sh/index_ja.html)

```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Homebrew-cask の install

[Homebrew Cask](https://caskroom.github.io/)

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
$ brew install kotlin
```

## 下記をbrew cask で install

```
$ brew cask install iterm2
$ brew cask install atom
$ brew cask install google-chrome
$ brew cask install java
$ brew cask install sourcetree
$ brew cask install sequel-pro
$ brew cask install virtualbox
$ brew cask install vagrant
$ brew cask install docker
$ brew cask install rubymine
```

# Homebrew で 配布されていないものについて

[SimpleDiagrams](http://www.simplediagrams.com/)
