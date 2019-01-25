---
title: "檢查瀏覽器的 Service Workers 有沒有被埋奇怪的東西"
draft: false
date: 2018-01-15
tags: ["Chrome", "Firefox", "Service Workers"]
---


故是就是現在網頁能透過太多種方法來背景執行一些服務，其中目前常見的方法就是使用 Service Worker 來讓服務在背景跑。

所以就是可以自己來檢查看看有沒有被允許的陌生或是不認識網站正在執行 Service Worker，如果曾經有允許網站的推播基本上都會出現。

<!--more-->

Chrome 開啟的方法是在網址列輸入 `chrome://inspect/#service-workers`

Firefox 開啟的方法則是在網址列輸入 `about:debugging#workers`，

然後就會看到下面這兩種介面的 Service Worker 管理。就看看有沒有不認識的，要記得關 XD

<center>
![](1.png)
</center>

<center>
![](2.png)
</center>


