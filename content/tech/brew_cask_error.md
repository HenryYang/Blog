---
title: "brew cask 安裝軟體時跳出權限錯誤"
draft: false
date: 2015-12-28
tags: ["Brew"]
---


通常這狀況都是出現在 OSX 10.11 ，因為系統對於根目錄的權限有做調整，因此輸入下列指令來讓目前使用者有權限存取就可以了

<em><strong>$ sudo chown -R $(whoami):admin /etc/Caskroom</strong></em>


