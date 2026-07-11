# 術語

## 狀態

- `owned`：已持有，現階段可實際使用。
- `ordered`：已訂購但尚未收到，不得假設版本或實際零件。
- `wishlist`：想買但尚未訂購。

## 配置

- `stock`：原廠配置。
- `actual`：目前真的組得出來的配裝。
- `theoretical`：理論配置、待到貨、待確認版本或待確認零件。
- `unknown`：未確認資訊，不可用推測補齊。

## 零件

- `Blade`：上層攻擊環或主體零件。
- `Ratchet`：中層棘輪零件。
- `Bit`：底部軸心零件。

目前所有 Blade / Ratchet / Bit 的官方名稱都尚未確認，因此資料中維持 `unknown`。

## 隨機款

`random_variant: true` 代表已知是隨機款，但尚未收到前不得推測實際版本。實際版本需在到貨後更新 `confirmed_variant`。
