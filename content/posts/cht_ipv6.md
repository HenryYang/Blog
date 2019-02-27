---
title: "中華電信 ipv6 相關資訊筆記"
draft: false
date: 2016-08-04
tags: ["ipv6", "CHT"]
---


<a href="https://123.cht.com.tw/eCAS/B8W">中華電信 ipv6 線上申辦</a>

光世代 FTTH 所提供的 040GW 數據機的 PPPOE 撥號不提供 ipv6

<!--more-->

Mac OS 雖然在 10.5 後就有支援 IPv6 over PPPoE 但因為無法透過 ICMPv6 Router Advertisement 封包自動設定 IPv6 位址
白話文就是系統預設的 pppd 無法讓你直接就拿到 ipv6

所以建議 Mac OS 前面接一台支援 ipv6 的 router 來處理，或者你可以選則自己設定與編譯 ipv6 相關的元件，詳情可以參考<a href="http://blog.clkao.org/post/285074/ipv6-over-pppoe-on-mac">高村長的紀錄</a>

我自己是使用 RouterOS 來負責我家網路的各項處理，而 RouterOS 設定 ipv6 的教學可以參考<a href="https://blog.cprteam.org/archives/279">線路組的 Blog</a>



