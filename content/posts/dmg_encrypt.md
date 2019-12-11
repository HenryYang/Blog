---
title: "用磁碟工具程式來製作一個 DMG 檔以加密重要資料"
draft: false
date: 2016-10-22
tags: ["macOS", "Encrypt"]
---


目前市面上的加密軟體百百種，但我自己尋找的條件是要可以快速加密，然後最好是可以虛擬出一個磁區出來，放進去就是背景加密而複製出來就可以自動解密，然後因為希望可以跟雲端同步，所以不希望是完全加密成一個檔案，這樣會造成有變動就會是全部重新上傳。

<!--more-->

現有在 MacOS 上面找到符合我需求的是 boxcryptor 這套軟體，但他目前改成年費制（但也有提供單一電腦的使用的免費版本）而且公鑰會存一份在他們家的伺服器上，總還是感覺怪怪的 :(

因此目前研究到另外一個不錯的就是 MacOS 系統內建的磁碟工具程式，可以產生加密的 DMG 映象檔，然後選擇動態大小時，他會依照檔案的大小自己動態調整，不會一開始就吃到設定映象檔的上限，然後因為他雖然看起來像是單一檔案，但實際上是由多個檔案所組成的，所以上傳檔案的時候就不會全部都要上傳，只會需要上傳有更改過的部分而已，所以其實就是很方便的加密與放上雲端。


## 教學

開啟磁碟工具程式，然後新增空白映象檔

<center>
![](https://hiy.tw/tech/dmg_encrypt/1.png)
</center>

這時候請記得，映像檔格式請選擇 "稀疏的磁碟映像檔" 然後加密請選擇 "256 位元的 AES 加密" 

<center>
![](https://hiy.tw/tech/dmg_encrypt/2.png)
</center>

<center>
![](https://hiy.tw/tech/dmg_encrypt/3.png)
</center>

等完成後你設定的地方應該會多一個副檔名為 .sparseimage 的檔案，以後只要點擊它，系統就會問你密碼，我個人是建議不要記憶每次都輸入，然後輸入正確後理論上 Finder 左側就會出現一個新的磁碟，把檔案放入就可以了。

<center>
![](https://hiy.tw/tech/dmg_encrypt/4.png)
</center>

<center>
![](https://hiy.tw/tech/dmg_encrypt/.png)
</center>

<center>
![](https://hiy.tw/tech/dmg_encrypt/6.png)
</center>

然後記得以後這 .sparseimage 的檔案就會存有你加密過的資料，請好好保管與備份這檔案，不見或是忘記密碼裡面的東西就說再見了 QQ







