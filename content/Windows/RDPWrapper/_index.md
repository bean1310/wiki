---
title: "RDPWrapper"
date: 2019-01-13T20:00:04+09:00
draft: false
---

## これはなに？

Home EditionでもMicrosoftのリモートデスクトップをできるようにするもの.

- [GitHub](https://github.com/stascorp/rdpwrap)

## インストール方法

GitHubのReleasesのzip形式のものを落としてくる.

zip内のinstall.bat, update.batを叩く.

## アンインストール

zip内のuninstall.batを叩く

## 入ってるものの簡単な説明

RDPCheck.exeは自分にリモートデスクトップしに行く. これでRDPできるか確認できる.  
RDPConf.exeは詳細設定ができたり, 状態が見れたりする

{{<figure src="rdpconf.png" title="RDPConf.exe" alt="RDPConf.exeの画像">}}

diagnostics欄が全て緑色なら正常に動作してる.