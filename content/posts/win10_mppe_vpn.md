---
title: "Windows 10 遇到 MPPE 加密時的 PPTP VPN 設定"
draft: flase
date: 2019-05-13
tags: ["VPN", "Windows 10"]
categories: ["科技新知"]
---

#### 我也不想用 PPTP VPN 啊，但希望總是無法實現

總之 Windows 預設的 PPTP 是有沒有加密都可以連線的，如果遇到伺服器強制需要 MPPE 加密，這時候就會連不上。

解決方法就是進到控制台，去該 PPTP 連線設定值中的安全性，把資料加密改成『需要加密』，並且下面選項照圖片勾選。

這樣就會可以連線了!



![](https://hiy.tw/tech/win10_mppe_vpn/01.png)





