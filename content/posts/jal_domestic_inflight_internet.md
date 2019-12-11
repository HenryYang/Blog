---
title: "日航 JAL 國內線 Inflight internet 連線障礙排除"
draft: false
date: 2018-12-20
tags: ["JAL", "WiFi" ]
categories: ["科技新知"]

---

#### 注意，如果是遇到 WiFi 直接無法連接到該 SSID 的請直接放棄吧，因為那是設備問題了 XD
<!--more-->

![](https://hiy.tw/tech/jal_domestic_inflight_internet/1.png)




##### 狀況一：連上 WiFi 熱點但一直拿不到 IP

這時候請嘗試更新重新跟 DHCP 取得 ip 看看

* Windows：在 CMD 下輸入 `ipconfig /renew`
* macOS：選擇 `系統偏好設定` -> `網路` ->  `進階` -> `TCP/IP` -> `更新 DHCP 租約`
* Android：痾，好像沒有很通用的作法，就建議重開機再連線試試看
* iOS：選擇 `設定`  -> `Wi-Fi`  -> 點選右方的藍色 `i` -> `更新租約`

##### 狀況二：連上 WiFi 熱點也拿到 IP，但就是不會跳出驗證畫面

首先可以直接在瀏覽器輸入 [http://airborne.gogoinflight.com](http://airborne.gogoinflight.com)，這是會自動轉向到 JAL 國內線的驗證網頁，如果輸入後就可以看到驗證畫面就可以直接登入使用。但通常都是不行的，所以這時候請確認 DNS 是被`設定成自動` 而不是 Google 的 8.8.8.8 或是 Hinet 的 168.95.1.1。

小科普，DNS 可以想像成把我們常見的網域轉換成 IP 的功能，然後上述日航國內線所用的 airborne.gogoinflight.com 它只有被 JAL 自己的 DNS 所記錄，如果用的是 Google 或是 Hinet DNS 是不認得這網域的。

P.S. 如果改成自動後還是無法連上 [http://airborne.gogoinflight.com](http://airborne.gogoinflight.com) 這網頁，可以考慮手動把 DNS 指向到 `172.19.134.2` 這是 2018 年搭了十多班航班確認過都是指向這 IP 位置，所以也可以試試。

* Windows：[請參考官方教學](https://support.microsoft.com/zh-tw/help/15089/windows-change-tcp-ip-settings)
* macOS：[請參考網友的步驟](https://briian.com/27152/)
* Android：[一樣參考網友步驟](https://briian.com/22242/)，各家介面稍微不同，但主要都還是在連線上後去修改對該 WiFI 熱點設定值
* iOS：[網友教學](https://www.howtogeek.com/261701/how-to-change-the-dns-server-on-your-ios-device/)，一樣是對每個 WiFi 熱點做分別修改

##### 狀況三：連上 WiFi 熱點也看到登入頁面但一直無法使用

就剛起飛的時候雖然已經有在機內提供 WiFi 訊號，這這不代表這 WiFi 有連上網際網路，所以通常都是建議在個幾十分鐘等安全帶指示燈熄滅，代表飛機到一定高度時，這時候基本上都一定可以成功登入。

然後也建議，可以先提前到 [Gogoair](https://www.gogoair.com/) 官網註冊帳號，雖然在飛機上也是可以註冊，只是因為網路延遲等等的奇怪狀況，其實還蠻容易註冊失敗的。反正帳號是重複使用，就提早先在地面上註冊吧。


