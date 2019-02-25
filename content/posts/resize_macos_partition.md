---
title: "在 VMware 下 MacOS 重新調整分割區大小"
draft: false
date: 2016-12-17
tags: ["macOS", "VMware"]
---


我自己會遇到這情況是在當 VM 的虛擬磁碟已經調整完大小，但是 MacOS 虛擬機中的作業系統並無法自己動態調整

<center>
![](https://hiy.tw/coding/resize_macos_partition/1.png)
</center>

<!--more-->

所以需要下指令手動調整

這指令用來先確認你的調整的硬碟系統代號為何（ 就是 IDENTIFIER 這欄位）

```  diskutil list ```


然後就可以輸入

```diskutil resizeVolume  剛剛上面找到的名稱 你要的容量```

然後系統就會開始執行，只要執行完成沒有錯誤就可以重開機，重開完就可以看到分割區容量變大了



參考資料：

http://www.macworld.com/article/1055274/software-utilities/marchgeekfactor.html







