---
title: "Windowsをアップデートしたら使えなくなった場合の対処法"
date: 2019-01-13T20:04:53+09:00
draft: false
---

基本的にGitHubのIssuesなどを見て解決する.

おそらく`rdpwrap.ini`を編集して対処できる.

ここの編集は  
[Program Files内を編集する]({{%relref "Program Files内を編集する.md"%}})  
[所有者をTrustedInstallerに戻す方法]({{%relref "所有者をTrustedInstallerに戻す方法.md"%}})  
を参照.

で肝心のiniの書き換えだけど

[ここ](https://github.com/stascorp/rdpwrap/issues/601#issuecomment-448895969)のようにするのだと思う.

これを簡単に書くと
`rdpwrap.ini`に以下を追記

```
;-----------追記するもの その1 ------ [10.0.17763.1] セクションの後に追記 ------
[10.0.17763.168]
LocalOnlyPatch.x86=1
LocalOnlyOffset.x86=AFC74
LocalOnlyCode.x86=jmpshort
LocalOnlyPatch.x64=1
LocalOnlyOffset.x64=77AF1
LocalOnlyCode.x64=jmpshort
SingleUserPatch.x86=1
SingleUserOffset.x86=4D665
SingleUserCode.x86=nop
SingleUserPatch.x64=1
SingleUserOffset.x64=1322C
SingleUserCode.x64=Zero
DefPolicyPatch.x86=1
DefPolicyOffset.x86=4BE69
DefPolicyCode.x86=CDefPolicy_Query_eax_ecx
DefPolicyPatch.x64=1
DefPolicyOffset.x64=17F45
DefPolicyCode.x64=CDefPolicy_Query_eax_rcx
SLInitHook.x86=1
SLInitOffset.x86=5B18A
SLInitFunc.x86=New_CSLQuery_Initialize
SLInitHook.x64=1
SLInitOffset.x64=1ABFC
SLInitFunc.x64=New_CSLQuery_Initialize
;--------------追記ここまで-----------
;
;-----------追記するもの その2 ------ [10.0.17763.1-SLInit] セクションの後に追記 ------
;.
[10.0.17763.168-SLInit]
bInitialized.x86 =CD798
bServerSku.x86 =CD79C
lMaxUserSessions.x86 =CD7A0
bAppServerAllowed.x86 =CD7A8
bRemoteConnAllowed.x86=CD7AC
bMultimonAllowed.x86 =CD7B0
ulMaxDebugSessions.x86=CD7B4
bFUSEnabled.x86 =CD7B8

bInitialized.x64 =ECAB0
bServerSku.x64 =ECAB4
lMaxUserSessions.x64 =ECAB8
bAppServerAllowed.x64 =ECAC0
bRemoteConnAllowed.x64=ECAC4
bMultimonAllowed.x64 =ECAC8
ulMaxDebugSessions.x64=ECACC
bFUSEnabled.x64 =ECAD0
;---------追記ここまで --------------
```

この後Remote Desktop Serviceを再起動する.  
編集前に止めておいた方がいいかもしれない.  
CMD.exeを管理者権限で起動して
```
net stop TermService
net start TermService
```