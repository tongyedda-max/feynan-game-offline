# 訊號教室｜GitHub Pages 多檔發布

這個版本把網站拆成多個靜態檔案，避免單一 HTML 過大。請將 ZIP 解壓後的**全部內容**上傳到 GitHub 儲存庫根目錄，不要只上傳 `index.html`。

```text
你的儲存庫/
├── index.html
└── assets/
    ├── JavaScript 檔案
    ├── CSS 檔案
    ├── fonts.css 及 fonts/*.ttf
    └── 網站圖片
```

`index.html` 和 `assets/` 必須保持上述相對位置。不要改名或移動 `assets` 資料夾；GitHub Pages 會由根目錄載入 `index.html`。

到 GitHub 儲存庫的 **Settings → Pages**，將 Source 設為 **Deploy from a branch**，選擇你的發布分支（通常是 `main`）及 **`/ (root)`**。這個版本不需要建置指令，也不需要 Node.js。

網站採用 hash 路由，適合 GitHub Pages 的靜態託管。根頁是 `/#/`；學生聯絡簿是 `/#/students`；授課紀錄是 `/#/records`；Profile 是 `/#/profile`；指南是 `/#/guide`；戰役資料是 `/#/settings`；範例試跑是 `/#/trial`。這些頁面可以直接加入書籤，不會因 GitHub Pages 的伺服器路由而出現 404。

這是純前端、離線優先網站。課堂進度、人物工坊和設定保存在瀏覽器自己的 localStorage，不會上傳至外部服務。若要由原本的網站轉移進度，請先在「戰役資料」下載 JSON，再在 GitHub Pages 版本匯入。

本多檔版本已將可內嵌的圖片、字體和 CSS／JavaScript 依賴放在 ZIP 內；不需要額外下載資產，也不依賴 Manus 儲存服務、Google Fonts、外部 AI 或分析服務。
