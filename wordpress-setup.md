# WordPress 落地頁安裝

## 三份檔案

- `wordpress-download-page.html`：新版落地頁內容，貼到頁面的「自訂 HTML」區塊。
- `wordpress-download-page.css`：獨立樣式，貼到「外觀 → 自訂 → 額外 CSS」，或使用自訂 CSS 外掛載入。
- `wordpress-download-page.js`：獨立 JavaScript，使用自訂 JS／頁首與頁尾程式碼外掛，在該頁頁尾載入。

CSS／JS 編輯欄若接受純程式碼，直接貼檔案內容，不加 `<style>`／`<script>` 標籤。HTML 檔沒有內嵌 CSS 或 JS。

圖片已使用 `https://qn5566.github.io/BabayLearnEnglish/res/`，不需要上傳到 WordPress 媒體庫。首頁截圖和角色圖片與 GitHub Pages 首頁一致。

## 直接載入 GitHub Pages 的 CSS／JS

將新檔案 push 並等 GitHub Pages 部署完成後，也可以使用以下方式，省去複製 CSS／JS。請只選一種載入方式，避免重複載入。

在該頁的 head 載入 CSS：

```html
<link rel="stylesheet" href="https://qn5566.github.io/BabayLearnEnglish/wordpress-download-page.css">
```

在該頁頁尾載入 JS：

```html
<script defer src="https://qn5566.github.io/BabayLearnEnglish/wordpress-download-page.js"></script>
```

可使用支援「指定頁面」的程式碼外掛設定以上標籤。更新後若仍看到舊版，清除 WordPress／CDN 快取，必要時在 CSS／JS 網址後加上版本參數（例如 `?v=2`）。

## 頁面版型

選擇主題的「全寬」或「Canvas／空白頁」範本，讓內容有足夠寬度。若主題會額外顯示頁面標題，使用主題設定隱藏該標題：落地頁本身已有一個 H1。CSS 已限定在 `.ble-wp-landing` 範圍內，JS 只更新落地頁內容，不會改動 WordPress 的文件語言或 SEO head。

## SEO

在 WordPress 的 SEO 外掛（如 Yoast／Rank Math）或主題 SEO 設定填入：

- SEO 標題：`寶貝學英文｜幼兒英語學習 App 下載`
- Meta description：`寶貝學英文｜適合幼兒的英文字母與發音學習 App。透過可愛角色、聲音與趣味互動，陪孩子從 A 到 Z 開心學英文，支援 iPhone、iPad 與 Android。`
- 社群分享圖片：`https://qn5566.github.io/BabayLearnEnglish/res/1024_%20500.png`
- Robots：允許索引與追蹤連結（index、follow）。
- Canonical／社群分享 URL：使用這個 WordPress 頁面的正式網址，通常保留 SEO 外掛的預設值即可。

HTML 已包含 `MobileApplication` microdata，以及免費 `Offer`、作業系統與安裝連結；不需要再重複加入同一份 App schema。發布後可用 Google Rich Results Test 確認 WordPress 實際輸出的結構化資料。

頁面即使不載入 JS，仍有完整中文內容、圖片及下載連結。JS 提供原有七種語言的核心文案切換與年份更新；新增特色、藝廊和 FAQ 保留中英雙語內容。SEO metadata 由 WordPress 輸出，不依賴 JS。
