---
title: "Raspberry Pi 透過 USB 3G 行動網卡上網"
draft: false
date: 2016-12-17
tags: ["Cellular", "Raspberry Pi"]
categories: ["程式技術"]
---



![](https://hiy.tw/coding/raspberry_pi_usb_3g/1.jpg)



注意： 目前 "理論上" 未鎖電信商的華為 **3G** USB 網卡理論上都可以使用，我自己是使用當年跟中華電信買的 E161 

我這邊是使用 sakis3g  這到軟體來簡化連線的設定，真的就只要下載執行就可以連上行動網路的，就不用在設定很多麻煩的 pppd

<!--more-->

#### 下載軟體

```  wget "http://raspberry-at-home.com/files/sakis3g.tar.gz" ```
``` tar -zxvf sakis3g.tar.gz -C . ```
``` sudo chmod +x sakis3g```


#### 執行服務

對，這樣就算是安裝完成了，只是請記得要使用 ROOT 權限或是使用 sudo 來執行這程式

如果要用互動式介面就輸入
``` sakis3g --interactive```

如果想直接連線就輸入（注意就算你的電信商不用設定 APN 的帳號密碼也請隨意輸入，不然會錯誤）
``` sakis3g connect APN=internet APN_USER="123" APN_PASS="123" ```

如果想要斷線可以輸入
``` sakis3g disconnect```

#### 如果覺得指令太常可以搭配 alias 使用 (預設檔案是放在 pi 的家目錄下)

```echo "alias 3gup='sudo /home/pi/sakis3g connect APN=internet APN_USER="123" APN_PASS="123"'" >> ~/.bashrc ```

```echo "alias 3gdown='sudo /home/pi/sakis3g disconnect '" >> ~/.bashrc ```

這樣就可以直接用 3gup 跟 3gdown 這指令來建立與關閉 3G 行動網路的連線了

參考資料：

http://felix-lin.com/linux/%E8%A8%AD%E5%AE%9A-raspberry-pi-%E6%88%90%E7%82%BA-3g-router-%E6%95%99%E5%AD%B8/

http://elinux.org/RPi_VerifiedPeripherals#USB_3G_Dongles

https://github.com/Trixarian/sakis3g-source






