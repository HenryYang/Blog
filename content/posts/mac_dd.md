---
title: "APFS 格式的 MacOS 系統硬碟對拷"
draft: false
date: 2019-05-09
tags: ["MacOS"]
categories: ["程式技術"]
---

以前當需要轉移 MacOS 系統時就是拿一條 Thunderbolt 線插在兩台 Mac 上面，然後要當外接硬碟的重開機按住 T 變成磁碟模式，這時候就可以打開磁碟管理程式透過回復來把資料完整備份到另外一臺上。

<!--more-->

但是在 macOS 10.13 後只要是 SSD 都會被格式化成 APFS 格式，然後[網路上就有很多災情](https://discussions.apple.com/thread/8340855)說不能複製會出現各種錯誤，我自己是出現 ERROR 28。據有經驗的朋友表示，這是 APFS 的格式有部分損壞或是磁碟管理程式的版本不對所造成的。


![](https://hiy.tw/tech/mac_dd/1.jpg)


而目前的解法有兩大類，一個是先把磁碟封裝成 DMG 再回復回去。另外一種則是用第三方軟體複製。我自己的解法是用後者。


### [Carbon Copy Cloner](https://bombich.com/download)


![](https://hiy.tw/tech/mac_dd/2.jpg)


這套軟體雖然是付費軟體，但是它可以試用 30 天。這用來硬碟對拷非常足夠，它的 UI 也非常簡單，先選來源磁區，再選目標磁區然後按下 Clone 就開始跑了。我自己的兩台 Mac 都是 2014 年的然後走 Thunderbolt 2 傳輸，看起來每 10 分鐘可以跑 25 GB 左右，我個人覺得是蠻快的複製。


![](https://hiy.tw/tech/mac_dd/3.jpg)



等複製完後，電腦重開確定可以進去系統就可以拉！


![](https://hiy.tw/tech/mac_dd/4.jpg)







