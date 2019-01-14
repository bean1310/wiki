---
title: "Program Files内を編集する"
date: 2019-01-13T19:31:38+09:00
draft: false
---

Program Files内を編集するとなると管理者権限でもダメって言われるのでその対処法

`C:\Program Files\RDP Wrapper\rdpwrap.ini`を編集するとするとき

`C:\Program Files\RDP Wrapper`のプロパティのセキュリティタブの詳細設定を開いて上に表示されている所有者を自分のアカウント（CMD.exe で`whoami`するとわかる or マイクロソフトアカウントなら***@outlook.comなど）に変更する.

そのあと詳細設定の画面でUsersにフルコントロール権限を与える.（AdministratorだけどAdministratorsに権限付与してても編集できなかったのでこの方式）

これで編集可能になるはず.

編集を終えたら権限など元に戻しておく.