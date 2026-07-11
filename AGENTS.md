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
- 目前所有零件皆為原廠配置（`stock`）。
- 尚未購買任何額外零件。
- 同一個 Ratchet 或 Bit 不可同時出現在兩個 `actual` 實際配裝。
- 配裝或戰術建議必須標示 `actual` 或 `theoretical`。
- `actual` 代表目前真的組得出來。
- `theoretical` 代表理論配置、待到貨、待確認版本或待確認零件。
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
