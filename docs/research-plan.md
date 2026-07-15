# Main Blade 研究計畫

目前版本：**v1**｜建立日期：2026-07-16｜狀態：進行中

本計畫只研究核心三機：藍鳳凰、女武神、狐狸。機器可讀的完整版本資料以 [`data/research-plan.yaml`](../data/research-plan.yaml) 為準；本文件是目前版本的人讀摘要。

研究候選不等於已持有零件，也不會自動改寫 `inventory`、`opt` 或 `dck`。只有實測結果或想法足以改變角色目標、候選配置、假說、判定門檻、候選排序、信心或階段結論時，才建立下一個完整版本。

## v1 配置假說總覽

| Main Blade | 既有 dck 基準 | 到貨池研究候選 | 不限持有理想案 | 信心 |
|---|---|---|---|---|
| 藍鳳凰 | `1-50 LF` | `1-50 I` | `1-50 I` | 中 |
| 女武神 | 一體式＋`J` | 一體式＋`GP` | 一體式＋`P` | 低至中 |
| 狐狸 | 待定 | Brush Jaggy `9-60 GP` | Brush Jaggy `1-60 U` | 中 |

若狐狸隨機包實際包含 `U`，優先增加 Brush Jaggy `9-60 U` 與 `1-60 U` 的比較；在收到並確認前，不把該零件視為已持有。

## 共通規則與計分模型

本版以 Takara Tomy 第 12 版、先取 4 分為主要判定基準：

- Spin：1 分
- Over：2 分
- Burst：2 分
- Xtreme：3 分
- 官方規則沒有 Own Finish 降分保護；自行進入 Over／Xtreme 區仍可能送出完整 2／3 分

單回合淨期望分差：

```text
EV = [pSpin + 2 × (pOver + pBurst) + 3 × pXtreme]
   - [qSpin + 2 × (qOver + qBurst) + 3 × qXtreme]
```

如果狂暴化主要增加 2 分 Burst／Over，同時增加 3 分自殺 Xtreme，新增 Burst／Over 機率必須大於新增自殺 Xtreme 機率的 1.5 倍，單回合淨期望分差才會上升。

近期 WBO 頒獎資料只用來選擇假想敵，不能直接視為逐回合勝率。v1 主要參考：Shark Scale `1-70 LR`、Wizard Rod `1-60 H`、Aero Pegasus `1-60 R`、Cobalt／Meteor Dragoon、Silver Wolf `9-60 FB`。

## 藍鳳凰

### 角色目標

極限狂暴的高變異破陣手。主要追求 Over、Burst、Xtreme，面對任何主流都保留爆冷能力；可以犧牲持久與控制，但新增自殺成本必須被實際高分終結補回。

### v1 主假說

`Phoenix Wing 1-50 I` 比既有 `1-50 LF` 更接近角色極限：`I` 的低高度、16 齒與高機動可增加下位攻擊、Burst 接觸和首擊速度。

`1-50 LF` 保留為實戰容錯基準；`3-60 R/LR` 僅作近期 Phoenix Wing 高 CP 配置的對照，不是角色首選。

### 優先測試

1. `1-50 I` 對 `1-50 LF`。
2. 先測 Shark Scale 與 Wizard Rod 類型。
3. 記錄自殺 Xtreme、無有效接觸、首擊時間與高分終結。
4. 實秤不同配置，避免忽略 Phoenix Wing 個體重量差。

### 判定門檻

- 先比較官方 4 分制下的淨期望分差。
- 若 `I` 的 EV 不高於 `LF`，但角色體驗更符合使用者偏好，可保留 `I` 為人格配置、`LF` 為比賽配置。

## 女武神

### 角色目標

穩偏輸出的最高 CP 機。對攻擊型以存活與 Spin Finish 建立下限；對持久、防禦型保留 Over／Burst 的二分路線。

### v1 主假說

既有一體式＋`J` 保留為第一個實測基準，但 `J` 可能放大偏重心、16 齒與 Bound 回彈造成的自耗。

- 到貨池優先候選：一體式＋`GP`
- 不限持有理想案：一體式＋`P`
- 對照：`J`、`K`、`LR`

`GP/P` 可用平射守中心、角度發射進攻，理論上較符合「轉停攻擊型、擊飛持久型」的雙路線。

### 優先測試

