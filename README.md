# Vue 3 PWA 待辦事項應用

一個簡易的 Vue 3 Progressive Web App (PWA) 待辦事項網站，支援離線使用和安裝到主畫面。

## 功能特色

- ✅ 添加、刪除、完成待辦事項
- 📱 響應式設計，支援手機和桌面
- 🔄 離線支援（Service Worker）
- 💾 本地存儲（localStorage）
- 📲 可安裝到主畫面（PWA）
- 🎨 現代化 UI 設計

## 技術棧

- **Vue 3** - 使用 Composition API
- **Vite** - 快速的前端構建工具
- **vite-plugin-pwa** - PWA 支援插件
- **Service Worker** - 離線功能和緩存策略

## 安裝與使用

### 1. 安裝依賴

```bash
npm install
```

### 2. 開發模式

```bash
npm run dev
```

應用將在 `http://localhost:5173` 啟動

### 3. 構建生產版本

```bash
npm run build
```

構建後的檔案會在 `dist` 目錄中

### 4. 預覽生產版本

```bash
npm run preview
```

## PWA 圖標設置

為了完整支援 PWA 功能，您需要準備以下圖標文件：

- `public/icons/icon-192x192.png` (192x192 像素)
- `public/icons/icon-512x512.png` (512x512 像素)

您可以使用以下工具生成圖標：
- [PWA Asset Generator](https://github.com/elegantapp/pwa-asset-generator)
- [RealFaviconGenerator](https://realfavicongenerator.net/)

或者使用在線工具生成後，將圖標放置在 `public/icons/` 目錄下。

## 使用說明

1. **添加待辦事項**：在輸入框中輸入內容，按 Enter 或點擊「新增」按鈕
2. **標記完成**：點擊待辦事項前的複選框或點擊文字
3. **刪除待辦事項**：點擊右側的「刪除」按鈕
4. **查看統計**：頂部顯示總數、已完成和未完成的數量

## PWA 功能

### 安裝到主畫面

- **Chrome/Edge**：點擊地址欄右側的安裝圖標
- **Safari (iOS)**：點擊分享按鈕，選擇「加入主畫面」
- **Firefox**：點擊地址欄右側的「+」圖標

### 離線使用

應用會自動緩存資源，即使沒有網路連線也能正常使用。

## 專案結構

```
PWA測試/
├── index.html              # 入口 HTML
├── package.json            # 專案配置
├── vite.config.js         # Vite 配置
├── manifest.json          # PWA Manifest
├── public/                # 靜態資源
│   ├── icons/            # PWA 圖標
│   └── vite.svg          # 網站圖標
└── src/
    ├── main.js           # Vue 應用入口
    ├── App.vue           # 根組件
    ├── components/
    │   └── TodoList.vue  # 待辦事項組件
    └── assets/
        └── style.css     # 全局樣式
```

## 瀏覽器支援

- Chrome/Edge (推薦)
- Firefox
- Safari (iOS 11.3+)
- 其他支援 Service Worker 的現代瀏覽器

## 授權

MIT License

