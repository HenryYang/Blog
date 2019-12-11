---
title: "完整移除 Parallels Desktop"
draft: false
date: 2016-02-01
tags: ["macOS"]
categories: ["科技新知"]
---


就是升級到 OSX 10.11 後真的是踩雷大會，然後我的 Parallels Desktop 11 又在鬼打牆的狀況（EX：USB 裝置隨機失效、鍵盤滑鼠在抽筋）

所以就決定把整個 Parallels 乾淨的移除，然後從<a href="http://kb.parallels.com/Attachments/kcs-35959/PDremove.zip" target="_blank">官方的載點</a>重新下載安裝



![](https://hiy.tw/tech/parallels_desktop_remove/1.png)


這是一個搭配 shell script 的 Automator 的腳本程式，總之就是執行後輸入密碼，然後他會跳出一個終端機的視窗，不要關閉，等他程式跑完會跳出一個移除成功的訊息，這樣就算是完成乾淨的移除了

接下來去官網載最新版的 DMG 安裝檔安裝就可以
註：不知道為什麼，我如果用 brew cask 安裝的還是會怪怪的，一定要用官方的 DMG 安裝載的才會正常





