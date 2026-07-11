# 更新指南

## 新增收藏

1. 從 `templates/beyblade-entry.yaml` 複製格式。
2. 將新項目加入 `data/inventory.yaml`。
3. 將購買資訊加入 `data/purchases.yaml`。
4. 若已確認零件，更新 `data/parts.yaml`；否則維持 `unknown`。
5. 同步更新 `docs/collection.md` 與 README 統計。

## 訂購品到貨

1. 將 `data/inventory.yaml` 的 `status` 從 `ordered` 改為 `owned`。
2. 補上 `purchase_order` 或到貨後的收藏排序。
3. 更新 `data/purchases.yaml` 的 `received_date`，未知則維持 `unknown`。
4. 若為隨機款，補上 `confirmed_variant`；未確認則維持 `unknown`。
5. 若可納入實際配裝，更新 `data/loadouts.yaml`，並確保 Ratchet / Bit 沒有重複用於其他 `actual` 配裝。

## 新增配裝

1. 從 `templates/loadout-entry.yaml` 複製格式。
2. 判斷是 `actual` 還是 `theoretical`。
3. `actual` 必須只使用已持有且確認存在的零件。
4. 檢查 `actual` 配裝中 Ratchet / Bit 不重複。
5. 未確認零件不要推測，填 `unknown`。

## 新增實戰紀錄

1. 從 `templates/battle-test-entry.yaml` 複製格式。
2. 加入 `data/battle-tests.yaml` 的 `battle_tests`。
3. 實戰使用的配裝需對應 `data/loadouts.yaml`。
4. 若結果影響主力定位，更新 `docs/main-roster.md`。
