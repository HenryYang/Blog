---
title: "在 ESXI 下擴充有分割 swap 分割區的磁碟"
draft: false
date: 2018-03-04
tags: ["ESXI", "Linux"]
categories: ["程式技術"]
---


***狀況簡介，如果該系統還有 swap 分割區就先需要把 swap 分割區改成 swap 檔案才能做擴充。(就是一步一步做下去)***

***如果該系統已經有 swap 檔案，請確定有安裝 parted 後直接做 Step1、Step2、Step18 然後跳 Step22 開始擴充就可以，不需要再做前面的修改 swap 步驟***


<!--more-->


![](https://hiy.tw/coding/esxi_swap/1.png)


### Step1: 在 ESXi 調整磁碟影像檔案大小之後, 要讓 VM 的檔案系統變大, 但是有一個 swap 分割區的狀況的處裡方式


### Step2:  強制作業系統更新硬碟大小

`sudo echo 1 > '/sys/class/scsi_disk/0:0:0:0/device/rescan'`


### Step3: 先看分割區狀態, 有 swap 分割區, 所以要先建立 swap 檔案, 然後加 swap 檔案, 關閉 swap partition
`sudo fdisk -l /dev/sda`


### Step4: 沒有裝 parted, 所以要裝一下
`sudo apt-get install parted`


### Step5: 用 parted 再看一下分割區
`sudo parted /dev/sda`




### Step6: 確認目前檔案系統空間
`df -h`


### Step7: 建立一個 1GB 的檔案
`sudo fallocate -l 1G /mnt/1GB.swap`


### Step8: 把檔案格式化成 swap 的檔案系統
`sudo mkswap /mnt/1GB.swap`


### Step9: 啟用 swap 檔案
`sudo swapon /mnt/1GB.swap`


### Step10: 確認檔案屬性
`sudo ls -lh  /mnt/1GB.swap`


### Step11: 修改屬性為 600
`sudo chmod 600  /mnt/1GB.swap`


### Step12: 確認檔案屬性
`ls -lh  /mnt/1GB.swap`




### Step13: 編輯 fstab 檔案, 加上新行內容如下 , 註解掉原來的 swap 分割區
`sudo vim /etc/fstab`

**/mnt/1GB.swap  none  swap  sw 0  0**



### Step14: 編輯 sysctl.conf, 加上新行內容如下
`sudo vim /etc/sysctl.conf`

**vm.swappiness=10**



### Step15: 確認 swap 檔案狀態
`sudo swapon -s`


### Step16: 關閉 swap, 記得要確認 swap 使用狀態
`sudo swapoff -a`


### Step17: 啟動 swap
`sudo swapon -a`


### Step18: 在 parted 裡面執行下列指令
`sudo parted /dev/sda`


### Step19: 顯示目前分割區狀態
(parted) `print`


### Step:20 刪除 swap 分割區
Model: VMware Virtual disk (scsi)

Disk /dev/sda: 34.4GB

Sector size (logical/physical): 512B/512B

Partition Table: msdos

Disk Flags:


Number  Start   End     Size    Type      File system     Flags

 1      1049kB  16.4GB  16.4GB  primary   ext4            boot

 2      16.4GB  17.2GB  749MB   extended

 5      16.4GB  17.2GB  749MB   logical   linux-swap(v1)


(parted) `rm 5`


### Step21: 刪除延伸分割區
(parted) `print`

Model: VMware Virtual disk (scsi)

Disk /dev/sda: 34.4GB

Sector size (logical/physical): 512B/512B

Partition Table: msdos

Disk Flags:


Number  Start   End     Size    Type      File system  Flags

 1      1049kB  16.4GB  16.4GB  primary   ext4         boot

 2      16.4GB  17.2GB  749MB   extended


(parted) `rm 2`


### Step22: 確認分割區是否都正確
(parted) `print`

Model: VMware Virtual disk (scsi)

Disk /dev/sda: 34.4GB

Sector size (logical/physical): 512B/512B

Partition Table: msdos

Disk Flags:


Number  Start   End     Size    Type     File system  Flags

 1      1049kB  16.4GB  16.4GB  primary  ext4         boot


### Step23: 執行下面的指令讓分割區最大化
(parted) `resizepart 1 yes 100%`


### Step24: 然後會顯示下面的訊息
Warning: Partition /dev/sda1 is being used. Are you sure you want to continue?


### Step25: print 指令顯示現在分割區狀態
(parted) `print`

Model: VMware Virtual disk (scsi)

Disk /dev/sda: 34.4GB

Sector size (logical/physical): 512B/512B

Partition Table: msdos

Disk Flags:


Number  Start   End     Size    Type     File system  Flags

 1      1049kB  34.4GB  34.4GB  primary  ext4         

 

### Step26: 結束 parted
(parted) `quit`


### Step27: 檢查檔案系統空間
`df -h`


### Step28: 更新檔案系統大小
`sudo resize2fs -F /dev/sda1`


### Step29: 檢查檔案系統空間
`df -h`



