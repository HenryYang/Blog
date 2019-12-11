---
title: "Linux 用 PAM 限制使用者登入"
draft: false
date: 2016-10-12
tags: ["PAM", "Linux"]
categories: ["程式技術"]
---


### 修改 /etc/security/access.conf 這檔案

然後在這檔案中新增下面指令 ( 請把下面的 root 跟 systemadmin 換成你自己的帳號 )

    -:ALL EXCEPT root sysadmin:ALL
	
<!--more-->
		
### 接下來是修改 P

**/etc/pam.d/login** 是負責處理 tty1 而 **/etc/pam.d/sshd** 則是處理 SSH 登入的

然後請加上下面這指令來啟用原則

    account required pam_access.so
		
		
然後登出後在登入就會生效了，你會發現如果 SSH 輸入錯密碼或是請你重新輸入但是如果輸入正確反而是直接中斷連線就是設定成功。


