---
title: "iOS 10 JB 後 Cydia 突然消失解決方案"
draft: false
date: 2017-07-29
tags: ["iOS", "Jailbreak"]
---


就 iOS 10 所使用的 yalu 來 Jailbreak 還不是那麼的穩定，所以會有突發狀況導致 Cydia 突然消失。然後以下兩種是網路上找到可以解覺得方案

<!--more-->

## 方案一：移除 Yalu 在 Jailbreak 留下的記錄檔

就因為 iOS 10 都是 Semi Jailbreak 所以重開機後系統會需要重新跑一次越獄流程，但因為已經安裝過 Cydia 所以理當 Yalu 不應該在跑一次安裝 Cydia 的流程。這也就是為什麼在 Cydia 消失後重跑 Yalu 不會重新安裝 Cydia 的原因，因為他認為你已經越獄過所以不需要重新裝 Cydia。

所以我們需要的作法就是把系統根目錄下的 `.installed_yaluX` 移除掉然後重開機再執行 Yalu 就可以了。

#### 具體作法會是：

##### Step0: 
確認 Yalu 已經完成越獄
 
##### Step1: 
如果 OpenSSH 有正常運作就直接在同區網下使用 SSH 服務來登入，然後預設帳號是 root 而密碼是 alpine；如果當時沒有裝 OpenSSH，那請找一台 Windows 電腦安裝 iFunbox 3.0 之後版本使用其中的 USB Tunnle 來幫你建立連線。

<center>
![](https://hiy.tw/tech/ios_10_cydia_disappear/1.png)
</center>


##### Step2: 
登入後直接執行 `rm /.installed_yaluX`，然後就可以重開機在執行一次 Yalu，這時候理論上你的 Cydia 就會回來了，如果沒有就再使用 SSH 登入後輸入 uicache 來強制把你 iOS 的介面重新更新一次。這時候應該就會出現了，如果還是沒有就可以參考方案二。

<center>
![](https://hiy.tw/tech/ios_10_cydia_disappear/2.png)
</center>





## 方案二：自己重新安裝 Cydia

如果上述方式無效，可以考慮看看自己來安裝 Cydia，理論上這一定會出現如果還是沒有應該就是你系統有什麼損壞，可以請直接回復出廠設定等待下一版本的 Jailbreak 比較快。

#### 具體作法會是：

##### Step0: 
確認 Yalu 已經完成越獄

##### Step1: 
用 iFunbox 或是其他可以管理 iOS 設備的軟體或甚至使用 SCP 把這解壓縮出來的檔案都放到 iOS 設備中。

#### Step2: 
登入 SSH 後，直接用 `dpkg -i` 的方式把 Cydia 那兩個檔案安裝起來，然後一樣在 shell 中先執行 `uicache` 然後再執行 `killall SpringBoard` 這時候理論上 iOS 裝置就會假重開，理論上 Cydia 就會回來了。


參考資料：
https://www.youtube.com/watch?v=AECDX96E2k8





