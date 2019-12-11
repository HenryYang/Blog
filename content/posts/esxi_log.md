---
title: "ESXI 的 LOG 移至內建空間"
draft: false
date: 2016-11-23
tags: ["Log", "ESXI"]
categories: ["程式技術"]
---


就很多教學都會教說把 ESXI 系統安裝在記憶卡或是隨身碟上，但如果你的系統使用太頻繁就有可能會讓 LOG 把記憶卡的存取次數快速耗盡。

所以我個人都會習慣把 LOG 放在內建的空間中，除了空間會比較大以外更重要的是傳統硬碟或是 SSD 的存取壽命都高非常多啊。

<!--more-->


![](https://hiy.tw/coding/esxi_log/1.png)





### 教學：

他可以用 Web Client 、 CLI 跟 vSphere Client 來設定，我這邊就以最熟悉的 vSphere Client 為主

登入主機後進到儲存空間，然後新增一個名為 .locker-***ESXHostname*** 的資料夾（其中 ***ESXHostname*** 請換成你自己主機的名字）

然後選擇軟體這分頁，有一個進接設定，這時候找到 ScratchConfig 這選項，然後把 ScratchConfig.ConfiguredScratchLocation 這欄位填入 /vmfs/volumes/***DatastoreUUID***/.locker-***ESXHostname***

其中 DatastoreUUID 請換成你硬碟的 UUID，這可以設定/儲存空間的地方找到。然後記得 .locker-***ESXHostname*** 也請改成自己主機的名字

這時候再把主機重開一次就完成了

參考資料：

https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1033696





