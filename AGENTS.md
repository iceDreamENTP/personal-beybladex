# AGENTS.md

本 repo 是 Beyblade X 收藏與配裝資料庫。任何 AI 在分析、建議配裝、更新資料或回覆使用者前，必須先閱讀：

1. `data/inventory.yaml`
2. `data/parts.yaml`
3. `data/loadouts.yaml`
4. `docs/main-roster.md`

## 基本規則

- 不可假設使用者擁有不存在的零件。
- 不可自行猜測未知資訊；未確認資料一律填 `unknown`。
- 必須清楚區分 `owned`、`ordered`、`wishlist`。
- 已訂購但尚未收到的商品不得假設是哪個版本。
- 鯨魚與狐狸是路上的隨機包，目前實際款式尚未確認；主打款資訊不得視為實際取得零件。
- 尚未購買任何額外零件。
- 所有配裝資料統一使用 `org`、`opt`、`dck`、`tmp`。
- 不要同時保留任何與四層模型重複的冗長替代欄位名稱。
- `org` 代表 Takara Tomy 原廠配置與官方設計策略，固定不隨 Inventory 或 Deck 改變。
- `opt` 代表純粹依 Blade 物理結構推導的單顆理論最佳配置，不依網路 META 擅自覆蓋。
- `dck` 代表固定六機賽制下，零件不重複的永久配置。
- `tmp` 代表依目前已實際擁有的零件可組出的暫時配置。
- 固定六機 `dck` 之間 Ratchet 不重複、Bit 不重複。
- 女武神沒有獨立 Ratchet，因此不占用一般 Ratchet 名額。
- `dck` 尚未定案前，`dck鎖`、`dck軸`、`dck策略` 保持空白。
- `tmp` 僅能使用目前已實際擁有且已確認存在的零件。
- 實測結果可以修正 `opt`，但需保留修改理由與實測紀錄。
- 如果零件名稱、版本、購入日期、店家或實戰結果未確認，維持 `unknown`。

## 公開 repo 安全規則

- 不得新增個資、Token、Secret、帳號憑證、私人聯絡資訊或付款資訊。
- 不得在 commit message、文件或 YAML 中貼上密碼、Cookie、API key。
- 所有文字檔維持 UTF-8。
- 說明文件維持繁體中文。

## 更新資料時

- 先改 `data/`，再同步改 `docs/` 與 README 統計。
- 若新增實戰紀錄，優先使用 `templates/battle-test-entry.yaml`。
- 若新增陀螺，優先使用 `templates/beyblade-entry.yaml`。
- 若新增配裝，優先使用 `templates/loadout-entry.yaml`。
- 若有不確定資訊，保留 `unknown`，不要用推測補齊。

## 資料可信度與來源規則

- 原廠型號、名稱、`org` 配置及官方策略，以 Takara Tomy 官方產品頁為主要來源。
- BX-35-05 子款 Phoenix Wing 5-80H 可使用可靠零售資料補充確認。
- 隨機包尚未確認實際抽中款式時，只能記錄主打款資訊，不得寫入實際 Inventory。
- 玩家 META、論壇配裝與比賽使用率，不得直接覆蓋 `opt`。
- 日後如需記錄 META，應另設獨立欄位或文件，例如 `meta`，不要與 `opt` 混用。
