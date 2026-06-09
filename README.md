# shop-search — 店家地圖

匯入現有客戶名單（Excel / CSV）後，把每家店的地址轉成座標，標記在地圖上。

## 功能
- 📂 匯入 `.xlsx` / `.xls` / `.csv` 名單
- 🗺️ 將店家地址轉成座標並在地圖上標記（標記過多時自動叢集）
- 🔍 關鍵字搜尋，同步篩選清單與地圖標記
- 📍 點清單卡片可在地圖上定位；點標記可看店家資訊、撥號、開 Google 地圖導航
- 💾 名單與地址座標皆存在瀏覽器（localStorage），重開可續用

## 名單格式
第一列為欄位名稱，需包含「地址」欄。系統會自動辨識下列欄位：

| 用途 | 可接受的欄位名稱（擇一） |
| --- | --- |
| 店名 | 顧客名、店名、名稱、客戶、公司、name |
| 電話 | 電話、手機、phone、tel、mobile |
| 地址 | 地址、住址、address |
| 經緯度（選填） | 經度 / 緯度、lng / lat |

> 若名單已含「經度／緯度」欄，會直接使用該座標（最準確），不再做地址轉換。

## 技術
- 純前端單一 `index.html`，可直接放 GitHub Pages，免後端、免 API 金鑰
- 地圖：[Leaflet](https://leafletjs.com/) + OpenStreetMap 圖磚
- 地理編碼：[Nominatim](https://nominatim.org/)（免費、每秒最多 1 次，結果會快取）
- Excel 解析：[SheetJS](https://sheetjs.com/)

> 註：Nominatim 對台灣巷弄號的解析準確度有限；若需要最高準確度，建議在名單加上「經度／緯度」欄。
