---
title: "iOS 簡訊轉移到 Android 教學（附註 iOS 11 問題處理）"
draft: false
date: 2017-08-13
tags: ["Andorid", "ios", "iSMS2droid", "sms"]
---

### 轉移概念：

iOS 裝置插電腦用 iTunes 備份同步，然後把備份完的 SQLite 檔案複製出來並複製到 Android 手機，用 iSMS2droid 把檔案回復回去，就完了。

<!--more-->

### 操作步驟：

#### Step1：把加密關閉後備份整台手機

<center>
![](https://hiy.tw/tech/ios_sms_to_android/1.png)
</center>

#### Step2：找出備份檔案的路徑

Windows 路徑是：C:\Users\[YourUsername]\AppData\Roaming\Apple Computer\MobileSync\Backup\

macOS 路徑是： ~/Library/Application Support/MobileSync/Backup/

然後如果有多個資料夾請看資料夾哪一個是最近有被更動過的那就是你剛剛備份的。然後進入資料夾後把檔名為 3d0d7e5fb2ce288813306e4d4636395e047a3d28 的檔案複製到 Android 手機中

#### Step3：安裝 iSMS2droid 並回復上面說的那個檔案

Google Play 下載位置：https://play.google.com/store/apps/details?id=org.faked.isms2droid

#### Step4：回復完就一切完成了




### 但...當然一切沒有這麼簡單


* 記得 iTunes 備份要把加密關閉不然 iSMS2droid 無法開啟
* 如果是 iOS 11 回復完會出現靈異狀況


然後經過研究後發現，如果系統是 iOS 11 備份出來的 SQLite 不知道為什麼在 date 欄位都會被補上 9 個 0，所以匯入到 Android 後就會變成西元 40000 多年，然後簡訊的 App 就會卡住。

<center>
![](https://hiy.tw/tech/ios_sms_to_android/2.png)
</center>

所以需要用任何一套能編輯 SQLite 的軟體來處理都好，我自己是用 Firefox 的 Add-on：[SQLite Manager](https://addons.mozilla.org/en-US/firefox/addon/sqlite-manager/) 來處理。

所以作法就是下這段 SQL 指令 `update message set date = date / 1000000000;` 這樣就最簡單把所有的 date 都去除 9  個 0 然後再把這 SQLite 檔案匯入到 Android 用 iSMS2droid 就一切正常了。

註：然後我也不知道為什麼 iOS 資料庫存的時間戳記跟 Epoch time 整整快了 31 年，真的超級有趣的。








