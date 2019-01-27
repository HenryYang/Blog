---
title: "快速讓全景照片支援 Facebook 的 360 度顯示"
draft: false
date: 2017-04-16
tags: ["Facebook", "360", "EXIF"]
---


最近越來越多攝影設備支援全景照片，但不是每家的 EXIF 都可以正確的被 Facebook 辨識出來，所以就會造成上傳後變成一張很醜的 2:1 照片。

以下教學是 Facebook 官方的建議方式，讓沒有被 Facebook 辨識出來的全景照片手動修復成可以在 Facebook 上看的 360 照片。

<!--more-->

<center>
![](1.png)
</center>



照片需求：
 * 需要為 2:1 比例的照片
 * 解析度最高只能到 6000 ＊ 3000，超過一樣會無法辨識


使用軟體： [exiftool](http://www.sno.phy.queensu.ca/~phil/exiftool/)

使用方式：

就非常簡單，只要在命令提示字元或是終端機下   ```  exiftool -ProjectionType="equirectangular" 你照片的名稱.jpg ``` 

<center>
![](2.png)
</center>

然後原本的檔案的 EXIF 就會被加上 ProjectionType=equirectangular 這數值，然後如果有任何做錯，也還有 ```你照片的名稱.jpg_original``` 的原始照片存在。

這時候打開你的 Facebook 網頁版本，再點選那張照片就會看到地球圖示，這樣就代表上傳後會變成 360 相片

<center>
![](3.png)
</center>

參考資料：

https://facebook360.fb.com/editing-360-photos-injecting-metadata/






