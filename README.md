# 明基材料新人報到資訊網站

這是一個可直接部署至 GitHub Pages 的靜態網站，目的為協助新進人員完成報到前準備。

## 網站功能

- 報到前四項任務儀表板
- 桃園總部、龍科廠、雲科廠資訊並列呈現
- 導覽列滾動高亮（scrollspy），標示目前閱讀區塊
- 報到文件互動點檢表
- 體檢注意事項與參考醫院
- 各廠區交通、停車與報到流程
- 常見問題與個資邊界說明

網站不設後端、不接收檔案，也不儲存新人個人資料。點檢進度與廠區選擇只保存在使用者自己的瀏覽器。

## 本機預覽

在本目錄執行：

```bash
python3 -m http.server 8080
```

開啟 `http://localhost:8080/`。

## GitHub Pages 部署

1. 在公司 GitHub Organization 建立 repository。
2. 將本目錄內容推送至 `main` branch。
3. Repository Settings → Pages → Source 選擇 **GitHub Actions**。
4. 等待 `Deploy onboarding site to GitHub Pages` workflow 完成。
5. 設定公司正式子網域，完成網域驗證並強制啟用 HTTPS。

## 上線前必要確認

- HR 確認基本資料表單、文件清單、銀行優惠與報到時程。
- 職護／環安衛確認體檢條件、醫院資格與注意事項。
- 各廠區窗口確認地址、集合地點、停車方式。
- 品牌或公關確認 Logo、公司名稱與品牌色使用方式。
- IT／法遵確認公開內容與外部表單的個資告知事項。

詳細維運責任請見 `CONTENT-GOVERNANCE.md`。
