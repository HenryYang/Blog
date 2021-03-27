---
title: "各種取得 iOS App 的原始 .ipa 檔案的方法 (包括取得 TestFlight 版本)"
draft: false
date: 2021-03-27
tags: ["app", "jailbreak", "ios"]
categories: ["程式技術"]
---


想要 .ipa 檔案的理由很多，可能是怕開發者就這樣下架了有可能是其他原因。

總之，就來看看我們有啥選擇吧

<!--more-->


### 情境1 : 如果該 App 其實有正式上架到 App Store 且接受下載最新版本


其實這解法超簡單的，我個人是強力推薦使用 [iMazing](https://imazing.com/ios-app-management) 這套軟體

他 Windows 與 MacOS 版本都有，只需要把手機插上電腦執行它，他就可以幫你下載你曾經購買過的 App 的最新版 .ipa 檔到電腦

然後他也可以幫你安裝至手機中，只要你有當時下載 .ipa 檔所關連的 Apple ID 帳號密碼，這時候你想要安裝到那邊都是可以的。


詳細教學連結：https://imazing.com/guides/how-to-manage-apps-without-itunes



### 情境2 : 雖然有上架到 App Store 但我就是需要下載舊版本的


這種就麻煩很多了，然後網路上的教學大概分成三類

* 使用第三方的下載器 （不推薦）
* 在 Windows 下攔截封包修改資料騙舊版 iTunes 下載 （最穩但麻煩）
* 在 MacOS 下攔截封包修改資料騙舊版 iTunes 下載 （我沒成功過）


這邊的思路其實都是一樣的，就是透過舊版還可以下載 .ipa 版本的 iTunes，然後故意讓他回傳一個錯誤版本的訊息給蘋果的伺服器

就可以下載到一個有經過蘋果簽署自己的 Apple ID 的合法且舊版的 .ipa 檔回來。

唯一的差異就是第三方的下載器把全部需要手工的部分給自動化處理掉了，但是風險就是他有沒有可能會把軟體加料沒人知道，所以不推薦

至於 Windows 比 MacOS 方便的地方是因為新版的 MacOS 已經沒有內建 iTunes 所以降版起來更是麻煩。


Windows 教學：[https://zhuanlan.zhihu.com/p/101541667](http://webcache.googleusercontent.com/search?q=cache:66AvN_1oLEYJ:https://zhuanlan.zhihu.com/p/101541667&hl=zh-TW&gl=tw&strip=1&vwsrc=0)

第三方的下載器（不推薦）：[https://www.52pojie.cn/thread-742414-1-5.html](https://webcache.googleusercontent.com/search?q=cache:-UIovfHv7oUJ:https://www.52pojie.cn/thread-742414-1-1.html+&cd=1&hl=zh-TW&ct=clnk&gl=tw)


### 情境3 : 想要下載的 App 只有出現在 TestFlight 上


查過了網路上，基本上所有的說法都是無法直接下在拿到 TestFlight 版本的 .ipa 檔案。

所以這時候的思路只能轉回來從手機端匯出了。當然從手機端處理就表示需要把手機給 JB 了，而這風險當然也是需要自負的。


P.S. 目前 App Store 版本的 TestFlight 需要 iOS 13 才能安裝，如果使用的裝置是 iOS 12 或是更舊，請安裝 2.7.0 版本的 TestFlight

##### App Store 降版工具 - 「AppStore++」

* 軟體源：「http://cokepokes.github.io」
* 用法：在 App Store 中選擇要下載的 App 長壓下載或是打開，選擇「Upgrade/Downgrade」就可以手動升降 App 版本


##### 匯出 .ipa 檔案工具（未解密） - 「Ext3nder Installer」

* 軟體源：「https://julioverne.github.io/」
* 用法：打開後先選擇「更多」，然後把「Show User Applications」打開。這時候回到「已安裝」點選想要的 App 後選「Rebuild To .ipa」就可以了
* 檔案存放位置： `/var/mobile/Douments/Ext3nder`


##### 匯出 .ipa 檔案工具（有解密） - 「CrackerXI+」

* 軟體源：找不到官方的，請自行尋找
* 用法：打開後先選擇「Settings」，然後把「CrackerXI Hook」打開。這時候回到「AppList」點選想要的 App 後選「YES, FULL IPA」就可以了
* 檔案存放位置： `/var/mobile/Documents/CrackerXI`


參考資料

https://github.com/BishopFox/bfinject

https://www.mdeditor.tw/pl/pi59/zh-tw

https://www.reddit.com/r/jailbreak/comments/eayke0/help_how_to_export_an_app_as_ipa/

https://mrmad.com.tw/app-store-plusplus


