---
title: "讓 iOS 9 設備也支援台灣信用卡的 Apple Pay"
draft: false
date: 2017-03-29
tags: ["Apple Pay", "Jailbreak", "iOS"]
categories: ["科技新知"]
---


故事前情提要：蘋果表示，Apple Pay 就是要最新版本的才可以用喔 >.^

所以理論上 iOS 10.3 的人就會直接在 Wallet App 中出現新增信用卡的選項，但如果是比較舊一點的版本的人（例如 iOS 10.1.1 ）這類的可以透過修改地區的方式將 iPhone 改為比較早有 Apple Pay 的國家例如美國、日本就可以正常加卡了！

<!--more-->


修改地區的方式：設定 -> 一般 -> 語言與地區 -> 地區，把地區暫時改成美國理論上就會出現新增信用卡的選項了。

### 但是...

如果是 iOS 9 透過上述方法想要啟用台灣 Apple Pay 就會再最後一步跳出請更新系統 Orz

所以這邊提供一個方法來略過 Apple 的檢查，但注意這是需要 JB 的，我想不想升級 iOS 9 又想用台灣 Apple Pay 的人應該都是有 JB 的才對。

步驟零：請先確定 iPhone 已經依照上面教學先把地區切到美國了

步驟一：打開 iFile（如果你不知道它是什麼那我建議你/妳也不用 JB 了，直接還原成最新版本吧 ）

步驟二：到 "/System/Library/CoreServices" 用 "Property List Viewer" 開啟 "SystemVersion.plist" 


![](https://hiy.tw/tech/ios_9_apple_pay_taiwan/1.png)



![](https://hiy.tw/tech/ios_9_apple_pay_taiwan/2.png)



![](https://hiy.tw/tech/ios_9_apple_pay_taiwan/3.png)


步驟三：請把看到的畫面螢幕截圖下來，以供未來還原時參考

步驟四：將 "SystemVersion.plist" 裡面的 "ProductBuildVersion" 改成「14C92」、"ProductVersion" 改成「10.2」

步驟五：新增 Apple Pay

步驟六：一定要記得把步驟四修改的數值改回原本的


![](https://hiy.tw/tech/ios_9_apple_pay_taiwan/4.jpg)


### 注意，請確保在電力充足時操作，並且在完成第六步前千萬不可以重開機，不然 iPhone 就再也無法回到 JB 狀態了


