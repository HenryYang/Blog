---
title: "SSH 使用特殊阜來執行 Wordpress 線上更新"
draft: false
date: 2016-08-01
tags: ["SSH", "Wordpress"]
---


### SSH 使用特殊阜來執行 Wordpress 線上更新

如果因為安全因素所以沒有開啟 FTP 服務，這樣就無法用 Wordpress 內建的線上更新執行系統、佈景或是外掛的更新，需要直接登入遠端主機修改或是直接覆蓋檔案來更新。

<!--more-->


<center>
![](1.png)
</center>


但目前有個名為 <a href="https://wordpress.org/plugins/ssh-sftp-updater-support/">SSH SFTP Updater Support</a> 的外掛是可以用 UNIX 主機常見的 SSH 來取代原本的 FTP 登入驗證，然後透過 SSH 來達到線上更新。

但這邊要分享一個小經驗就是如果你跟我一樣習慣都會把 SSH 所使用的阜換成非預設的，這時候通常你會找遍設定檔但還是找不到那邊可以修改，其實很簡單，就是在主機位置的地方直接冒號接上你的阜號即可。


<center>
![](2.png)
</center>




