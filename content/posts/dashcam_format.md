---
title: "讓行車記錄器的記憶卡壽命更長 - 只格式化部分空間"
draft: false
date: 2021-05-03
tags: ["camera", "SD_Card"]
categories: ["生活技巧"]
---


因為記憶卡這類產品所使用的快閃記憶體的物理特性來說，最忌諱的就是一直空間處於滿載狀態

這會容易會讓它內建的控制晶片無法好好發揮該有的控制效果，輕則存取速度變慢，重則是可能讓壽命減短

<!--more-->


所以解決方法很簡單，就是在格式化記憶卡的時候不要把全部的空間都劃分出去

反正現在的記憶卡容量都是有夠大，只格式化原本的 70-80% 都還是有很大的空間

我知道一定很多人會說，為什麼不買更大的就好，因為人都有惰性，通常只有要上網罵人時才會記得把記憶卡拿下來

平常無論放多大，記憶卡都是會一直被寫滿，然後只會一直複寫最後一點點空間。這就容易造成損壞

所以如果行車記錄器可以設定儲存上限也是可以一併設定的



### 在 macOS 下指分割部分的方式

~~~
# 列出現在所有的磁碟
$ diskutil list
~~~

```
# 通常會類似這樣，然後可以從 NAME 這邊去判斷知道說 disk2 是我的記憶卡
/dev/disk0 (internal, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *1.0 TB     disk0
   1:                        EFI EFI                     314.6 MB   disk0s1
   2:                 Apple_APFS Container disk1         1.0 TB     disk0s2


/dev/disk2 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     FDisk_partition_scheme                        *64.1 GB    disk2
   1:             Windows_FAT_32 NO NAME                 64.1 GB    disk2s1
```

~~~
# 接著用 partitionDisk 這指令來把分成兩個分割區，其中第一個是 FAT32 格式，名稱叫 NO NAME 且空間為 48GB
# 至於 free free 0 則表示剩餘的都不使用 
$ diskutil partitionDisk disk2 2 GPT "MS-DOS FAT32" "NO NAME" 48GB  free free 0
~~~
