# Btcjiaoyi

BTC 3分钟 EMA20 失衡衰竭交易策略项目。

## 当前文件

- `tradingview/btc_ema20_imbalance_v0_1.pine`：TradingView Pine Script V0.1 可回测策略。
- `tradingview/btc_ema20_imbalance_v0_2.pine`：V0.2，在 V0.1 基础上新增 A版“三波分布衰竭空”模块。
- `docs/strategy_spec_v0_1.md`：策略逻辑说明与后续迭代计划。

## V0.1 核心逻辑

V0.1 先把主观打法拆成六个内部指标：

1. Age：沿 EMA20 单边运行时间。
2. Extension：价格远离 EMA20 的失衡程度。
3. Flatten：EMA20 从陡峭到走平的动能衰竭。
4. Touch：价格重新靠近 EMA20。
5. Rejection：影线拒绝。
6. Confirm：反向确认K线。

策略默认做 BTC 3分钟图，使用结构止损和 3R 止盈。

## V0.2 新增：A版三波分布衰竭空

A版不是等跌破箱体后再空，而是更激进：

1. 前面已经涨了很多。
2. 高位进入横盘 / 分布。
3. 出现三次上攻。
4. 第三波上攻没有有效打开新空间。
5. 第三波出现上影线或失败迹象。
6. 价格收回 EMA20 下方后，提前做空。

A版追求更好的入场位置和更高盈亏比，但会比确认空更容易出现假信号。
