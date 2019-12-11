---
title: "把使用 Yalu 來 JB 的 iOS 10 裝置開啟透過 WiFi 連接 SSH"
draft: false
date: 2017-08-28
tags: ["iOS", "Jailbreak"]
categories: ["科技新知"]
---

故事就是如果你用 Yalu 來 JailBreak 你的 iOS 10 設備，然後你會發現到用 WiFi 來接 SSH 怎麼樣都不會通，可是透過 USB 建立本地通道卻是可以連接 SSH 的。

<!--more-->

這其實不是設備壞了或是 JB 沒有處理好，而是 iOS 10 對於 OpenSSH 有相容性問題，所以作者改使用 dropbear 這套來代替，但是預設他只允許 127.0.0.1 的設備登入想當然的你用 WiFi 當然不會給你登入的。所以解法就是把 IPA 裡面的 Plist 修改後在重新簽署安裝。



## 教學

Yalu102 Beta7 的 MD5 值：bce2f84fc679a4e10a5a0c08e38e4fa7

Yalu102 Beta7 的下載點：[http://www.mediafire.com/file/v6on6gho64h3gnv/yalu102_beta7.ipa](http://www.mediafire.com/file/v6on6gho64h3gnv/yalu102_beta7.ipa)


把 Yalu 下載下來後，直接把副檔名從 .ipa 改成 .zip 並且解壓縮，這時候你會得到一個名為 Playload 的資料夾，然後點進去會看到一個名為 yalu102 的應用程式。


![](https://hiy.tw/tech/yalu_ios10_jb_wifi/1.png)



這時候在應用程式按右鍵選擇 *顯示套件內容*，然後找到 *dropbear.plist* 並且用 XCode 打開，這時候請把 ProgramArguments 的 Item 4 從 *127.0.0.1:22* 改成 *22* 然後存檔。



![](https://hiy.tw/tech/yalu_ios10_jb_wifi/2.png)




當確認修改且存檔完畢，在 Playload 資料夾按右鍵選擇 *壓縮『Payload』*，然後就會得到一個新的 Payload.zip 這時候請把副檔名從 .zip 改成 .ipa 然後就得到了一個新的 IPA 檔案。


![](https://hiy.tw/tech/yalu_ios10_jb_wifi/3.png)




這時候只要再使用 Cydia Impactor 來簽署憑證與安裝就可以讓 iOS 10 設備獲得透過 WiFi 登入 SSH 的功能了！

### 此外要記得，不要再從 Cydia 內安裝 OpenSSH 這會導致系統不定時的白蘋果重開

然後千萬記得，請修改預設密碼

#### 然後千萬記得，請修改預設密碼

### 然後千萬記得，請修改預設密碼 

## 然後千萬記得，請修改預設密碼

# 然後千萬記得，請修改預設密碼


超重要所以說五次，千萬不要使用預設密碼在外面裸奔！


參考資料：

[http://www.idownloadblog.com/2017/07/12/configure-ssh-extra_recipe-yalu-jailbreak/](http://www.idownloadblog.com/2017/07/12/configure-ssh-extra_recipe-yalu-jailbreak/)