1. 到貨後先比較 `J` 與 `GP`。
2. 分別對主流攻擊型與 Wizard Rod 類型測試。
3. 記錄有效 Dash 次數、Bound 接觸後自耗、末段失衡與 Spin Finish。
4. 取得 `P` 或 `K` 後再做同條件比較。

### 判定門檻

以跨假想敵的整體 EV 與最差 matchup 為主，不能只看單次大擊飛。理想 Bit 必須同時保留對攻擊型的一分路線與對持久／防禦型的二分路線。

## 狐狸

### 角色目標

以反覆接觸累積 Burst。面對攻擊型避開前段鋒芒並轉停；面對持久、防禦型則主動追擊，最大化 Burst Finish。

### v1 主假說

- 到貨池研究候選：Fox Brush Jaggy `9-60 GP`
- 不限持有理想案：Fox Brush Jaggy `1-60 U`
- 低變異對照：Brush Jaggy `9-60 U`
- 防守對照：Brush Jaggy `9-60 H`
- Assist Blade 對照：Brush Jaggy／Brush Heavy

`9-60 GP` 用圓整 Ratchet 控制自身 Burst，並以平射／斜射切換避戰與主動接觸。`1-60 U` 則用不規則碰撞換取更高 Burst 壓力，再由 Unite 的後段行為保留轉停機會。

如果未來目標改成總勝率而非 Burst 人格，再研究 Delta Peak Heavy `9-60 K`；本版不把它列為狐狸的角色首選。

### 優先測試

1. 到貨後先建立 `9-60 GP` 基準。
2. 若取得 `U`，比較 `9-60 U` 與 `1-60 U`。
3. 分開統計對攻擊型的 Spin／自身失分，以及對持久、防禦型的 Burst。
4. 有 Heavy 後進行 Jaggy／Heavy 單變因比較。

### 判定門檻

不得用總勝率掩蓋 matchup。`1-60 U` 只有在增加的 Burst 收益足以抵銷自身 Burst、KO 與持久損失時，才壓過 `9-60 U`。

## 實測輸入方式

使用者不需要在遊玩時做完整表格；之後可以直接憑印象口述。AI 會：

1. 將原意整理成 [`data/battle-tests.yaml`](../data/battle-tests.yaml) 的質性案例。
2. 未確認日期、場數、場地、零件與勝率填 `unknown`。
3. 不把「常常、明顯、感覺」換算成虛構數字。
4. 同步更新 [`docs/test-cases.md`](test-cases.md)。
5. 只有案例被吸收後改變研究假說、候選排序、信心或階段結論時，才新增研究計畫版本。

若進行有控制的比較，目標為每個候選配置對每類假想敵 40 至 50 回合，並交換發射順序與站位。

## 進版規則

- 新增案例：不升版。
- 修正錯字、補來源：不升版。
- 改變角色目標、主假說、候選配置、測試變因、規則、判定門檻、候選排序、信心或階段結論：建立下一版。
- 新版保存完整快照，記錄 `supersedes`、變更理由及依據案例編號；舊版只改為 `superseded`，不刪除。

## v1 主要來源

- [Takara Tomy 第 12 版規則](https://beyblade.takaratomy.co.jp/beyblade-x/_image/regulation.pdf)
- [2026-06-28 至 07-11 WBO 頒獎配置彙整](https://note.com/kamen_a/n/n8c00dfd22387)
- [Phoenix Wing 近期配置資料](https://www.beymetatool.com/blades/PhoenixWing)
- [Ignition Bit 分析](https://beyblade.wiki/ignition-bit/)
- [Glory Valkyrie 官方產品頁](https://beyblade.takaratomy.co.jp/beyblade-x/lineup/ux20.html)
- [Glory Valkyrie 首批賽事向實測](https://note.com/sabo_ip01/n/ndf66bd69e718)
- [Brush Main Blade 分析](https://beyblade.wiki/brush-main-blade/)
- [Fox Brush Jaggy 1-60 Unite 地方賽案例](https://www.reddit.com/r/BeybladeX/comments/1sp0ghq/won_3rd_in_a_local_tournament_with_this_deck/)

## 版本紀錄

| 版本 | 日期 | 狀態 | 內容 |
|---|---|---|---|
| v1 | 2026-07-16 | current | 建立核心三機角色目標、第一批候選配置、共通計分模型與實測門檻。 |
