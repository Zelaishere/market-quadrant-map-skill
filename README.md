# market-quadrant-map

一個 Claude（Cowork / Claude Code）skill：使用者要做特定產品類別的市場調查／競品分析，
想把多個品牌的產品依「價格 x 風格」畫成象限圖（可點擊連到Amazon或官網銷售頁）時使用；
特別適合產品/工業設計師初接觸一個新領域、想快速掃描市場找設計方向，或需要快速產出一張市場定位圖表的場合。
觸發詞：市場調查、競品分析、象限圖、品牌比較圖、產品定位圖、market map、quadrant chart。

## 這個 repo 放什麼

- [`SKILL.md`](./SKILL.md) — skill 本體。把整個資料夾（或至少 `SKILL.md`）放進你的 Claude skills 目錄即可使用。
- [`reference/quadrant-map-template.html`](./reference/quadrant-map-template.html) — 一份實際跑過完整流程的成品（PSU／電源供應器市場定位圖），標了 `EDIT-PER-CATEGORY` 註解，做新類別時可以直接照著改。
- [`reference/example-products.json`](./reference/example-products.json) — 上面那份成品對應的真實資料範例（18 品牌、28 款產品），示範資料欄位格式。

## 快速開始

在 Claude 裡對話：「幫我做〔某個產品類別〕的市場調查象限圖」，Claude 會：

1. 用 AskUserQuestion 確認要查幾個品牌、每個品牌放幾款代表產品
2. 提出一組「風格」光譜建議（例如：極簡 vs 復古），供確認或調整
3. 實際用網頁搜尋／瀏覽工具查詢 Amazon 與品牌官網，蒐集真實售價、產品描述、銷售連結
4. 畫出象限圖並發布成互動網頁（Y 軸＝售價、X 軸＝風格、背景依入門/中階/高階分層），
   每個色塊可點擊連到真實銷售頁
5. 視需求加上匯出按鈕：資料表 Markdown、象限圖 PNG、Figma Make 重現規格 Markdown

## 已知限制

目前 Claude 的雲端執行環境通常無法把 Amazon／品牌官網的商品照片安全下載並內嵌進發布的網頁
（外部圖片主機被安全限制擋下，且工具本身也不支援回傳圖片二進位內容）。
因此預設會以「品牌名稱＋價格帶色點」的色塊取代真實商品照片，但銷售連結、售價、產品描述都是真實查證過的資料。
細節見 `SKILL.md` 的「圖片處理」一節。

## 授權

MIT — 隨意使用、修改、分享。
