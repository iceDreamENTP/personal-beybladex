# 更新指南

## 新增收藏

1. 從 `templates/beyblade-entry.yaml` 複製格式。
2. 將新項目加入 `data/inventory.yaml`。
3. 將購買資訊加入 `data/purchases.yaml`。
4. 若已確認 `org` 的 Blade / Ratchet / Bit，更新 `data/parts.yaml`；未知資訊維持 `unknown`。
5. 同步更新 `docs/collection.md` 與 README 統計。
6. 若納入固定六機，更新 `docs/main-roster.md` 與 `data/loadouts.yaml`。

## 訂購品到貨

1. 將 `data/inventory.yaml` 的 `status` 從 `ordered` 改為 `owned`。
2. 補上 `purchase_order` 或到貨後的收藏排序。
3. 更新 `data/purchases.yaml` 的 `received_date`，未知則維持 `unknown`。
4. 若為隨機款，補上 `confirmed_variant`；未確認則維持 `unknown`。
5. 到貨後才能將該商品的 Ratchet / Bit 視為可用於 `tmp` 或未來 `dck`。
6. 若可納入固定六機，更新 `data/loadouts.yaml`，並確保 `dck` 中 Ratchet / Bit 不重複。

## 更新四層配置

1. `org` 只記錄原廠配置與官方設計策略。
2. `opt` 只依 Blade 物理結構、重量分布、接觸點、重心、衝量、反作用力、運動軌跡與特殊機構分析。
3. `dck` 用於固定六機永久配置；尚未定案時保留空白。
4. `tmp` 僅能使用目前已實際擁有且確認存在的零件。
5. 單顆 `opt` 不等於最終 `dck`。
6. 不要用玩家 META 直接覆蓋 `opt`。

## 新增實戰紀錄

1. 從 `templates/battle-test-entry.yaml` 複製格式。
2. 加入 `data/battle-tests.yaml` 的 `battle_tests`。
3. 實戰使用的配裝需標示 `org`、`opt`、`dck` 或 `tmp`。
4. 若結果影響固定六機定位、`opt` 或 `tmp`，同步更新 `docs/main-roster.md`、`data/inventory.yaml` 與 `data/loadouts.yaml`。
5. 實測可以修正 `opt`，但需保留修改理由與實測紀錄。

## 資料可信度與來源規則

- 原廠型號、名稱、`org` 配置及官方策略，以 Takara Tomy 官方產品頁為主要來源。
- BX-35-05 子款 Phoenix Wing 5-80H 可使用可靠零售資料補充確認。
- 隨機包尚未確認實際抽中款式時，只能記錄主打款資訊，不得寫入實際 Inventory。
- 玩家 META、論壇配裝與比賽使用率，不得直接覆蓋 `opt`。
- 日後如需記錄 META，應另設獨立欄位或文件，例如 `meta`，不要與 `opt` 混用。
- 實測結果可以用來修正 `opt`，但需保留修改理由與實測紀錄。
