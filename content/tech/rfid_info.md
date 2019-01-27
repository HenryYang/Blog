---
title: "RFID 感應卡冷知識整理"
draft: false
date: 2017-03-05
tags: ["RFID"]
---


以下會記錄一些常見的 RFID 相關冷知識

<!--more-->

<center>
![](1.jpg)
</center>

[CC By Scott Lewis](https://www.flickr.com/photos/99781513@N04/14891130616)

### 簡易快速判斷門禁系統使用的種類

* 如果門禁系統刷悠遊卡或是一般常見的卡片有反應就代表他支援的有 Mifare 卡，而且很有可能是只驗證 UID
* 如果門禁系統可以登記悠遊卡或是一般常見的卡片來當作門禁卡，就代表一定是用 UID 來驗證使用者
* 只使用 UID 來驗證使用者的門禁系統我自己會是歸類在不安全的
* 如果門禁卡是很厚一張，然後上面也沒有 HID 字樣的，這通常會是 EM 卡
* 如果門禁卡上面有 HID 字樣的，那就是 HID 卡（廢話阿

### Mifare 卡 UID 的轉換

* 如果門禁系統有鍵盤而且沒有關閉然後又是用 UID 做驗證的，就可以把 16 進位的 UID 轉成 10 進位然後用鍵盤輸入就有機會驗證成功

[http://patricks.tw/MIDConv/](http://patricks.tw/MIDConv/)



未完待續...





