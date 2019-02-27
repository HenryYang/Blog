---
title: "查看公鑰 (Public Key) 的指紋 (fingerprint)"
draft: false
date: 2015-12-28
tags: ["Public Key"]
---


通常在使用 SSH 連線到一台新的主機的時候，系統會跳出該主機的公鑰 (Public Key) 所產生出來的指紋 (fingerprint)，這主要是用來確認我們連線到的機器是正確的與確保沒有遭受到中間人攻擊。
所以如果要確認自己的公鑰指紋，可以用以下的指令來獲得公鑰的指紋

<em><strong>$ ssh-keygen -lf 公鑰名稱</strong></em>


