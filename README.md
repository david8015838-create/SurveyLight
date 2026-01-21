# SurveyLight

此專案為 **單一 HTML 檔案（Single-File SPA）** 的問卷平台，可直接部署到 **GitHub Pages**，不需要 Webpack / Vite 等 Build Process。

## 部署重點（解決 GitHub Pages 打開空白）

- GitHub Pages 預設入口為 **`index.html`**  
  本專案已提供：`/index.html`（主要入口），並保留舊檔 `SurveyLight.html`。

## 路由設計

- **管理端（需要登入）**：使用 Hash 路由，例如 `#/dashboard`、`#/create`、`#/analytics/{surveyId}`，確保部署在 `.../SurveyLight/` 子路徑也不會 404。
- **填寫端（免登入）**：使用 URL 參數 `?s={surveyId}`，例如：`https://david8015838-create.github.io/SurveyLight/?s=xxxxxxxx`

## Firebase 登入常見錯誤（一定要做）

若登入出現 **Unauthorized Domain**：
- 請到 Firebase Console → Authentication → Settings → Authorized domains
- 新增你的網域（至少）：
  - `david8015838-create.github.io`
  - （本機測試）`localhost`
