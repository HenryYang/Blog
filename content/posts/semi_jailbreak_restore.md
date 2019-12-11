---
title: "Semi Jailbreak 回復出廠設定但仍保有 Jailbreak 方式"
draft: false
date: 2017-07-24
tags: ["iOS", "Jailbreak"]
categories: ["科技新知"]
---


這主要發生情況或是在於當你有一個 iOS 9 或是 10 的 Jailbreak 但手機需要轉售或是借人因此需要把手機清乾淨但又還是想保留 Jailbreak 時使用的。

註：Semi Jailbreak 就是在 iOS 9 或 10 常見的 Jailbreak 方法，之所以稱 semi 因為每一次重新開機系統的 Jailbreak 就會喪失需要重新在執行一次 Jailbreak 程式才能在拿回來權限。

<!--more-->

所需軟體：

* [iMazing](https://imazing.com/)
* 該 iOS 所需的 Jailbreak 軟體 [iOS9](http://en.pangu.io/help.html)、[iOS10](https://www.reddit.com/r/jailbreak/comments/5r45cg/news_lmao_luca_really_put_it_on_his_website/)
* [Cydia Patch](https://mega.nz/#!tptRATha!3k5mV8S4Jusm3S2QqsnVXDVxuz0nsoDsTprmgjK09pY)

## Step0: 把不需要的 Cydia Tweak 先移除，然後把手機重開機

因為 Cydia Tweak 是安裝在系統分割區，所以這種的回復出廠設定後主程式還是會在，因此請先自己手動移除，然後移除完後重開機是為了讓系統變回未 Jailbreak 狀態。

## Step1: 手機重開機後使用 iMazing 將 iOS 設備回復出廠設定

請記得不要使用 iTunes 回復，因為他一定會回復成最新版。然後使用手機內建的回復會導致白蘋果。所以請務必使用 iMazing 內的 Erase All Content 來清除資料。


![](https://hiy.tw/tech/semi_jailbreak_restore/1.png)


## Step2: 回復完成後請直接在執行 Jailbreak 程式一次

這時候你會發現你系統變成乾淨的，但是 Cydia 跟 Cydia Tweak 都還是存在的。這時候理論上打不開，所以請直接執行你的 Jailbreak 程式來重新的 Jailbreak。

## Step3: Cydia 跳出錯誤，請將 Patch 放入系統目錄

就 Jailbreak 成功後理論上你會跳出 Could Not Open File /var/lib/dpkg/status，因為 Cydia 很多 manifest 檔案也不是存放在系統分割區因此就再上一次用 iMazing 時被清掉了。然後你使用 Jailbreak 程式時他又發現你已經有 Cydia 所以它就也沒有幫你重新寫入那些 manifest 檔案，因此就跳錯誤了。

這時候就是可以用 iMazing 的 File System 或是其他可以管理目錄的軟體把下載回來的 zip 檔直接放入到 /var 這目錄下然後解壓縮，這時候重新把 Cydia 開啟理論上就能正常開啟了。


## Step4: 原有 Cydia Tweak 全部重新安裝一次

就這時候理論上你已經獲得到一台乾淨且有 Cydia 的 Jailbreak iOS 裝置，但就如同我剛剛說的，因為 Cydia 很多 manifest 檔案都不見了，所以就算該 Cydia Tweak 之前就已經安裝在手機內的但 Cydia 還是會顯示未安裝。

因此就是把手機有的 Cydia Tweak 全部再重新安裝一次，讓 Cydia 知道你有安裝過這 Tweak 這樣有更新的時候才會收到通知。


![](https://hiy.tw/tech/semi_jailbreak_restore/2.png)



## 參考資料


[https://www.reddit.com/r/jailbreak/comments/5r45cg/news_lmao_luca_really_put_it_on_his_website/](https://www.reddit.com/r/jailbreak/comments/5r45cg/news_lmao_luca_really_put_it_on_his_website/)
[http://bbs.feng.com/read-htm-tid-11055525.html](http://bbs.feng.com/read-htm-tid-11055525.html)
[https://www.reddit.com/r/jailbreak/comments/5rtckg/tutorial_how_to_fix_varlibdpkgstatus_error/](https://www.reddit.com/r/jailbreak/comments/5rtckg/tutorial_how_to_fix_varlibdpkgstatus_error/)




