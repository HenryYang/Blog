---
title: "Apple Pay 交通票卡的一些冷知識"
draft: false
date: 2018-09-03
tags: ["Apple Pay"]
categories: ["科技新知"]
---

### 日本的 Suica 是轉移，中國的北京一卡通是買新卡

* 所以 Suica  在實體卡轉移到手機後，原實體卡會失效

* 中國的北京一卡通，是用實體卡的餘額花 20 RMB 買張新卡然後把實體卡餘額轉到虛擬卡去

* 因此，最後結果是一張 0 RMB 但是可以用的實體卡與一張有原本餘額減 20 RMB 的虛擬卡

<!--more-->



![](https://hiy.tw/tech/apple_pay_transit/1.png)



### 中國的北京一卡通一樣可以手機跟手錶之間互轉

* 互轉過程中，虛擬卡的外卡卡號不變，但是內卡卡號（俗稱 UID）會在每一次傳送到下一台設備時更換

* 意思是如果一開始在手機的 UID 是 A ，傳到手錶後會變成 B，再傳回手機不會變回 A 而是會再變成 C

* 中國的北京一卡通是走 Mifare 規格

* 所以可以相容於大部分的台灣常見讀 UID 驗證的門禁系統



![](https://hiy.tw/tech/apple_pay_transit/2.png)




