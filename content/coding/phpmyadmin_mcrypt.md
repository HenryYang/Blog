---
title: "phpMyAdmin 出現 '缺少 mcrypt 擴充套件' 解決方法"
draft: false
date: 2015-11-28
tags: ["MySQL", "phpMyAdmin"]
---


目前在各版本 Linux 上所安裝 MySQL 後理論上都會把相關套件裝起來，所以當你確定你有裝過 mcrypt 但是系統又是一直在跳警示，可能會是模組沒有被啟用，所以可以嘗試看看以下指令把模組啟用起來

註：需要最高權限或是使用 sudo 來執行

### 啟用 mcrypt 模組
sudo php5enmod mcrypt

### 重新啟動 Apache 服務
sudo service apache2 restart


這樣再重新登入 phpMyAdmin 就不會再跳出警示了

