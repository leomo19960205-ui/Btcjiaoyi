# Btcjiaoyi

BTC 3分钟 EMA20 失衡衰竭交易策略项目。

## 当前文件

- `tradingview/btc_ema20_imbalance_v0_1.pine`：TradingView Pine Script V0.1 可回测策略。
- `docs/strategy_spec_v0_1.md`：策略逻辑说明与后续迭代计划。

## V0.1 核心逻辑

V0.1 先把你的主观打法拆成六个内部指标：

1. Age：沿 EMA20 单边运行时间。
2. Extension：价格远离 EMA20 的失衡程度。
3. Flatten：EMA20 从陡峭到走平的动能衰竭。
4. Touch：价格重新靠近 EMA20。
5. Rejection：影线拒绝。
6. Confirm：反向确认K线。

策略默认做 BTC 3分钟图，使用结构止损和 3R 止盈。
