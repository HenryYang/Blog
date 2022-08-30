---
title: "解決 Windows 測試人員計畫頁面空白問題"
draft: false
date: 2022-08-30
tags: ["windows"]
categories: ["程式技術"]
---

當你想要修改 Windows 測試人員計畫頁 (Windows Insider) 的版本或甚至是退出計畫時  

有可能會遇到該頁面整個空白，或是顯示下面這錯誤訊息。通常大家都建議重灌，但其實可能還有救

<!--more-->

</br>

![](https://i.imgur.com/Z2qV8wa.jpg)


這時候可以做的事情是同時按下 Windows 與 R 鍵叫出執行，並輸入 `services.msc` 叫出 `服務` 這程式  

然後就選擇 `Connected User Experiences and Telemetry` 這服務，不論它是啟用還是停用，就是把它手動給停用後再啟用一次

![](https://i.imgur.com/gJAowO9.jpg)

![](https://i.imgur.com/txs66SP.jpg)

這時候重新把 `設定` 的應用程式關閉並重新開啟後點選 ` Windows 測試人員計畫頁面` 就會看到東西啦


![](https://i.imgur.com/c0jRkWM.jpg)


參考資料: https://www.youtube.com/watch?v=2ZZOPgw5VBk
