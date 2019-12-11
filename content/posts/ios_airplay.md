---
title: "iOS 設備同時輸出螢幕訊號且使用有線網路"
draft: false
date: 2017-10-04
tags: ["Airplay", "Ethernet", "iOS", "Lightning"]
categories: ["科技新知"]
---



故事很簡單，就是當有需要強聯網的 App 需要投放到螢幕上的時候，這時候就會需要考量到網路穩不穩的風險。尤其是在不熟悉的場地或是在人潮眾多的區域，無線網路的可靠度真的是讓人存疑的。

因此這邊就是實驗到底有什麼方法可以達成使用有線網路又可以投影畫面的方案。

<!--more-->

# 不行的方法

* iDevice 同時串接 Lightning to HDMI 與 Lightning to USB 再加上 USB 網卡

> 最棒的 "幻想" 當然是能讓設備接上有線網路然後又能輸出 HDMI 訊號。所以這時候就是想到使用雙轉接頭的可能性。雖然 Lightning to HDMI 與 Lightning to USB 的轉接線都有再提供一個 Lightning 的接頭，但他實際上就是指有供電的功能而已。所以如果兩個同時串接 iDevice 只會抓到真的插在設備的 Lightning 孔的擴充功能。另外一個串接的 Lightning 是無法被偵測到的。


![](https://hiy.tw/tech/ios_airplay/1.jpg)

 
 
> 此外已經有嘗試過 Lightning to HDMI 與 Lightning to USB 互換插設備的狀況，但結果都是只會抓到實際插在設備上的擴充功能。而且如果先插 Lightning to USB 轉有線網卡再插 Lightning to HDMI 還會直接說電壓不足。所以同時輸出多功能是不行的。


![](https://hiy.tw/tech/ios_airplay/2.jpg)



* iDevice 先接 Belkin 的 Lightning 一對二轉接頭再接上述設備

> 請直接死心，因為 Belkin 的轉接頭就直接寫明說它提供的第二 Lightning 只有供電功能，還是無法同時串兩個設備。


![](https://hiy.tw/tech/ios_airplay/3.jpg)


* iDevice 只接 Lightning to USB 再加上 USB 網卡然後供電的 Lightning 孔接電腦

> 就是 iDevice 接電腦後可以用 Quick Time 或是 OBS 這類的軟體直接獲取螢幕畫面。所以想說設備接出有線網卡然後供電的 Lightning 嘗試接電腦看會不會有偵測到設備。但上面已經說過他只有供電功能，所以電腦當然是抓不到的。


![](https://hiy.tw/tech/ios_airplay/4.jpg)


* iDevice 插上 USB 使用 rvictl 來導流量到 macOS

> 原本想說這樣會再 macOS 上面建立一張與 iDevice 連線的虛擬網卡。但是該網卡實際上就是無法獲得 IP，所以把 rvictl 的功能當成 Port Mirror 比較合理，就是單純的把 iDevice 流量複製一份到電腦。


![](https://hiy.tw/tech/ios_airplay/5.jpg)



# 可行的方法

* iDevice 接上 Lightning to USB 與有線網卡後，在有線網路的區網下做 Airplay

> 平常 Airplay 因為大多數都是走無線網路，所以會有一種延遲感非常重的印象。但是如果 Airplay 走的是有線網路且在不同時比對畫面的狀況下。這應該已經是一種可以接受的選項了。

> 然後這時候我就會推薦安裝 AirServer 這套軟體來模擬 Airplay 的顯示端，因為能調整的細節比較多。不論是單純是要顯示大畫面或是直播這都是一個不錯的方式。


<iframe width="560" height="315" src="https://www.youtube.com/embed/Emo2lI3hW6Q" frameborder="0" allowfullscreen></iframe>


## 參考資料

* http://www.airserver.com/
* https://www.apple.com/shop/product/MD826AM/A/lightning-digital-av-adapter
* https://www.apple.com/shop/product/MK0W2AM/A/lightning-to-usb-3-camera-adapter
* http://www.belkin.com/us/p/P-F8J198/



