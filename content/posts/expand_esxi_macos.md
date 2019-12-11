---
title: "擴充 VMware 上面的 MacOS 虛擬機硬碟空間"
draft: false
date: 2017-04-16
tags: ["macOS", "ESXI"]
categories: ["程式技術"]
---


目前最簡單擴充硬碟的應該就屬 MacOS 了，然後以下是筆記

Step1: 當然是修改 VMware 上面的參數，讓 OS 實際能動用的到空間變大。


![](https://hiy.tw/tech/expand_esxi_macos/1.png)


<!--more-->

Step2: 查看目前要擴充的磁碟代號

`diskutil list`

Step3: 將你預估的硬碟擴充成你想要的容量，這樣就完成了（這邊選擇 disk0s2 並且擴充成為 200GB 硬碟）

`diskutil resizeVolume disk0s2 200G`



註，如果有跳出問題可以先修復你預估擴充的磁碟（這邊是以 disk0 為例）

`diskutil repairDisk disk0`







