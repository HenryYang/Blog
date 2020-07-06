---
title: "用 SSH 搭配 Public Key 登入 Windows 10"
draft: false
date: 2020-07-06
tags: ["PIV", "Yubikey"]
categories: ["程式技術"]
---

Windows 10 其實是可以透過 SSH 登入到 cmd 的，但是步驟跟正常想的有點不一樣

<!--more-->



## 教學

首先要安裝 OpenSSH Server 並且啟用服務

1. 開始 -> 設定 -> 應用程式與功能 -> 選用功能

![](https://hiy.tw/coding/win10_ssh/1.jpeg)

2. 新增 『OpenSSH 服務器』

![](https://hiy.tw/coding/win10_ssh/2.jpeg)

3. 控制台 -> 系統管理工具 -> 服務，把『OpenSSH SSH Server』與『OpenSSH Authentication Agent』都啟動

![](https://hiy.tw/coding/win10_ssh/3.jpeg)

這樣就做完了 OpenSSH Server 的設定了，接下來設定 Public Key 的部分

請注意，如果是具有管理員的帳號是需要依照下面設定在特殊的地方，並非在家目錄

1. 請把 Public Key 放在 `C:\ProgramData\ssh\` 下，並且檔案請命名為 `administrators_authorized_keys`

2. 因為他需要設定 ACL 讓只有 Administrators 群組與 SYSTEM 能存取，所以請用管理員權限的 powershell 執行下方指令。

![](https://hiy.tw/coding/win10_ssh/4.png)

```
$acl = Get-Acl C:\ProgramData\ssh\administrators_authorized_keys
$acl.SetAccessRuleProtection($true, $false)
$administratorsRule = New-Object system.security.accesscontrol.filesystemaccessrule("Administrators","FullControl","Allow")
$systemRule = New-Object system.security.accesscontrol.filesystemaccessrule("SYSTEM","FullControl","Allow")
$acl.SetAccessRule($administratorsRule)
$acl.SetAccessRule($systemRule)
$acl | Set-Acl
```

3. 這樣就可以登入了



參考資料：

[https://www.concurrency.com/blog/may-2019/key-based-authentication-for-openssh-on-windows](https://www.concurrency.com/blog/may-2019/key-based-authentication-for-openssh-on-windows)

[https://kheresy.wordpress.com/2017/12/14/windows-begin-to-provide-ssh-client-and-server/](https://kheresy.wordpress.com/2017/12/14/windows-begin-to-provide-ssh-client-and-server/)






