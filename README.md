# personal-beybladex

這個 Repository 用來管理 Beyblade X 收藏、零件庫、配裝、購買紀錄與實戰測試紀錄。目標是讓 AI（ChatGPT / Codex）可以直接讀取此 repo，取得最新收藏資訊，避免每次重新整理。

本 repo 是公開資料庫，不應包含個資、Token、Secret、帳號憑證或私人聯絡資訊。所有文字檔使用 UTF-8，說明文件使用繁體中文。

## 四層配置模型

| 代號 | 意義 | 定義 |
|---|---|---|
| `org` | Original | Takara Tomy 原廠配置與官方設計策略 |
| `opt` | Optimal | 純粹依物理結構推導的單顆理論最佳配置 |
| `dck` | Deck | 核心三機的目標永久配置 |
| `tmp` | Temporary | 依目前已實際擁有的零件可組出的暫時配置 |

## 收藏總覽

| 類別 | 數量 |
| --- | ---: |
| 已持有 | 7 顆 |
| 已訂購 | 4 顆 |
| 總數 | 11 顆 |

## 主 Inventory

完整表格見 [docs/collection.md](docs/collection.md)。

| 型號 | 中文名 | Blade | 狀態 | 備註 | 完成度 |
|---|---|---|---|---|---|
| BX-23 | 紅鳳凰 | Phoenix Wing | 擁有 | 備選 | ⭐☆☆☆☆ |
| UX-17 | 隕星龍 | Meteor Dragoon | 擁有 | 左旋 | ⭐☆☆☆☆ |
| CX-14 | 騎士堡壘 | Knight Fortress GV | 擁有 | 備選 | ⭐☆☆☆☆ |
| BX-35-05 | 藍鳳凰 | Phoenix Wing | 擁有 | 核心三機順位1、最喜歡的鳳凰 | ⭐☆☆☆☆ |
| UX-14 | 天蠍 | Scorpio Spear | 擁有 | 攻擊不足、持久不敵神杖類型，缺乏特色，已退出核心 | ⭐⭐⭐⭐☆ |
| BX-26 | 獨角獸 | Unicorn Sting | 路上 | 零件、備選 | ⭐☆☆☆☆ |
| BX-36 | 鯨魚 | Whale Wave | 路上 | 隨機包3款 | ⭐☆☆☆☆ |
| CX-06-01 | 白狐 | Fox Brush J | 已持有 | 核心三機順位3、配裝待定、原裝 9-70GR | ⭐☆☆☆☆ |
| UX-20 | 女武神 | Glory Valkyrie | 路上 | 核心三機順位2 | ⭐☆☆☆☆ |
| CX-13 | 龍王 | Bahamut Blitz BK | 路上 | 零件、備選 | ⭐☆☆☆☆ |
| CX-12 | 鳳凰閃焰 | Phoenix Flare Z | 擁有 | 同事日本代購 | ⭐☆☆☆☆ |

## 核心三機

完整規則見 [docs/main-roster.md](docs/main-roster.md)。

| 順位 | Blade | dck鎖 | dck軸 | 定位 | 完成 |
|---|---|---|---|---|---|
| 1 | 藍鳳凰 | 1-50 | LF | 第一主攻、核心主力 | ☑ |
| 2 | 女武神 | 一體化 | J | 第二主攻、Bound 爆發擊飛 | ☑ |
| 3 | 狐狸 |  |  | 連續追擊、配裝待定 | ☐ |

目前零件池可同時組出的雙機極致配置：

| Blade | tmp 配置 | 定位 | 驗證狀態 |
|---|---|---|---|
| 藍鳳凰 | 4-50 J | 低位破陣、極限主攻 | 完整配對待實測 |
| 白狐 | 9-60 GR | 連續 X Dash、廣範圍連打 | 完整配對待實測 |

## 研究與實測

- [Main Blade 研究計畫](docs/research-plan.md)：只針對藍鳳凰、女武神與狐狸，保存版本化目標、假說、候選配置、計分模型與測試門檻。
- [實測案例](docs/test-cases.md)：收錄使用者實際遊玩後的口述或統計結果；不確定日期、場數與零件維持 `unknown`。
- `data/research-plan.yaml` 與 `data/battle-tests.yaml` 是機器可讀的事實來源，Markdown 文件是人讀摘要。
- 新增案例不會自動讓研究計畫升版；只有目標、候選配置、假說、規則、判定門檻、候選排序、信心或階段結論改變時才建立下一版。

## 花費統計

| 類別 | 金額 |
| --- | ---: |
| 已持有 | 12500 TWD |
| 已訂購 | 5100 TWD |
| 累計 | 17600 TWD |

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
│   ├── research-plan.yaml
│   └── battle-tests.yaml
├── docs/
│   ├── collection.md
│   ├── main-roster.md
│   ├── research-plan.md
│   ├── test-cases.md
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
4. 若已確認 `org` 的 Blade / Ratchet / Bit，更新 `data/parts.yaml`；未知資訊一律填 `unknown`。
5. 需要納入核心三機時，再更新 `docs/main-roster.md` 與 `data/loadouts.yaml`。
6. 更新 README 的收藏數量與花費統計。

## 如何新增一次實戰紀錄

1. 使用者可以直接憑印象口述，不必提供完整逐場統計。
2. 依 `templates/battle-test-entry.yaml` 格式，新增到 `data/battle-tests.yaml` 的 `test_cases`。
3. 已知配裝標示 `org`、`opt`、`dck` 或 `tmp`；未知日期、場數、場地與對手零件填 `unknown`。
4. 同步更新 `docs/test-cases.md` 的索引與摘要。
5. 若案例改變 Main Blade 研究方向，再新增 `data/research-plan.yaml` 的完整版本並同步 `docs/research-plan.md`；不要直接覆蓋舊版。

## 如何更新研究計畫

1. 研究計畫只包含藍鳳凰、女武神與狐狸。
2. 單純新增案例、修字或補來源不升版。
3. 角色目標、候選配置、假說、規則、判定門檻、候選排序、信心或階段結論改變時，複製目前完整版本建立下一版。
4. 新版記錄 `supersedes`、變更理由與依據案例編號；舊版改為 `superseded`，不刪除。
5. 研究候選不等於已持有零件，也不自動覆蓋 `inventory`、`opt` 或 `dck`。
