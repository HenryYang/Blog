---
title: "用 MacOS 安全的抹除硬碟 ( CLI 與 GUI 教學 )"
draft: false
date: 2016-09-18
tags: ["macOS", "CLI"]
categories: ["程式技術"]
---


當硬碟要賣出或是要借人時，如果你覺得自己的過去已經刪除的資料很機密或是很見不得人，可以先把硬碟抹除乾淨，格式化與抹除的差異在於格式化只是修改了硬碟的檔頭，所以還是很有機會可以把資料救回來，而抹除則是寫入無意義的資料來佔滿空間，讓資料救援變的 "比較" 不可能。

<!--more-->

### GUI 教學

開啟磁碟管理工具，然後點選你的抹除的分割區，並且按下 "清除" 然後你就會看到左下方有安全層級可以選擇，左邊是不抹除而右邊則是最安全的 DOD 建議抹除等級，當然越安全越久。當選擇好後，就按下清除就可以了。


![](https://hiy.tw/tech/macos_format_cli_gui/1.png)




![](https://hiy.tw/tech/macos_format_cli_gui/2.png)




### CLI 教學

如果你就是耍帥，覺得文字介面比較帥也可以用下方指令來達成抹除的目的，然後請務必記得把下方指令的 "Macintosh HD" 換成你要抹除的名稱，不然你就會抹到你的系統分割區了（但理論上你是抹不了的


diskutil secureErase freespace 3 "/Volumes/Macintosh HD"



上方指令的數字部分就是安全係數，可以參考下面的解說，其實 2 就是剛剛圖形化最安全等級的抹除。

0 – Single-pass zero-fill erase.

1 – Single-pass random-fill erase.

2 – US DoD 7-pass secure erase.

3 – Gutmann algorithm 35-pass secure erase.

4 – US DoE algorithm 3-pass secure erase.



### 結論

其實我不懂抹除硬碟的原因，因為真的有裝過敏感資料的不是應該用物理銷毀（榔頭？！）才是真正安全的嗎？







