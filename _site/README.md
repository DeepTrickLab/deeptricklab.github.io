## 實驗室網站
本專案使用 Github Pages 以及 [Jekyll](https://jekyllrb.com/) 完成。Jekyll 使用 Markdown 完成文章撰寫與互動。因此，在修改之前你必須先熟悉 Markdown 語法，參考文件有：
* [Markdown文件](https://markdown.tw/)
* [Discord - Markdown語法101](https://support.discord.com/hc/zh-tw/articles/210298617)

### 執行
#### 在地測試
* 請先依照 [Jekyll](https://jekyllrb.com/docs/installation/) 完成本地安裝
* 並且將 `Gemfile` 修改成以下
```
# frozen_string_literal: true

source "https://rubygems.org"

# For local depolyment
gem "jekyll"

# Github page depolyment
# git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }
# gem "github-pages", "~> 3.8.7", group: :jekyll_plugins
```
* 最後執行以下指令即可透過 localhost:4000 瀏覽
```
bundle exec jekyll serve
```
#### 上架到 Github
* 完成修改後，請注意 `Gemfile` 是否修改成以下
```
# frozen_string_literal: true

source "https://rubygems.org"

# For local depolyment
# gem "jekyll"

# Github page depolyment
git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }
gem "github-pages", "~> 3.8.7", group: :jekyll_plugins
```
* 確認正確後，執行相關指令 `git commit`, `git push`，Github 會自動更新實驗室網站內容

### 新增成員
* 新增一個空白的 md 檔案在 `_members` 資料夾
* 請注意，Jekyll 是依照檔名排序，所以建議您用學年度加流水號完成排序，並且加上姓名英文拼音 (建議英文，不過中文也可以)。例如：`109_2_WuWeiTing.md`
* 在空白的檔案設定成員資料，模板如下：
```
---
name: 張慶宇 (姓名)
position: 108學年度 (入學學年度或其他職稱)
status: present (在學 present / 畢業 alumni)
profile-picture: (可省略 個人圖片)
home: (可省略不寫的個人網站網址)
mail: (可省略不寫的個人email地址)
github: https://github.com/iomanker (可省略不寫的 Github 地址)
---
(這裡填寫個人介紹)
```
* 其中 `profile-picture` 可以是外頭圖片網址，若要自行上傳圖片需要按照下方的〈新增圖片〉章節

### 新增文章
* 新增一個空白的 md 檔案在 `_posts` 資料夾
* 請注意，Jekyll 是依照檔名排序，所以建議您用日期完成排序。例如：`2022-07-21-reveal-Lab-Site.md` 的 2022-07-21
* 另外，日期後頭需接上文章標題，這同時會顯示在網頁上。例如：`2022-07-21-reveal-Lab-Site.md` (標題不分大小寫，可中文) 的標題自動轉成 `Reveal Lab Site` 
* 在空白的檔案填寫文章內容，模板如下：
```
---
layout: post
---
實驗室網站上架 (文章內文)
```
* 文章內文也可以使用 Markdown 編寫

### 新增圖片
* 只要將圖片放到 `assets/images` 之下並且記得 `git add`，我們就能索引圖片網址
* 以成員放上圖片為例，在 `profile-picture` 加上 `../assets/images/<接下來的對應位置>` (前方的 `..` 須注意加上)
* 例如： `../assets/images/profiles/108_YeChunTing.jpg`

### 修改介紹
* `about.html`, `advisor.html`, `research.html` 都是能直接在檔案中修改 Markdown 文字
* 只要保持 `---` 之間(包含)資訊，就能夠完成編輯

### 雜七雜八
* 該網站介面是使用 Bootstrap5 完成 RWD 切版與規劃
* `404.html` 是用來解決找不到網址的問題
* 若有任何網頁原生問題，直接加入我的 Discord 帳號私訊我 `iomanker#1392`
* 也謝謝學弟學妹，持續協助實驗室網站更新