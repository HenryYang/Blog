---
title: "Thunderbolt 的碎碎念比較"
draft: false
date: 2016-11-26
tags: ["Thunderbolt", "Type-C"]
---


就新版的 Macbook Pro 也正式支援 Thunberbolt 3 了，但是規格真的有點複雜，所以在這邊整理一下。

就以下圖來看，我們可以很明顯的發現到 Thunderbolt 1 與 2 都是使用上面款式的接口，而 Thunderbolt 3 則是使用下圖的接口。

<!--more-->

<center>
![](1.jpeg)
</center>


從過去的到現在， Thunderbolt 都是依附別種協定的接頭來使用，像是 Thunderbolt 1 與 2 就是使用跟 Mini Display Port 的接頭而Thunderbolt 3 則是使用 USB Type-C 外觀的接頭。

也因為 Thunderbolt 是依附在別種協定之下的，所以如果你主機的 Thunderbolt 使用接頭為 Mini Display Port 外觀的，那就也會支援 Mini Display Port 功能。然後 Thunderbolt 3 其實是透過 USB Type-C 來支援的，但也因為 USB Type-C 能支援的協定有太多，所以這需要自行確認到底主機上的 USB Type-C 還有支援什麼協定。

**理論上** 如果 Mini Display Port 或 USB Type-C 接口上有一個閃電圖示就是代表有支援 Thunderbolt 協定，然後如果有一個閃電 3 的圖示則就是支援 Thunderbolt 3 協定，但很不幸的是 Apple 在新款的 Macbook Pro 並沒有依照規定加上圖示。

### 請記得，  Thunderbolt 與原接頭的線材不可以混用，因為其中的晶片不同，所以不一定會相容！


Thunderbolt 1 與 2 可能會發生的狀況

* Mini Display 的螢幕 + Thunderbolt 傳輸線，就算主機的孔同時支援 Mini Display 與 Thunderbolt 也還是無法使用，因為Thunderbolt 傳輸線無法單純傳輸影像訊號
* Thunderbolt 的螢幕 + Thunderbolt 傳輸線 + 只有 Mini Display 功能的主機也還是無法使用，因為雖然插頭一樣也可以插上，但因為螢幕走的協定無法被電腦認識所以無法使用
* Thunderbolt 的螢幕 + Mini Display 傳輸線 + 同時支援 Mini Display 與 Thunderbolt 的電腦同樣無法使用，因為中間的線材無法傳輸 Thunderbolt 訊號，所以一樣無法使用

Thunderbolt 3 可能會發生的狀況

* Thunderbolt 外接設備 + USB Type-C 傳輸線 +  同時支援 USB 3.1 與 Thunderbolt 的電腦這是同樣是無法使用，因為 USB Type-C 傳輸線沒有 Thunderbolt 晶片因此無法辨識
* USB 3.1 (USB Type-C 外觀) 外接設備 + Thunderbolt 傳輸線 + 只支援 USB 3.1 的電腦，這樣是可以使用的，但至於是跑 USB2.0 還是  USB 3.1 的速度就要看線材的品質了

Thunderbolt 組合技可能會發生的狀況

* 目前蘋果有出一條 Thunderbolt 2 與 Thunderbolt 3 互轉的傳輸線，所以外觀就是 USB Type-C 與 Mini Display Port ，但請記得他是沒有辦法讓 Thunderbolt 3 或是  USB Type-C 的設備去支援 Mini Display Port 的，雖然外觀一樣而且又插的上去，但他就真的只有 Thunderbolt 的功能並沒有其他原本它那接頭會有的協定。

### 結論

自從 USB Type-C 出現後，請看清楚設備支援的協定，並且也確認線材支援的協定，不要像過去一樣只要是 USB 就管他三七二十一的插上去了，在  USB Type-C 時代這可是會讓你吃到苦頭的。





