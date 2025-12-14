# PWA 圖標說明

為了完整支援 PWA 功能，請在此目錄放置以下圖標文件：

- `icon-192x192.png` - 192x192 像素
- `icon-512x512.png` - 512x512 像素

## 快速生成圖標

### 方法 1: 使用在線工具

1. 訪問 [PWA Asset Generator](https://github.com/elegantapp/pwa-asset-generator)
2. 上傳您的圖標（建議至少 512x512 像素）
3. 下載生成的圖標並放置在此目錄

### 方法 2: 使用命令行工具

```bash
npx pwa-asset-generator your-icon.png public/icons
```

### 方法 3: 手動創建

使用任何圖像編輯軟件創建：
- 192x192 像素的 PNG 圖標
- 512x512 像素的 PNG 圖標

## 臨時解決方案

如果暫時沒有圖標，應用仍可正常運行，但 PWA 安裝功能可能不完整。您可以使用任何簡單的圖標作為占位符。

