---
title: "iOS 砸殼步驟"
draft: false
date: 2017-07-29
tags: ["ios", "JB", "砸殼", "dumpdecrypted"]
---

<center>
![](https://hiy.tw/tech/ios_dumpdecrypted/1.png)
</center>

<!--more-->

#### Step1:
在電腦以 root 遠端使用 SSH 登入 iOS 設備 

#### Step2:
在 iOS 設備端開啟想砸殼的 App 然後在 shell 端使用 `ps -e` 來看詳細路徑，並且記下來

#### Step3:
輸入 `cycript -p 要砸殼的App名稱` 

#### Step4:
在出現 `cy#` 後輸入 `[[NSFileManager defaultManager] URLsForDirectory:NSDocumentDirectory inDomains:NSUserDomainMask][0]` 來找到該 App 的文件夾路徑並記錄下來

#### Step5:
把 `dumpdecrypted.dylib` 複製到 Step4 所找到的 App 文件夾路徑

註：需要自行先把你 iOS 設備版本的 dumpdecrypted.dylib 編譯好，原始碼[請參考這](https://github.com/stefanesser/dumpdecrypted/)


#### Step6:
輸入 `DYLD_INSERT_LIBRARIES=dumpdecrypted.dylib 在Step2所找到的App路徑`，這時候就會開始砸殼

#### Step7:
砸殼完成該目錄就會產生一個副檔名是 .decrypted 的文件，這就是砸殼後的未加密檔案，請自行帶回電腦。


參考資料：

[http://www.jianshu.com/p/14db1ac34bf1](http://www.jianshu.com/p/14db1ac34bf1)
[http://www.jianshu.com/p/a4373b5feca0](http://www.jianshu.com/p/a4373b5feca0)








