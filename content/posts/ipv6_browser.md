---
title: "在網址列正確連上 ipv6 方式"
draft: false
date: 2016-08-08
tags: ["ipv6", "Browser"]
categories: ["科技新知"]
---


不知道大家有沒有在網址列輸入 ipv6 位置後是被轉跳到 Google 搜尋而非連線到主機的經驗，就算前面有加 https:// 也都還是一樣。

其實是因為如果要讓瀏覽器正確辨識你到底是要搜尋還是連線，因此你需要把 ipv6 用 [] 包起來

<!--more-->


![](https://hiy.tw/tech/ipv6_browser/1.png)


所以用法看起來會像是 [https://[2001:b032:1c::11]](https://[2001:b032:1c::11]) 這樣子，這樣瀏覽器就會正確的把你得ipv6 網址認為是主機位置而非是你要用 Google 搜尋，然後 ipv6 有些公家機關服務會跳出一些預期之外的資訊喔 :p







