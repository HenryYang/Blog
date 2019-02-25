---
title: "libimobiledevice 相關指令"
draft: false
date: 2016-12-11
tags: ["iOS"]
---


**idevice_id -l** 查詢設備 UID

**ideviceinstaller -l** 列出使用者安裝的 App

**ideviceinfo** 列出設備訊息


<!--more-->


**idevicebackup2 backup ./TEST** 備份檔案到當前目錄的 TEST 資料夾 

**idevicebackup2 unback ./TEST** 解開備份的資料成為正常檔案

**idevicesscreenshot** 螢幕節圖，但似乎要搭配 ideviceimagemounter 一起使用

**idevicesyslog** 即時的系統 log （但手機要為解鎖狀態）

**idevicediagnostics sleep** 睡眠（關閉螢幕？！）

**idevicediagnostics shutdown** 關機

**idevicediagnostics restart** 重開機

**ideviceinstaller -u com.example.map** 解除指定軟體

**ideviceinstaller -i xxx.ipa** 安裝指定軟體



