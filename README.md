# 我的 App 作品集網站

單檔靜態網站(`index.html`),展示跨平台 App,連到 App Store / Google Play / Microsoft Store / Mac App Store。

## 設計重點
- 卡片式版面:左邊 App ICON、右邊資訊(名稱 / 標語 / 介紹 / 下載按鈕)
- **只顯示有上架的平台** — 沒上架的就把那顆按鈕整段刪掉,不會出現
- 深色主題、手機自動切換為 ICON 置頂的直式排版

## 怎麼預覽
用瀏覽器打開 `index.html`。

## 怎麼修改
打開 `index.html`,看 `<!-- 如何新增一個 App -->` 的註解:
- 改 ICON、名稱、標語、介紹
- **平台按鈕**:每顆下載按鈕上方都有 `<!-- STORE: xxx -->` 標記。某平台沒上架,就把那顆 `<a class="store">...</a>` 整段刪掉
- **真實圖示**:把 `<div class="icon">A</div>` 換成 `<div class="icon"><img src="icon-a.png" alt="App 圖示"></div>`,並把圖檔放進同資料夾
- **新增 App**:整段 `<article class="card">...</article>` 複製貼上後改內容

## 怎麼免費上線(三選一,皆 NT$0)

### 方案 A：Cloudflare Pages(推薦)
1. 註冊 https://pages.cloudflare.com
2. 選「Direct Upload / 直接上傳」→ 把整個資料夾拖上去
3. 得到網址 `xxx.pages.dev`

### 方案 B：GitHub Pages
1. 建 repo,推上 `index.html`
2. Settings → Pages → Source 選 main → 存檔
3. 得到 `帳號.github.io/repo`

### 方案 C：Vercel
1. 註冊 https://vercel.com → Import → Deploy
2. 得到 `xxx.vercel.app`

## ⚠️ 重要:上線 = 公開
部署到上述任一平台後,**任何有網址的人都看得到**,搜尋引擎也可能收錄。
上線前確認頁面上沒有不想公開的私人資訊(email、未發布的 App 等)。
免費平台一般沒有「限特定人觀看」功能,需要密碼保護通常得用付費方案。
