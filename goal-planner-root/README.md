# 🎯 目標理財規劃器

以 PV（現值）、FV（終值）、PMT（每期投入）為核心的目標導向理財工具。選擇或自訂理財目標，即時得到分析與建議。結果僅供規劃參考，不構成投資建議。

## 專案結構

```
.
├── index.html     # 網站本體（HTML、CSS、JS 都在這一個檔案）
├── _headers       # Cloudflare Pages 回應標頭
├── package.json
├── .gitignore
├── LICENSE
└── README.md
```

純靜態網站，不需要安裝套件或 build。`index.html` 就在最外層。

## 上傳到 GitHub

1. 在 GitHub 建立新的 repository，不要勾選自動建立 README。
2. 在「有 index.html 的這個資料夾裡」開啟終端機，執行：

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<你的帳號>/goal-planner.git
git push -u origin main
```

3. 推上去後，打開 GitHub repository 首頁，應該直接看到 `index.html`。

## 部署到 Cloudflare Pages

1. Cloudflare Dashboard →「Workers & Pages」→「Create」→「Pages」→「Connect to Git」。
2. 選擇你的 repository。
3. 設定：
   - Framework preset：`None`
   - Build command：留空
   - Build output directory：留空（或填 `/`）
4. 點「Save and Deploy」。

注意：請選 Pages 流程。若畫面出現「Deploy command」欄位，代表建立成了 Workers 專案，請回頭重建。
