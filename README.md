# AI 教學工作坊 — 教師培訓教材網站

支援 2026-08-26 14:00–16:00 嘅教師培訓，教老師用 AI 教學。靜態網站，host 喺 GitHub Pages。

## 內容
| 單元 | 檔案 |
|------|------|
| 主網站 | `index.html` |
| 數學速算遊戲 | `games/math-speed.html` |
| 中文認字遊戲 | `games/chinese-characters.html` |
| 英文 vocab 遊戲 | `games/english-vocab.html` |
| 遊戲製作 Prompt Pack（PDF） | `docs/ai-game-prompt-pack.pdf` |
| 教案範本（Word） | `docs/lesson-plan-template.docx` |
| 工作紙範本（Word） | `docs/worksheet-template.docx` |
| Apps Script 後端（貼入 Google Sheet） | `docs/AppsScript.gs` |

`docs/*.txt` 係各 Word/PDF 檔嘅純文字來源，改咗之後要重新用 Word 轉返做 `.docx` / `.pdf`。

## 部署到 GitHub Pages
1. 開 GitHub repo，名稱例如 `ai-teaching-workshop`
2. 將成個資料夾（index.html、games/、docs/、assets/）推上去
3. Settings → Pages → Source 揀 `main` branch / root
4. 幾分鐘後有條 `https://<username>.github.io/<repo>/` 網址

## 成績／名單／遊戲設定（Google Sheet + Apps Script）

遊戲（尤其數學速算）會連 Google Sheet：
- 開局前讀「名單」分頁，學生揀班別＋學號
- 讀「數學設定」分頁攞難度／限時（老師喺 sheet 改題目，唔使改 code）
- 玩完寫得分入「成績」分頁
- 網站「成績排名」單元投影全班最高得分排名

### 設定步驟（15 分鐘，只需你做一次）
1. 開一個新 Google Sheet，開呢幾個分頁：**名單、數學設定、中文題目、英文題目、成績**
2. **名單**：A=班別　B=學號（可寫 `1-40` 或 `1,5,12`）
3. **數學設定**：A=項目　B=值（`算式下限`/`算式上限`/`運算`(加/減/加減)/`限時`(秒)）
4. **中文題目**：A=字　B=讀音　C~E=干擾選項（最少 4 行）
5. **英文題目**：A=英文　B=中文（最少 4 行）
6. 選單「擴充功能」→「Apps Script」→ 刪走預設，貼入 `docs/AppsScript.gs`
7. 「部署」→「新增部署」→ 類型「網頁應用程式」→ 執行身分「我自己」→ 存取「任何人」
8. 部署完複製個網址（結尾 `/exec`），貼入網站「成績排名」單元／第一次開 game 時
9. 網址由瀏覽器記住（localStorage），每部機只需貼一次

注意：Apps Script 部署權限約每 30 日要檢查一次；重新部署會換網址，要再貼一次。

## 有待完成（培訓前補上）
- [ ] 示範影片 YouTube embed（#videos 單元）
- [ ] 教案／工作紙範本實際內容
- [ ] 培訓最終名稱（標題暫用「AI 教學工作坊」）
- [ ] 確認實際使用嘅 AI 工具名（ChatGPT／Copilot／Gemini…）
