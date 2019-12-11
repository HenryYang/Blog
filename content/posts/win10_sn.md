---
title: "Windows 10 序號使用限制"
draft: false
date: 2016-08-04
tags: ["Windows 10"]
categories: ["科技新知"]
---


實測結果，如果序號來源是 "<strong>由舊版 Windows 升級到 Windows 10 時所產生</strong>"的拿來給全新安裝的 Windows 10 是  "<strong>可以被系統辨識版本，但是無法啟用的！</strong>"

<!--more-->


![](https://hiy.tw/tech/win10_sn/1.png)



如果你當時是用免費升級的，理論上查詢系統序號會是以下這兩組

專業版 VK7JG-NPHTM-C97JM-9MPGT-3V66T
家庭版 TX9XD-98N7V-6WMQ6-BX7FG-H8Q99

然後蠻有趣的是拿<a href="https://www.microsoft.com/zh-tw/software-download/windows10ISO">官方網站</a>下載的 ISO 輸入企業版序號會說因為找不到對應的映象檔所以無法安裝，但如果先選擇安裝專業版，就算沒有先啟用，進到系統後更換成企業版序號竟然就可以，而且很明顯的不像以前的 Windows Anytime Upgrade 要跑超久，根本幾秒鐘就變成企業版

註：根據 Jas Chiang 的回報，Windows 10 ISO 裡面沒內含 ei.cfg，但可以透過手動新增的方式修改安裝任意版本或授權形式的 Windows

順便附上 <a href="https://support.microsoft.com/zh-tw/help/12440/windows-10-activation">Windows 10 授權的介紹</a>





