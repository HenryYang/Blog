---
title: "Apple M1 晶片的 MacOS 一些必備知識"
draft: false
date: 2021-06-05
tags: ["MacOS"]
categories: ["程式技術"]
---

請記得，把 Apple M1 的 MacOS 當成一台手機或是平版來看看待，這樣思路會比較簡單一點。

<!--more-->

![](https://www.apple.com/newsroom/images/product/mac/standard/Apple_new-m1-chip-graphic_11102020_big.jpg.large_2x.jpg)

### 先從軟體安裝面來說

* 請從 `Terminal` 執行 `softwareupdate --install-rosetta` 來安裝 Rosetta 來讓自己為來都可以用相容模式跑傳統軟體
* 對於應用程式按右鍵會有「使用 Rosetta 開啟」，如果勾選了應用程式就會以 intel-x86 架構運行
    * 對於 `Terminal` 這類的軟體勾選了「使用 Rosetta 開啟」，此時 `Terminal` 安裝的軟體如果由系統直接判斷就會是安裝 x86 架構
    * 反之沒勾選就是安裝 arm 架構
* homebrew 會偵測目前環境來決定安裝 arm 跟 intel x86 版本的軟體，如果在 arm 找不到套件，可以把 `Terminal` 啟用 Rosetta 後執行 homebrew 來安裝軟體

### 軟體版本的大災問

* 想要把過去的舊專案直接到放到 M1 就立刻可以執行通常有點難
    * 但基本上只要是有在更新的各種套件或是工具，嘗試把版本更新基本上就會逐步支援 M1 系統


### 重灌教學

* Apple M1 的重灌方式跟過去個都有點不同，像是進入重灌畫面是要長壓電源按鈕直到看到「選項」就是齒輪的圖示
    * 參考連結 : https://support.apple.com/zh-tw/HT211983
* 如果用使用內建的還原回覆失敗後，通常我就會建議使用 Apple Configurator 2 來幫設備還原
    * 參考連結：https://support.apple.com/zh-tw/guide/apple-configurator-2/apdd5f3c75ad/mac
    * 這有點麻煩，因為需要再多一台 macOS 10.15.6 以上的實體電腦，然後 Type-C 線才對接，用好的電腦幫有問題的重灌
    * 這一切就像是以前電腦幫手機還原的步驟類似，但現在是電腦幫電腦還原
    







