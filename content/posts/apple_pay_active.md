---
title: "Apple Pay 跨國啟用注意事項 (2017/04/20 更新)"
draft: false
date: 2017-04-20
tags: ["Apple Pay", "iOS", "iPhone", "Suica"]
---


今天跟朋友聊天發現到一些比較特殊的 Apple Pay 啟用狀況，怕忘記所以先筆記一下 :p

<center>
![](https://hiy.tw/tech/apple_pay_active/1.jpg)
</center>

<!--more-->

* 如果啟用外國信用卡的 Apple Pay 失敗時，請先嘗試把 iPhone 的地區調成該國家，如果還是不行請掛該國的 VPN。因為目前發現美國跟日本的有些發卡機構會檢查 IP 。
* 中國的 Apple Pay 不知道為什麼不用改地區也不用掛 VPN 就可以正常啟用
* 手機可以同時存在多個國家的 Apple Pay 卡片
* 如果想要在日版 Apple Watch 2 啟用 Suica 經過確認只需要把手錶的地區都改為日本然後就算沒有掛 VPN 現在Suica App 也以正常運作
* 日本 Apple Pay 中的 Suica 如果在使用 Suica App 產生時選擇無記名的，換手機時是無法轉換的，所以餘額就掰掰了。
* 用日本 iPhone 7/7 Plus 轉移實體卡的方式新增 Suica 的話，轉移成功後原本的卡就會失效，然後卡片資訊就會跟著 iCloud 跑
* 日本 Apple Pay 中的 Suica 可以使用台灣 JCB 卡付款或是使用手機內不同國家的 Apple Pay 付款（已經有人嘗試過用美國 Apple Pay 的卡來幫日本  Apple Pay 中的 Suica 加值成功，同理可證等台灣 Apple Pay 上市是有機會幫日本 Apple Pay 中的 Suica 加值）
* 日本 Apple Watch 2 的 NFC 是同時支援日本與國際標準的，所以不會有只能在日本境內用但不能在其他國家用的窘境
* 日本的感應支付都是支援 Type-F (除了 IKEA )，所以你需要 日本 iPhone 7/7 Plus 或是日本 AW2＋日本信用卡才感應使用。
* 台灣 Apple Pay 不會認地區與 IP ，所以在哪都可以啟用，如果手機沒有出現新增選項可以暫時把地區改為美國
* 如果是 iOS 9 用戶要新增台灣 Apple Pay 可以參考[此則教學](https://note.hy31.net/?p=295)


看了這麼多，還不去日本買支 Apple Watch 2 來使用嗎？


### Apple Pay 卡號小知識

紅色部分是真實卡號的後四碼，然後 Wallet 正面也是顯示它；而綠色部分則是依照裝置產生的虛擬卡號，你交易時簽單也是顯示這末四碼
注意，所以一旦產生虛擬卡後，每一次交易都是用綠色那組卡號做交易，除非你重新綁卡不然綠色這組號碼都不會更換

<center>
![](https://hiy.tw/tech/apple_pay_active/2.jpg)
</center>


圖片來源：

www.flickr.com/photos/iphonedigital/26177960506/



