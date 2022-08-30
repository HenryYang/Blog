---
title: "關於沒 Google Play 手機納管 VMware Airwatch 相關問題"
draft: false
date: 2022-08-30
tags: ["android", "mdm"]
categories: ["程式技術"]
---

TL;DR: 華為的新款手機基本上請直接放棄，非常難納管進入 VMware Airwatch 內



<!--more-->

VMware 官方對於中國境內網路環境的說法:

```
Customers are advised that Google Services are currently blocked in China, which includes the Google Play Store and any device management service that relies on Google.
Workspace ONE Intelligent Hub for Android is unable to leverage Android Enterprise Work Profile. Work Managed enrollment mode requires configuration Without Google Play Services.
As a public app, Users may download Workspace ONE Intelligent Hub .apk from GetWSONE.com.
```

https://kb.vmware.com/s/article/75197

</br>


總之官方文件都是寫爽的，重點如下:

1. https://www.getwsone.com/ 這邊還是只會給你 Google Play 的連結，如果真的要下載 .apk 檔請去 https://my.workspaceone.com/products/Workspace-ONE-Intelligent-Hub
2. 它只說到中國的網路環境狀況，沒說到中國手機的狀態。基本上中國賣的設備都不支援 Android Enterprise 納管，最多就只能在進入系統後以一個正常等級的應用程式運作
3. 雖然說可以在進入系統後才安裝，但能不能裝其實不是看有沒有 Google Play 這 App，而是看手機有沒有內建 Google Service Framework，判斷方式可以透過在系統內新增一個 Email 帳戶看有沒有 Google 或是 Gmail 可以選擇
4. 目前經驗來說 Oppo 跟小米的中國版機種都可以被成功納管，但華為的怎樣都不行。就算是硬裝上 Google Service Framework 也還是不行




</br>
