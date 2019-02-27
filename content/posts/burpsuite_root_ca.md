---
title: "在行動裝置上安裝 BurpSuite 所簽發的 Root CA 憑證"
draft: false
date: 2016-07-31
tags: ["CA", "BurpSuite"]
---


通常要測試手機 App 時，大多數都會選擇用 MITM （中間人攻擊）的方式來達成，但也因為目前大多數服務都已經走 HTTPS 來傳遞資料，因此需要在手機端匯入做中間人攻擊的根憑證。

<!--more-->

<center>
![](https://hiy.tw/coding/burpsuite_root_ca/1.png)
</center>



然後這邊要注意的是，透過 BurpSuite 產生出來的根憑證是 .der 格式，在這格式可以直接用 email 或是各種方式匯入 iOS

<center>
![](https://hiy.tw/coding/burpsuite_root_ca/2.png)
</center>


而 Android 並不認識 .der 格式，所以要把副檔名修改成 .cer 格式，然後進設定裡面的安全性去安裝憑證。

<center>
![](https://hiy.tw/coding/burpsuite_root_ca/3.png)
</center>






