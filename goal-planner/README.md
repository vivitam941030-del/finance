# 🎯 目標理財規劃器

以 PV（現值）、FV（終值）、PMT（每期投入）為核心的目標導向理財工具。選擇或自訂一個理財目標，即時得到分析與建議。

## 功能

- 預設目標：退休金、買房頭期款、子女教育、緊急預備金，也可自訂
- 考慮通膨，換算目標在未來真正需要的金額
- 反推四個關鍵數字：每月需存（PMT）、現在需一筆（PV）、所需報酬率、達標年數
- 資產成長路徑圖、依缺口自動產生的建議、保守／基本／樂觀三種情境
- 支援手機與深色模式

計算假設：月複利、月底投入、報酬率與通膨率固定。結果僅供規劃參考，不構成投資建議。

## 專案結構

```
goal-planner/
├── public/
│   ├── index.html    # 網站本體（HTML、CSS、JS 都在這一個檔案）
│   └── _headers      # Cloudflare Pages 回應標頭
├── package.json
├── .gitignore
├── LICENSE
└── README.md
```

純靜態網站，不需要安裝套件或 build。

## 本機預覽

直接用瀏覽器開啟 `public/index.html` 即可。
或執行 `npm run dev`（需要 Node.js，會用 Wrangler 啟動本機伺服器）。

## 上傳到 GitHub

1. 在 GitHub 建立新的 repository（例如 `goal-planner`），不要勾選自動建立 README。
2. 在本資料夾開啟終端機，執行：

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<你的帳號>/goal-planner.git
git push -u origin main
```

## 部署到 Cloudflare Pages（連結 GitHub，推薦）

1. 登入 Cloudflare Dashboard，進入「Workers & Pages」。
2. 點「Create」→「Pages」→「Connect to Git」，授權並選擇 `goal-planner` repository。
3. 設定：
   - Framework preset：`None`
   - Build command：留空
   - Build output directory：`public`
4. 點「Save and Deploy」，完成後會得到 `xxx.pages.dev` 網址。之後每次 push 到 `main` 都會自動重新部署。

## 其他部署方式

不透過 GitHub，直接用指令部署：

```bash
npm run deploy
```

第一次執行會要求登入 Cloudflare，專案名稱可在 `package.json` 修改。
