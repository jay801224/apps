# 我的作品集網站

單檔靜態網站（`index.html`），展示我用 AI 打造的 App 與遊戲，以及背後的開發基礎建設。

🔗 已上線：**https://jay801224.github.io/apps/**

## 網站裡有什麼

### 🐱 收錄的作品
| 作品 | 類型 | 通路 | 介紹 |
|---|---|---|---|
| **NyanVeil（喵紗）** | iOS App | App Store | 溫馨療癒的養貓收集遊戲，收集並照顧各式各樣的貓咪。 |
| **貓語研究所（MeowLinguistics）** | iOS App | App Store | 用學術出處詮釋貓咪叫聲，解讀每一聲「喵」背後的含義。 |
| **Inkwhisker（墨鬚貓）** | Web 遊戲 | itch.io（瀏覽器免費玩）/ Ko-fi | 俯視角 2D 動作遊戲：墨繪小貓揮舞發光的麒麟尾，在古卷軸的水墨世界用書法電光魔法迎戰水墨怪物。 |

### 📊 其他展示區塊
- **AI 自動化測試** — 前後端自動化測試框架的彙總數據（92 測試情境、25 套件檔、325+ 斷言、13 分類）。
- **我的 Claude Skills** — 為 Claude Code 打造的 77 個可重複使用 skill，依專案類型分類、自動部署。
- **雙系統 Sync 機制** — Windows ⇄ macOS 兩台機器以「單一來源」保持設定與能力一致的同步機制。

## 網站結構
整個網站是**單一檔案** `index.html`（HTML + 內嵌 CSS，無框架、無 build、零相依）。由上到下分為：

1. **Hero** — 標題與一句話定位
2. **作品卡片列表** — 上方的作品卡（App / 遊戲）
3. **AI 自動化測試** — 數據統計區
4. **我的 Claude Skills** — 分類卡片
5. **雙系統 Sync 機制** — 流程說明
6. **Footer** — 版權

同資料夾的 `*.png` 是各作品的圖示（如 `nyanveil.png`、`meowlinguistics.png`、`inkwhisker.png`）。

## 設計樣式
走「暖墨工作室」調性，刻意避開 AI 常見的藍紫漸層：

- **配色** — 深墨綠近黑的背景 + 銅金色（`#d9a441`）全站重點色；每張卡片可用 `--app` 個別覆寫重點色（影響圖示底色、標語、左側邊條）。
- **字體** — 本文用系統 UI 字體堆疊；標題與標籤用等寬字體，做出「獨立開發者」的簽名感。
- **間距 / 圓角** — 以 8pt 間距尺度與一組圓角 token 統一管理。
- **動態** — 收尾減速的彈簧 easing；hover 時卡片上浮、左側重點色邊條長出、圖示微旋轉、按鈕有斜向光澤掃過。
- **響應式** — 手機（≤540px）自動切換為圖示置頂的直式置中排版。
- **無障礙** — 尊重系統「減少動態」偏好，會關閉位移 / 旋轉 / 光澤動畫。

## 怎麼修改
打開 `index.html`，看 `<!-- 如何新增一個 App -->` 的註解：

- 改圖示、名稱、標語、介紹
- **通路按鈕**：每顆按鈕上方都有 `<!-- STORE: xxx -->` 標記，沒有的通路就整段刪掉。檔案最後的範本區已備好 App Store / Google Play / Microsoft / Mac / itch.io / Ko-fi 六種按鈕，需要哪個複製哪個。
- **圖示**：把 `<div class="icon">A</div>` 換成 `<div class="icon"><img src="icon.png" alt="圖示"></div>`，圖檔放進同資料夾。
- **新增作品**：整段 `<article class="card">...</article>` 複製貼上後改內容。

## 部署與上線方案
這是一個對外公開的網站。目前用 **GitHub Pages** 上線：推送到 `master` 後會自動重新部署，幾分鐘內生效。

如果之後想換平台，以下都是免費（NT$0）方案，把整個資料夾丟上去即可：

### 方案 A：Cloudflare Pages（推薦）
1. 註冊 https://pages.cloudflare.com
2. 選「Direct Upload / 直接上傳」→ 把整個資料夾拖上去
3. 得到網址 `xxx.pages.dev`

### 方案 B：GitHub Pages
1. 建 repo，推上 `index.html`
2. Settings → Pages → Source 選分支（本專案為 `master`）→ 存檔
3. 得到 `帳號.github.io/repo`

### 方案 C：Vercel
1. 註冊 https://vercel.com → Import → Deploy
2. 得到 `xxx.vercel.app`
