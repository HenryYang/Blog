---
title: "使用 Github Action 自動編譯並發布 Hugo 產生的頁面到 Github Pages"
draft: false
date: 2021-03-27
tags: ["CI", "git"]
categories: ["程式技術"]
---


Hugo 這類產生靜態網頁檔的東西的好處就是如果搭配上了 git + CI 做自動編譯，那就可以達到只需要一個文字編輯器就能發布新文章的好處

過去是使用 Travis CI 但因為它的免費時數用完了，所以就改成同樣免費的 Github Action，而且有人寫好模組了，更方便更簡單。

<!--more-->


### 預先準備工作1 : 建立 Github Personal Access Token

連結：https://github.com/settings/tokens

這個的用途是當你存需要用 Hugo 編譯的原始碼與實際部屬靜態網頁的 Repo 為不同時所需要的，如果是同一個 Repo 其實可以不用。

但我是建議都申請下來，然後保存好方便使用。

`要記得的是 repo 類的授權要全勾，剩下的可以都不用勾。`

![](https://docs.github.com/assets/images/help/settings/token_scopes.gif)




### 預先準備工作2 : 把 Github Personal Access Token 放到

連結：https://github.com/<你的Github帳號>/<你的Repo名稱>/settings/secrets/actions/new

這時候把剛剛上面產生出來的 Personal Access Token 填入 `Value` 的部分，然後 `Name` 的部分則是依照你的 Github Action 中的 main.yml 所設定的名稱來填

我這邊填寫的名稱是 `PERSONAL_TOKEN`

![](https://itknowledgeexchange.techtarget.com/coffee-talk/files/2020/11/github-actions-secrets-tokens.png)


### 設定 : 建立 Github Action 檔案

就是在存放有需要用 Hugo 編譯的原始碼的那個 Branch 下依照這路徑建立 `.github/workflows/main.yml` 檔案

下面範例中，請把 `<>` 內的東西換成自己的數值，然後都不用加上雙引號或是單引號，直接把包含 `<>` 的字串都刪除後填入自己的數值

當修改完成後，只要 commit 並 push 到 github 後，就可以到自己的 actions 頁面看狀態了。


這邊附上我實際在用的 `.github/workflows/main.yml` 所使用連結 

https://github.com/HenryYang/kb_source/blob/master/.github/workflows/main.yml

~~~
[core]
name: Build Hugo and Deploy
on:
  push:
    branches:
      - <你來源的Branch>
jobs:
  build-deploy:
    runs-on: ubuntu-18.04
    steps:
      - uses: actions/checkout@v1
      
      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: '0.80.0'
          
      - name: Build
        run: hugo
        
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          personal_token: ${{ secrets.PERSONAL_TOKEN }}
          external_repository: <你的Github帳號名>/<你預期部屬到的專案名稱>
          publish_dir: ./public 
          publish_branch: <你預期部屬到的Branch>
          cname: <如果有自訂網域這行寫你的網域，不然整行刪除即可>
~~~




參考資料

[https://medium.com/progressing-up/使用-github-action-部署部落格-hugo-a37fa5295b32](https://medium.com/progressing-up/使用-github-action-部署部落格-hugo-a37fa5295b32)

[https://medium.com/flutter-community/flutter-web-github-actions-github-pages-dec8f308542a](https://medium.com/flutter-community/flutter-web-github-actions-github-pages-dec8f308542a)
