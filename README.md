# 蕎安的小小手帳

繁體中文的一頁式個人網站，使用 React + Vite，部署至 GitHub Pages。

## 本機啟動

需要 Node.js 22.12+（或 24）。在本資料夾開啟終端機：

```sh
npm install
npm run dev
```

開啟終端機顯示的網址（預設 http://127.0.0.1:5173/self_introduction/）。

```sh
npm run build
npm run preview
```

`dist/` 是正式部署產物。

## 修改內容

- `src/content.js`：自介、學歷、學習、經歷、相簿註解、聯絡方式。
- `src/main.jsx`：頁面結構、區塊標題與導覽。
- `src/style.css`：配色、排版、響應式樣式與焦點。
- `public/assets/`：只有網站實際使用的圖片；WebP 照片已縮圖並移除 EXIF。

原始 PDF、原始照片資料夾與未使用圖片皆由 `.gitignore` 排除，不會提交；Vite 僅複製 `public/` 中的靜態素材。請勿將私人檔案放入 `public/`。網站不包含電話或 PDF 下載。

## GitHub Pages

目標：https://joanna3503.github.io/self_introduction/

儲存庫 Settings → Pages → Source 設為 **GitHub Actions**。推送到 `main` 會執行 `.github/workflows/deploy.yml`，安裝鎖定套件、建置並部署 `dist/`。

本機預設 base 為 `/self_introduction/`；Actions 從 `configure-pages` 取得實際 `base_path`，透過 `VITE_BASE_PATH` 設定 Vite。圖片路徑使用 `import.meta.env.BASE_URL`，可正常在子路徑載入。

字型使用 Google Fonts 的 Noto Sans TC；離線時使用系統無襯線字型。版面尊重減少動態效果設定。
