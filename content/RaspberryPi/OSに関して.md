+++
title = "OSに関して"
+++
## Raspbian

どうも3つにバージョンが分かれたらしい

日本のミラーサイトのURL

- [Raspbian Stretch with desktop and recommended software](http://ftp.jaist.ac.jp/pub/raspberrypi/raspbian_full/images/)
- [Raspbian Stretch with desktop](http://ftp.jaist.ac.jp/pub/raspberrypi/raspbian/images/)
- [Raspbian Stretch Lite](http://ftp.jaist.ac.jp/pub/raspberrypi/raspbian_lite/images/)

## 焼き方

公式サイトの手順: [Installing operating system images](https://www.raspberrypi.org/documentation/installation/installing-images/)

ただ`sudo dd`するのめんどくさいので[Etcher](https://www.balena.io/etcher/)を使う方が楽.

### mac

```
brew cask install balenaetcher
```