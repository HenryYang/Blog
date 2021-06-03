---
title: "取得 NordVPN 的 Wireguard 參數並匯入 Router 使用"
draft: false
date: 2021-06-03
tags: ["vpn", "wireguard", "nordvpn"]
categories: ["程式技術"]
---   

NordVPN 預設只提供 OpenVPN 的設定檔給不裝軟體的使用者使用

至於他們目前在測試的 NordLynx （以 WireGuard 為基礎）效能好非常多但是一定要裝 App 才能使用

所以為為了取得參數與公私鑰，下面就是目前可行的 workaround 方案

<!--more-->

核心概念就是在 Linux 系統上安裝 NordVPN 的官方軟體，並連接上後，這時候就可以取得自己目前在使用的私鑰

在這裝置不登出的前提下，就可以開心的把這私鑰帶去各台設備上使用了。以下用 Ubuntu 20.04 作為示範環境


</br>

#### Step.1 安裝所需軟體
```
# 先透過 apt 安裝所需軟體
sudo apt install wireguard curl jq net-tools

# 再來安裝 NordVPN 官方軟體
sh <(curl -sSf https://downloads.nordcdn.com/apps/linux/install.sh)
```


</br>

#### Step.2 登入 NordVPN 並把連線方式改成 NordLynx 後連上想連的國家
```
# 登入
sudo nordvpn login

# 把連線方式改成 NordLynx
sudo nordvpn set technology nordlynx

# 顯示目前支援的國家
sudo nordvpn countries

# 連線到想連的國家 （這邊以台灣為例）
sudo nordvpn c TAIWAN
```

</br>

#### Step.3 取得 NordVPN 所配發的 ip 位置 
```
# 輸入後看 inet 的數值為多少，我這邊是 10.5.0.2，可能一樣可能不同，請把你自己的記下來
ifconfig nordlynx

```


</br>

#### Step.4 取得 NordVPN 屬於自己的私鑰 
```
# 輸入後顯示的字串就是你的私鑰，請妥善保存不要公開，誰有這組就可以偽裝成你來連線驗證
sudo wg show nordlynx private-key
```


</br>

#### Step.5 取得要連線的伺服器 ip 資訊與公鑰 
```
# 這邊是直接透過 NordVPN 的 API 去撈，然後他是依照你連去的 IP 顯示你該國家的伺服器資訊
# 所以要看哪一個國家的就是先用上面那個 sudo nordvpn c 這指令去連上想要的國家後再開下面的網址

https://api.nordvpn.com/v1/servers/recommendations

# 開啟網頁後，去找 station 內的 IP 資訊跟 public_key 這兩個值記錄下來就可以
# 如果覺得麻煩可以直接用下面這網友寫好的指令直接撈出最快的主機資訊
curl -s "https://api.nordvpn.com/v1/servers/recommendations?&filters\[servers_technologies\]\[identifier\]=wireguard_udp&limit=1"|jq -r '.[]|.hostname, .station, (.locations|.[]|.country|.city.name), (.locations|.[]|.country|.name), (.technologies|.[].metadata|.[].value), .load'
```


#### 這時候所需的資訊都有了

上面步驟都做完後，記得先把執行 `sudo nordvpn d` 來中斷電腦的 NordVPN 服務連線

就可以開心的去 Router 設定了，通常會分 Interface 跟 Peer 兩大區塊

前者是設定我方資訊，後者是設定有關伺服器資訊

* Interface
    * IP Address -> 輸入 Step3 所拿到的 ip 資訊
    * Private Key -> 輸入 Step4 所拿到的私鑰
    * Listen Port -> 可以空白，如果一定要填就輸入 41012
    * DNS -> 填寫你自己常用的 DNS

* Peer
   * Public Key -> 輸入 Step5 所拿到的伺服器公鑰
   * Endpoint Host ->  輸入 Step5 所拿到的伺服器 ip，如果輸入後系統顯示錯誤就請加上 `:51820` 的通訊埠資訊
   * Allowed IPs -> 輸入 `0.0.0.0/0`
   * Keep Alive -> 輸入 `25`


這邊記得，如果要更換伺服器就只需要重新在 Step5 取得新的伺服器 ip 資訊與公鑰後把 Peer 的 Public Key 與 Endpoint Host 換掉後重新連線就可以了


#### 參考資訊
[https://forum.openwrt.org/t/instruction-config-nordvpn-wireguard-nordlynx-on-openwrt/89976](https://forum.openwrt.org/t/instruction-config-nordvpn-wireguard-nordlynx-on-openwrt/89976)
 
