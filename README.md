# 明基材料新人報到資訊網站

協助新進人員完成報到前準備的靜態網站，取代原 Strikingly 頁面。

**正式網址**

- 中文版：https://harry985991.github.io/bmc-onboarding/
- 英文版：https://harry985991.github.io/bmc-onboarding/en/

## 網站功能

- 報到前四項任務儀表板
- 桃園總部、龍科廠、雲科廠資訊並列呈現
- 導覽列滾動高亮（scrollspy），標示目前閱讀區塊
- 中／英文雙語版本（`en/index.html`），導覽列 EN／中文鈕互切；英文版點檢表為外籍同仁版（護照＋工作許可＋居留證，免身分證）。**修改中文內容時必須同步修改英文版**
- 報到文件互動點檢表
- 體檢注意事項與參考醫院
- 各廠區交通、停車與報到流程
- 常見問題與個資邊界說明

網站不設後端、不接收檔案，也不儲存新人個人資料。點檢進度只保存在使用者自己的瀏覽器。

## 檔案結構

| 檔案 | 用途 |
|---|---|
| `index.html` | 中文版全站內容（單一檔案，含 CSS 與 JS） |
| `en/index.html` | 英文版全站內容 |
| `404.html` | 找不到頁面時的導引頁 |
| `robots.txt` | 阻擋搜尋引擎索引 |
| `.github/workflows/deploy-pages.yml` | push 後自動部署 GitHub Pages |
| `CONTENT-GOVERNANCE.md` | 內容責任分工與維護規範 |

## 內容維護

1. 直接編輯 `index.html`（中文）或 `en/index.html`（英文）中對應區塊的文字，各區塊有 `<!-- ===== 區塊名 ===== -->` 註解標記
2. **改中文必須同步改英文**，反之亦然
3. commit 並 push 至 `main`，GitHub Actions 約 1 分鐘內自動完成部署

### 主要區塊錨點

| 區塊 | 錨點 |
|---|---|
| 報到前準備事項 | `#prepare` |
| 攜帶資料點檢表 | `#checklist` |
| 自費勞工體檢資訊 | `#health` |
| 報到當日流程 | `#dayflow` |
| 停車／交通資訊 | `#traffic` |
| 常見問題 | `#faq` |

## 本機預覽

在本目錄執行：

```bash
python3 -m http.server 8080
```

開啟 `http://localhost:8080/`。

## 部署設定（已完成，供日後參考）

- Repository Settings → Pages → Source 設為 **GitHub Actions**
- push 至 `main` 即觸發 `Deploy onboarding site to GitHub Pages` workflow
- 如日後改用公司正式子網域：於 Settings → Pages 設定 custom domain、完成網域驗證並強制啟用 HTTPS

## 內容紅線（public repository）

本 repository 為公開，內容任何人皆可瀏覽：

- 不得放入個資、機密資訊或門禁細節
- 敏感或個別化資訊（報到時間異動、個人文件）一律以錄取通知信為準，網站只放通用資訊
- 已設 `noindex` 與 `robots.txt`，不會被搜尋引擎索引

詳細維運責任與更新流程請見 `CONTENT-GOVERNANCE.md`。

## 上線前必要確認

- HR 確認基本資料表單、文件清單、銀行優惠與報到時程
- 職護／環安衛確認體檢條件、醫院資格與注意事項
- 各廠區窗口確認地址、集合地點、停車方式
- 品牌或公關確認公司名稱與品牌色使用方式
- IT／法遵確認公開內容與外部表單的個資告知事項
