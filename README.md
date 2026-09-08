# Baby Learns English｜寶貝學英文

「Baby Learns English」是一個兒童英語啟蒙 App 的響應式下載頁面。網站以可愛、明亮的視覺呈現 App 特色，並提供 App Store 與 Google Play 的下載入口。

## 專案特色

- 支援桌面、平板與手機的響應式版面
- 提供 App Store 與 Google Play 下載連結
- 支援繁體中文、日文、印尼文、英文、泰文、越南文與韓文
- 依瀏覽器設定自動選擇語言
- 使用 `localStorage` 記住使用者選擇的語言
- 動態更新頁面標題、描述與 Open Graph 描述
- 使用語意化 HTML、ARIA 標籤及鍵盤焦點樣式改善無障礙體驗
- 支援 `prefers-reduced-motion`，減少不必要的動畫效果

## 技術

本專案不需要框架、套件管理器或建置工具，可直接由瀏覽器執行。

- HTML5
- CSS3
- Vanilla JavaScript
- Google Fonts：Nunito、Noto Sans TC

## 專案結構

```text
.
├── index.html          # 頁面結構、SEO 資訊與下載連結
├── styles.css          # 視覺樣式與響應式版面
├── translations.js    # 多語系內容、語言偵測與偏好儲存
└── res/
    └── 1024_ 500.png  # Hero 主視覺與 Open Graph 圖片
```

## 本機執行

你可以直接開啟 `index.html`，或使用本機靜態伺服器：

```bash
python3 -m http.server 8000
```

接著在瀏覽器前往：

```text
http://localhost:8000
```

## 多語系

所有翻譯內容都集中在 `translations.js` 的 `translations` 物件中。HTML 元素透過以下屬性對應翻譯鍵值：

- `data-i18n`：以純文字更新內容
- `data-i18n-html`：更新包含標記的內容，例如 Hero 標題中的換行與強調文字

若要新增語言：

1. 在 `translations.js` 的 `translations` 物件加入新的語言代碼與完整翻譯。
2. 在 `index.html` 的 `#language-select` 加入對應的 `<option>`。
3. 確認每個翻譯物件都包含相同鍵值。

目前支援的語言如下：

| 語言 | 代碼 |
| --- | --- |
| 繁體中文 | `zh-Hant` |
| 日本語 | `ja` |
| Bahasa Indonesia | `id` |
| English | `en` |
| ไทย | `th` |
| Tiếng Việt | `vi` |
| 한국어 | `ko` |

## App 下載

- [App Store](https://apps.apple.com/id6786215177)
- [Google Play](https://play.google.com/store/apps/details?id=com.himydream.bunnycatch)

## 部署

本專案是純靜態網站，可部署至 GitHub Pages、Cloudflare Pages、Netlify、Vercel，或任何可提供靜態檔案的網頁伺服器。部署時請保留目前的相對路徑結構，確保 CSS、JavaScript 與圖片可以正常載入。

## 維護提醒

- 修改圖片檔名或位置時，需同步更新 `index.html` 內的 Hero 圖片與 `og:image` 路徑。
- `data-i18n-html` 的翻譯內容會透過 `innerHTML` 寫入；只應放入專案內可信任的固定翻譯文字。
- 頁面字型由 Google Fonts 載入，離線環境會改用系統無襯線字型。

## 相關連結

- [HiMtDream 工作室](https://himydream.me/)

