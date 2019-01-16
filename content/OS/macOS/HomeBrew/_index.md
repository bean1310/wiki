---
title: "HomeBrew"
date: 2019-01-16T17:38:37+09:00
draft: false
---

## コマンド

### updateとupgradeとcleanupする

環境変数`HOMEBREW_INSTALL_CLEANUP`に1を設定して`brew upgrade`すればcleanupもやってくれる.  
`brew upgrade --cleanup`と同様だけどこれは古い.

[Implement the HOMEBREW_INSTALL_CLEANUP env to trigger cleanup on reinstall/install/upgrade by Wojonatior · Pull Request #5165 · Homebrew/brew](https://github.com/Homebrew/brew/pull/5165)