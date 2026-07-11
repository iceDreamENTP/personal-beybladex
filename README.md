# personal-beybladex

這個 Repository 用來管理 Beyblade X 收藏、零件庫、配裝、購買紀錄與實戰測試紀錄。目標是讓 AI（ChatGPT / Codex）可以直接讀取此 repo，取得最新收藏資訊，避免每次重新整理。

本 repo 是公開資料庫，不應包含個資、Token、Secret、帳號憑證或私人聯絡資訊。所有文字檔使用 UTF-8，說明文件使用繁體中文。

## 收藏總覽

| 類別 | 數量 |
| --- | ---: |
| 已持有 | 5 顆 |
| 已訂購 | 5 顆 |
| 總數 | 10 顆 |

## 已持有

| 購入順序 | 名稱 | 狀態 | 花費 | 配置 | 備註 |
| ---: | --- | --- | ---: | --- | --- |
| 1 | 紅鳳凰 | owned | 1700 TWD | stock |  |
| 2 | 隕星龍 | owned | 300 TWD | stock | 左旋 |
| 3 | 騎士堡壘 | owned | 1000 TWD | stock |  |
| 4 | 藍鳳凰 | owned | 6000 TWD | stock | 主力候選；最喜歡的鳳凰 |
| 5 | 天蠍 | owned | 1600 TWD | stock | 主力候選 |

## 已訂購

| 訂購順序 | 名稱 | 狀態 | 花費 | 配置 | 隨機款 | 備註 |
| ---: | --- | --- | ---: | --- | --- | --- |
| 1 | 獨角獸 | ordered | 700 TWD | stock | 否 | 為了零件 |
| 2 | 鯨魚 | ordered | 1000 TWD | stock | 是，3 種可能 | 主力候選 |
| 3 | 狐狸 | ordered | 1100 TWD | stock | 是，3 種可能 | 主力候選 |
| 4 | 女武神 | ordered | 2100 TWD | stock | 否 | UX-20；主力候選 |
| 5 | 龍王 | ordered | 1300 TWD | stock | 否 | 為了零件 |

## 五顆主力

目前主力戰備庫固定為五顆，但不是固定三顆 Deck。每次比賽可依 Meta、對手與場地自由挑選三顆。

| 名稱 | 狀態 | 定位 | 特色 | 目前可用性 |
| --- | --- | --- | --- | --- |
| 藍鳳凰 | owned | 高速攻擊 | 擊飛、爆體、主動進攻 | actual |
| 狐狸 | ordered | 技巧型攻擊 | 連擊、爆體、干擾 | theoretical，待到貨確認 |
| 天蠍 | owned | 均衡 | 能攻、能守、配裝彈性最高 | actual |
| 鯨魚 | ordered | 重量攻擊 | 正面硬碰、擊飛、壓制 | theoretical，待到貨確認 |
| 女武神 | ordered | 爆發攻擊 | 特殊機構、高爆發、奇襲 | theoretical，待到貨確認 |

## 花費統計

| 類別 | 金額 |
| --- | ---: |
| 已持有 | 10600 TWD |
| 已訂購 | 6200 TWD |
| 累計 | 16800 TWD |

## Repository 架構

```text
personal-beybladex/
├── README.md
├── AGENTS.md
├── LICENSE
├── .gitignore
├── data/
│   ├── inventory.yaml
│   ├── parts.yaml
│   ├── loadouts.yaml
│   ├── purchases.yaml
│   └── battle-tests.yaml
├── docs/
│   ├── collection.md
│   ├── main-roster.md
│   ├── wishlist.md
│   ├── terminology.md
│   └── update-guide.md
└── templates/
    ├── beyblade-entry.yaml
    ├── loadout-entry.yaml
    └── battle-test-entry.yaml
```

## 如何新增一顆陀螺

1. 複製 `templates/beyblade-entry.yaml` 的格式。
2. 新增到 `data/inventory.yaml` 的 `items`。
3. 同步更新 `data/purchases.yaml`。
4. 若已確認 Blade / Ratchet / Bit，才更新 `data/parts.yaml`；未知資訊一律填 `unknown`。
5. 需要納入主力時，再更新 `docs/main-roster.md` 與 `data/loadouts.yaml`。
6. 更新 README 的收藏數量與花費統計。

## 如何新增一次實戰紀錄

1. 複製 `templates/battle-test-entry.yaml` 的格式。
2. 新增到 `data/battle-tests.yaml` 的 `battle_tests`。
3. 實際使用的配裝必須能在 `data/loadouts.yaml` 找到，並標示 `actual` 或 `theoretical`。
4. 若測試結果讓主力順位或定位改變，同步更新 `docs/main-roster.md`。
