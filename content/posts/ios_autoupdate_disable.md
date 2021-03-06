---
title: "讓舊版 iOS 無法自動更新（2019年適用）"
draft: false
date: 2019-03-24
tags: ["iOS", "Jailbreak"]
categories: ["科技新知"]
---

故事很簡單，就是 iOS 12 之後就已經支援不要讓系統自動更新到最新版的 iOS 功能。但是對於我這種需要留在 iOS 10 做測試的人就還是會很困擾。

<!--more-->

過去網路上的教學是安裝 tvOS 的測試用描述檔，安裝後會變成都抓 tvOS 的來源檔案，但是因為跟 iPhone 不同，這樣就會造成找不到更新版的問題。但這問題就是我們想達到的不要被更新的目的。

目前繁體中文的教學中都是提供舊版的 tvOS 11 測試用描述檔 ，因為時效已經過期所以無法再安裝了。

這邊我找到在 [https://betaprofiles.com/](https://betaprofiles.com/) 有提供目前最新的 tvOS 12 的測試用描述檔，所以只要安裝了它並重開就可以達到找不到更新的目的。


![](https://hiy.tw/tech/ios_autoupdate_disable/1.png)



此外，如果在安裝之前系統就偷偷的把更新檔下載下來，這時候系統還是會顯示立刻安裝。

請點選 `設定` -> `一般` -> `儲存空間與 iCloud 用量` -> `管理儲存空間`，找到 找到 iOS 更新檔，把它刪除後再重開機。這樣就完成了另類的關閉自動更新。



![](https://hiy.tw/tech/ios_autoupdate_disable/2.png)




