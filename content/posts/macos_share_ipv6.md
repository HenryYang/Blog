---
title: "透過 MacOS 分享純 ipv6 的網路"
draft: false
date: 2017-04-16
tags: ["macOS", "ipv6", "NAT64"]
categories: ["科技新知"]
---


就有時會需要在設備只拿到 ipv6 的情況下來做一些神秘的 Debug，所以以下方式是快速的架設一個臨時純 ipv6 環境來測試


架設需求: MacOS 需要為 10.12 ，因為這版才有提供 ipv6 環境


設定步驟:

*  開啟 "系統偏好設定" -> 並點選  "分享"


<!--more-->


![](https://hiy.tw/tech/macos_share_ipv6/1.png)




![](https://hiy.tw/tech/macos_share_ipv6/2.png)



* 選擇 "Internet 共享" ，然後 "共享連線來源" 選擇你的有線網路，而 "對使用已傳輸卓的電腦" 選擇 Wi-Fi ，這時候請記得勾選左下方的 "建立 NAT64 網路"，然後如果如果需要設定密碼或是 SSID 請點選右下方的 "Wi-Fi 選項"。

P.S. 如果沒有出現 "建立 NAT64 網路" 的選項，請回到上一步，然後按住 "option" 後再點擊 "分享"



![](https://hiy.tw/tech/macos_share_ipv6/3.png)



![](https://hiy.tw/tech/macos_share_ipv6/4.png)



### 這時候你電腦已經建立了 NAT64 的網路了，只要連上你所建立網路的設備都會收到 ipv6 的位置。


#### iOS 設備查詢 ipv6方式:

設定 -> Wi-Fi  然後點選你連線網路後面的藍色 i ，這時候你就會看到 IP 位置會是 169.254 開頭的位置，然後下方的 ipv6  位置應該會是一組 2001 開頭的位置


<center>
![](https://hiy.tw/tech/macos_share_ipv6/5.png)
</center>

<center>
![](https://hiy.tw/tech/macos_share_ipv6/6.png)
</center>

####  這時候就是確認你設備已經透過 MacOS 的 NAT64 拿到 ipv6 的 ip 了



##注意，如果 ipv6 網路有任何異常或是 DNS 快取有誤，請將 iOS 的網路重設，這只會影響到有關網路的設定，手機資料不會遺失

設定 -> 一般 -> 重製 ->  重製網路設定


<center>
![](https://hiy.tw/tech/macos_share_ipv6/7.png)
</center>


#### Mac 清除 DNS 快取方法

`sudo killall -HUP mDNSResponder`





