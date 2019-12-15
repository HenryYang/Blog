---
title: "讓 macOS 使用 Yubikey PIV 智慧卡登入"
draft: false
date: 2019-12-15
tags: ["PIV", "Yubikey"]
categories: ["程式技術"]
---

其實現在 Yubikey 官方已經有推出 GUI 工具可以快速的開啟 PIV 智慧卡功能，這樣就可以讓 macOS 只需要輸入 PIN 就登入

<!--more-->

[官網教學與資訊](h)


## 教學

[下載對應版本的 Yubikey Manager 軟體](https://www.yubico.com/products/services-software/download/yubikey-manager/)

1. 開啟 Yubikey Manager 並選擇 PIV

![](https://hiy.tw/coding/yubikey_piv/1.png)

2. 把預設 PIN 碼與 PUK 碼還有 Management Key 修改掉

```
預設資訊
PIN: 123456 (6-8 characters allowed. macOS requires numeric-only.)
PUK: 12345678 (6-8 characters allowed. macOS requires numeric-only.)
Management Key: 010203040506070801020304050607080102030405060708

```

![](https://hiy.tw/coding/yubikey_piv/2.png)

3. 點選上一張圖的左上方，有一個 Setup for macOS，然後按下確認

![](https://hiy.tw/coding/yubikey_piv/3.png)

4. 這樣就完成了，然後把設備重新插拔，就會跳出配對畫面，並完成設定

![](https://hiy.tw/coding/yubikey_piv/4.png)

![](https://hiy.tw/coding/yubikey_piv/5.png)

5. 之後每次在鎖定畫面，只要有插上 PIV 且綁定過的 Yubikey 就可以 PIN 登入

![](https://hiy.tw/coding/yubikey_piv/6.png)
![](https://hiy.tw/coding/yubikey_piv/7.png)


P.S. 目前測試結果，只有綁定最後的一支 Yubikey 才可以解鎖 Keychain，之前綁定的會無法解鎖



參考資料：

[https://support.yubico.com/support/solutions/articles/15000006468-using-your-yubikey-as-a-smart-card-in-macos](https://support.yubico.com/support/solutions/articles/15000006468-using-your-yubikey-as-a-smart-card-in-macos)






