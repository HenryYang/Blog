---
title: "重設 Jailbreak 後的 iOS root 密碼"
draft: false
date: 2017-07-29
tags: ["ios", "JB", "root", "忘記密碼"]
---


就有時候會忘記自己當時到底把 iOS 的 root 密碼改成什麼，這時候有幾種選擇。

<center>
![](1.png)
</center>

<!--more-->


#### 方式一，已安裝 AFC2

如果你安裝了 AFC2 其實就可以直接插電腦，然後用常見的 iOS 管理程式(iMazing、iFunbox 或是你相信中國的 itools？)直接進入到系統目錄。

#### 方式二，無法安裝 AFC2

這時候就看看 iOS 裝置內有無 iFile 這類的檔案管理軟體，直接在手機上面做修改。


主要的方式就是想辦法切換到 `/private/etc/` 目錄，這時候有一個檔案叫做 `master.passwd` 複製回電腦或是直接用 iOS 設備開啟。

然後在電腦上用記事本或是任何文字編輯器打開，這時後你會看到一個以 `root:/` 開頭以 `:System`結尾的文字然後中間帶有一些亂數，而中間就是你被加密過後的密碼。

這時候很間單，把原本以`root:/` 開頭以 `:System`結尾的文字替換成 `root:/smx7MYTQIi2M:0:0::0:0:System`這組，因為這組就是預設密碼 alpine 的雜湊。所以在電腦修改好後把它覆蓋回到 iOS 裝置上。這樣 root 密碼就可以變回原本的 alpine，然後就可以登入或是自行修改密碼


參考資料：

[http://www.bytetips.com/reset-iphone-4s-root-password-to-alpine/](http://www.bytetips.com/reset-iphone-4s-root-password-to-alpine/)



