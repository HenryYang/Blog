---
title: "手動建立 FileVaultMaster.keychain 來設定 FileVault 恢復密鑰"
draft: false
date: 2018-04-09
tags: ["macOS", "FileVault", "Keychain"]
---


故事很簡單，就是過去可以透過預先建立好 FileVaultMaster.keychain，這樣當設備交給使用者後就算它們想啟用 FileVault2 也都會使用管理員預先指派好的密鑰。這就不會有當設備轉移時但密碼忘記所以無法把檔案找回來的問題。

<!--more-->

可是，在如果依照蘋果[官方的教學](https://support.apple.com/zh-tw/HT202385) 會發現到 macOS 10.13 後就無法設定主要密碼。所以就無法以 GUI 環境來達成了。因此這篇就是教學如何透過 CLI 來完成。

<center>
![](https://hiy.tw/coding/filevaultmaster_keychain/1.png)
</center>




其中官方文件在 "建立主要密碼與專用的恢復密鑰" 所說的 1 ~ 6 步驟，就只要濃縮成

第一步，產生帶有密碼的密鑰。就請記得第一組輸入的是電腦的密碼，然後接下來的兩個是加密密鑰想設定的密碼

`security create-filevaultmaster-keychain /Library/Keychains/FileVaultMaster.keychain`


第二步，把剛剛產生出來的密鑰解密。解密完後的密鑰就可以接者官方教學的 "更新與部署 FileVault 主鑰匙圈" 部分繼續執行拉。

`security unlock-keychain /Library/Keychains/FileVaultMaster.keychain`



參考資料：

[為機構內的 Mac 電腦設定 FileVault 恢復密鑰](https://support.apple.com/zh-tw/HT202385)

[FileVault 2 Institutional Recovery Keys](https://derflounder.wordpress.com/2014/08/13/filevault-2-institutional-recovery-keys-creation-deployment-and-use/)



