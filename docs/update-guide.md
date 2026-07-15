# 更新指南

## 新增收藏

1. 從 `templates/beyblade-entry.yaml` 複製格式。
2. 將新項目加入 `data/inventory.yaml`。
3. 將購買資訊加入 `data/purchases.yaml`。
4. 若已確認 `org` 的 Blade / Ratchet / Bit，更新 `data/parts.yaml`；未知資訊維持 `unknown`。
5. 同步更新 `docs/collection.md` 與 README 統計。
6. 若納入核心三機，更新 `docs/main-roster.md` 與 `data/loadouts.yaml`。

## 訂購品到貨

1. 將 `data/inventory.yaml` 的 `status` 從 `ordered` 改為 `owned`。
2. 補上 `purchase_order` 或到貨後的收藏排序。
3. 更新 `data/purchases.yaml` 的 `received_date`，未知則維持 `unknown`。
4. 若為隨機款，補上 `confirmed_variant`；未確認則維持 `unknown`。
5. 到貨後才能將該商品的 Ratchet / Bit 視為可用於 `tmp` 或未來 `dck`。
6. 若可納入核心三機，更新 `data/loadouts.yaml`，並確保實際組裝不重複使用同一個零件實體。

## 更新四層配置

1. `org` 只記錄原廠配置與官方設計策略。
2. `opt` 只依 Blade 物理結構、重量分布、接觸點、重心、衝量、反作用力、運動軌跡與特殊機構分析。
3. `dck` 用於核心三機目標永久配置；尚未定案時保留空白。
4. `tmp` 僅能使用目前已實際擁有且確認存在的零件。
5. 單顆 `opt` 不等於最終 `dck`。
6. 不要用玩家 META 直接覆蓋 `opt`。

## 更新 Main Blade 研究計畫

1. 研究計畫只包含藍鳳凰、女武神與狐狸。
2. `data/research-plan.yaml` 保存完整版本；`docs/research-plan.md` 顯示目前版本與版本摘要。
3. 單純新增案例、修正錯字或補來源不升版。
4. 角色目標、候選配置、假說、規則、判定門檻、候選排序、信心或階段結論改變時，複製目前完整版本建立下一版。
5. 新版記錄 `supersedes`、`change_reason` 與 `based_on_case_ids`；舊版改為 `superseded`，不得刪除。
6. 研究候選與理想配置必須標示可用性；不得把 ordered、conditional 或 unrestricted 寫成 owned。
7. 研究計畫不會自動覆蓋 `inventory`、`opt` 或 `dck`。若使用者正式改變核心配置，才同步更新既有四層資料。

## 新增實測案例

1. 使用者可以直接憑印象口述；不要求為了格式補出不存在的數字。
2. 從 `templates/battle-test-entry.yaml` 複製格式，加入 `data/battle-tests.yaml` 的 `test_cases`。
3. 已知配裝需標示 `org`、`opt`、`dck` 或 `tmp`；未知日期、場數、場地、對手零件與結果填 `unknown`。
4. 保留 `user_report_summary`，再另外整理結構化 `observations` 與 `conclusion`。
5. 「明顯、常常、感覺」維持質性描述，不換算成勝率或場數。
6. 同步更新 `docs/test-cases.md` 的案例索引與人讀摘要。
7. 案例以追加為原則；後續更正建立新案例並使用 `amends_case_id` 連回原案例。
8. 新增案例本身不讓研究計畫升版；案例被研究計畫吸收並改變研究方向、候選排序、信心或階段結論時，才依上一節建立新版。
9. 若結果正式影響核心三機、`opt` 或 `tmp`，再同步更新 `docs/main-roster.md`、`data/inventory.yaml` 與 `data/loadouts.yaml`，並保留案例作為理由。

## 資料可信度與來源規則

- 原廠型號、名稱、`org` 配置及官方策略，以 Takara Tomy 官方產品頁為主要來源。
- BX-35-05 子款 Phoenix Wing 5-80H 可使用可靠零售資料補充確認。
- 隨機包尚未確認實際抽中款式時，只能記錄主打款資訊，不得寫入實際 Inventory。
- 玩家 META、論壇配裝與比賽使用率，不得直接覆蓋 `opt`。
- 日後如需記錄 META，應另設獨立欄位或文件，例如 `meta`，不要與 `opt` 混用。
- 實測結果可以用來修正 `opt`，但需保留修改理由與實測紀錄。
