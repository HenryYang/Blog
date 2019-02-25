---
title: "Raspberry Pi 3 安裝 libimobiledevice ＆ ADB 筆記"
draft: false
date: 2016-12-10
tags: ["ADB", "iOS", "Android", "Raspberry Pi"]
---

<center>
![](https://hiy.tw/coding/raspberry_pi_libimobiledevice_adb/1.jpg)
</center>


## libimobiledevice 部分

Repo：https://github.com/libimobiledevice/libimobiledevice

<!--more-->

可以用 apt-get 取的的：

`sudo apt-get -y install vim tmux git build-essential libxml2-dev python2.7 python2.7-dev fuse libtool autoconf libusb-1.0-0-dev libfuse-dev make autoheader automake pkg-config libssl-dev libzip-dev`

需要依照順序編譯的：

**一：libplist**

`git clone https://github.com/libimobiledevice/libplist.git`

`cd libplist`

`./autogen.sh`

`make`

`sudo make install`


**二：libusbmuxd**

`git clone https://github.com/libimobiledevice/libusbmuxd.git`

`cd libusbmuxd`

`./autogen.sh`

`make`

`sudo make install`


**三：libimobiledevice**

`git clone https://github.com/libimobiledevice/libimobiledevice.git`

`cd libmobiledevice`

`./autogen.sh`

`make`

`sudo make install`


**四：ideviceinstaller**

`git clone https://github.com/libimobiledevice/ideviceinstaller.git`

`cd ideviceinstaller`

`./autogen.sh`

`make`

`sudo make install`


**五：ifuse**

`git clone https://github.com/libimobiledevice/ifuse.git`

`cd ifuse`

`./autogen.sh`

`make`

`sudo make install`


理論上安裝好後執行 ideviceinfo 等指令有程式就代表都完成了，但如果是找不到檔案可以嘗試新增以下路徑應該就可以了

`export LD_LIBRARY_PATH=/usr/local/lib`


## ADB 部分

安裝 ADB

`sudo apt-get install android-tools-adb android-tools-fastboot`

如果找不到資源就設定下面這 repo

`sudo add-apt-repository ppa:phablet-team/tools`

`sudo apt-get update`


如果系統沒有 add-apt-repository 的指令，就請安裝下面這兩個東西

`sudo apt-get install python-software-properties`

`sudo apt-get install software-properties-common`




參考資料：

https://github.com/libimobiledevice/libimobiledevice/issues/31

https://gist.github.com/kfatehi/8922430

http://www.arthurtoday.com/2010/09/ubuntu-add-apt-repository.html

http://codeblog.vurdalakov.net/2016/05/howto-install-adb-and-fastboot-on-rpi.html



