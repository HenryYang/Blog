---
title: "紅米 Note 4X ROOT 與刷第三方 Recovery 注意事項"
draft: false
date: 2017-03-05
tags: ["App", "Android", "Root"]
---


小米現在越來越難搞了，以下為強者我朋友的真心血淚紀錄：

<center>
![](https://hiy.tw/tech/note_4x_root/1.png)
</center>

<!--more-->

注意事項：
* 台灣賣的紅米 Note 4X 在中國會是稱為紅米 Note 4 高通版本，所以找資源時務必注意
* 現在小米都有鎖 Boot Loader (通常簡稱 BL)，要解鎖後才能做修改系統底層的事情
* 國際版本的開發版沒有 root，中國版本的開發版本才會內建 root
* 國際版本的無法刷第三方的 Recovery，因為沒有 root 所以無法關閉 system partition 的驗證功能


以下為刷第三方 Recovery 的方法：

## 申請unlock BL->刷國際開發版->用工具unlock BL->線刷大陸開發版->開啟內建root->關閉system區塊驗證->刷TWRP->裝google相關元件->收工


這邊解釋一下原因：
* 就是穩定版不能解鎖 BL，然後不知道為什麼中國的開發版也解不了，然後只要刷成國際開發版後，手機上面也不用去開啟設定，直接跑解鎖工具就可以完成解 BL，但要有 root 才能去關閉 system 區塊的驗證，所以只好在改刷成中國開發版，等關閉後就可以刷第三方的 Recovery。
* 然後目前找到能用的安裝 Google Play 服務的叫做 GO谷歌安裝器 ，但請自己確定來源的安全性


注意：如果有要安裝 Xposed 的使用者務必安裝給 MIUI 的特製版，可以參考以下連結

[https://forum.xda-developers.com/xposed/unofficial-xposed-miui-t3367634](https://forum.xda-developers.com/xposed/unofficial-xposed-miui-t3367634)




參考資料：

http://tw.miui.com/thread-20633-1-1.html

http://www.miui.com/unlock/done.html

http://www.miui.com/thread-7365784-1-1.html




