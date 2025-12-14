# GitHub Pages 設置步驟（圖文說明）

## 重要：必須進入「倉庫」的 Settings，不是「個人帳號」的 Settings

### 正確的導航路徑：

1. **前往您的倉庫首頁**
   - 訪問：`https://github.com/haoxiang16/PWA--`
   - 或點擊 GitHub 左上角的 Octocat 圖標，然後選擇您的倉庫

2. **進入倉庫的 Settings**
   - 在倉庫頁面頂部，點擊 **`Settings`** 標籤
   - ⚠️ 注意：這是在倉庫頁面的 Settings，不是個人帳號的 Settings

3. **找到 Pages 設置**
   - 在左側選單中，向下滾動找到 **`Pages`** 選項
   - 點擊 **`Pages`**

4. **選擇 Source**
   - 在 **`Source`** 部分，您會看到一個下拉選單
   - 選擇 **`GitHub Actions`**（不是 "Deploy from a branch"）
   - 保存設置

## 如果看不到 Pages 選項？

### 可能的原因：
1. **您進入了個人帳號的 Settings**
   - 解決：回到倉庫首頁，點擊倉庫的 Settings 標籤

2. **倉庫是 Private 且沒有 GitHub Pro**
   - 解決：將倉庫改為 Public（Settings → Danger Zone → Change visibility）
   - 或升級到 GitHub Pro

3. **權限不足**
   - 解決：確認您是倉庫的擁有者或有管理權限

## 快速檢查清單

- [ ] 在倉庫頁面（不是個人帳號頁面）
- [ ] 點擊倉庫頂部的 **Settings** 標籤
- [ ] 左側選單找到 **Pages**
- [ ] 在 Source 選擇 **GitHub Actions**
- [ ] 保存設置

## 正確的 URL 格式

**倉庫 Settings：**
```
https://github.com/haoxiang16/PWA--/settings/pages
```

**個人帳號 Settings（錯誤）：**
```
https://github.com/settings/pages  ← 這不是我們要的
```

