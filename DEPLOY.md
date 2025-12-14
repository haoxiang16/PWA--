# GitHub Pages 部署指南

## 快速部署步驟

### 1. 啟用 GitHub Pages

1. 前往您的 GitHub 倉庫：`https://github.com/haoxiang16/PWA--`
2. 點擊 **Settings**（設置）標籤
3. 左側選單選擇 **Pages**
4. 在 **Source** 下拉選單中選擇 **GitHub Actions**
5. 保存設置

### 2. 觸發部署

#### 方法 A：推送代碼（推薦）
```bash
git add .
git commit -m "Add deployment workflow"
git push origin main
```

#### 方法 B：手動觸發
1. 點擊倉庫頂部的 **Actions** 標籤
2. 選擇左側的 **Deploy to GitHub Pages** 工作流程
3. 點擊右側的 **Run workflow** 按鈕
4. 選擇分支（main）
5. 點擊 **Run workflow**

### 3. 查看部署狀態

1. 前往 **Actions** 標籤
2. 點擊最新的工作流程運行
3. 等待所有步驟完成（顯示綠色勾號）

### 4. 訪問網站

部署完成後，您的網站地址是：

**https://haoxiang16.github.io/PWA--/**

## 常見問題

### Q: 部署失敗怎麼辦？
A: 
- 檢查 **Actions** 標籤中的錯誤訊息
- 確認 `package.json` 中的依賴正確
- 確認 Node.js 版本兼容（工作流程使用 Node 20）

### Q: 網站顯示 404？
A: 
- 確認 GitHub Pages 已啟用（Settings → Pages）
- 確認 Source 選擇的是 **GitHub Actions**
- 等待幾分鐘讓 DNS 更新
- 清除瀏覽器緩存後重試

### Q: 如何更新網站？
A: 
- 推送新的代碼到 main 分支
- GitHub Actions 會自動重新部署
- 無需手動操作

### Q: 如何查看部署日誌？
A: 
- 前往 **Actions** 標籤
- 點擊最新的工作流程
- 查看每個步驟的詳細日誌

## 網站地址

**生產環境：** https://haoxiang16.github.io/PWA--/

**本地開發：** http://localhost:5173

