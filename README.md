# 訊號教室｜GitHub Pages 單一 HTML 發布

本專案已額外產生 **單一、自包含的 `index.html`**。JavaScript、CSS、網站使用的圖片與字體均已內嵌，不需要上傳 `assets/` 目錄，也不會載入外部 AI、圖片、字體或分析服務。

發布檔位於：`release-single/index.html`。檔案約 **43 MB**，低於 GitHub 一般單檔提交上限；請保留檔名為 `index.html`。

## 上傳到 GitHub Pages

請在你的 GitHub 儲存庫根目錄放入此一個檔案，結構如下：

```text
你的儲存庫/
└── index.html
```

提交並推送後，到 GitHub 儲存庫的 **Settings → Pages**，將 Source 設為 **Deploy from a branch**，選擇你的發布分支（通常是 `main`）及資料夾 **`/ (root)`**。儲存後，GitHub Pages 會發布該檔案。

> 這是純前端、離線優先網站。課堂進度、人物工坊和設定只保存在每個瀏覽器、每個網域自己的 localStorage；由 Manus 網域轉到 GitHub Pages 時，不會自動搬遷原有戰役。請先在舊網站的「戰役資料」下載 JSON，再在 GitHub Pages 版本匯入。

## 網址與路由

GitHub Pages 不會替單一 HTML 處理 React 的伺服器路由，因此發布檔已改用 **hash 路由**。根頁可用 `https://你的帳號.github.io/你的倉庫/#/` 開啟，以下連結可直接分享或加入書籤。

| 頁面 | hash 路徑 |
|---|---|
| 視訊大廳 | `#/` 或 `#/lobby` |
| 授課紀錄檔案 | `#/records` |
| 學生聯絡簿 | `#/students` |
| 學生 Profile | `#/profile` |
| 使用指南 | `#/guide` |
| 指南學生管理章節 | `#guide-students` |
| 戰役資料 | `#/settings` |
| 範例回覆試跑 | `#/trial` |

已驗證從 Profile 返回學生聯絡簿、學生聯絡簿開啟人物工坊、指南深層錨點，以及本機 JSON 匯出。

## 日後重新產生

如日後修改原始 React 專案，在專案根目錄執行：

```bash
pnpm build:single
```

新檔會重新寫入 `release-single/index.html`。單檔發布配置與正常 `pnpm build` 分開；它不改變現有網站的 pathname 路由與部署輸出。

## 直接開啟檔案

已在 Chromium 以 `file://` 測試直接開啟及 `#/students`、`#/guide` 等 hash 路徑。實際發布仍建議使用 GitHub Pages，因為部分瀏覽器可能對 `file://` 的 localStorage 或下載策略設有限制。
