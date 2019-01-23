---
title: "用 macOS Server 的 Profile Manager 部屬 FileVault 復原密鑰"
draft: false
date: 2018-10-04
tags: ["macOS", "FileVault","Profile Manager"]

---

簡單來說，就是在 10.12 之後就無法在 `系統偏好設定` 裡面的 `使用者與群組` 中建立 `主鑰匙圈 (Master Password)`

<!--more-->

所以就只好借用 CLI 的方式產生，詳細步驟可以參考下面的蘋果官方說明，這邊就指貼最關鍵的部分。

在終端機輸入下面指令

`security create-filevaultmaster-keychain ~/Desktop/FileVaultMaster.keychain`

這時候桌面上就會產生一組包含公私鑰的主鑰匙，請務必備份好，未來如果要解密時會需要。

把剛剛產生的主鑰匙點兩下就會把私鑰與憑證匯入到電腦的 Keychain 中，這時候對憑證按右鍵匯出成 DER 出來即可。

接下來請參考下面的英文網站的第 16 部開始，把剛剛產生的 DER 憑證上傳到 MDM Server 就可以開始部屬使用機構復原密鑰的  FileVault  （灑花）

<center>
![](1.png)
</center>


P.S. 想問大家的是，請問有沒有人預過每部屬一次新的設備 DER 就要重新上傳一次的經驗？我自己會遇到在選擇憑證的時候每次重新整理清單就會消失然後部屬就會失敗，想尋求大家的經驗 QQ



參考資料

https://support.apple.com/zh-tw/HT202385

https://www.danielsellers.com/blog/2017/1/23/set-a-filevault-recovery-key-for-mac-computers-in-your-institution

