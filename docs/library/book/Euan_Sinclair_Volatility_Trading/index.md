# Volatility Trading (波动率交易 · 全书原著 Markdown 版)

- **原著作者**: Euan Sinclair (物理学家、对冲基金合伙人、资深做市商交易员)
- **出版系列**: John Wiley & Sons (*Wiley Trading Series*)
- **版本规格**: 原版正文字符级 100% 结构化切片（全书 12 篇独立 Markdown 章节）
- **Token 消耗**: **0 Token（纯本地 M2 引擎物理切片）**
- **核心定位**: 全球公认最权威的波动率量化建模、动态对冲、Greeks 管理与交易心理学经典

---

### 全书完整章节导航与导读

| 章节 | 文件链接 | 核心主题与涵盖要点 |
|---|---|---|
| **导论** | [00. 交易流程导论](ch00_introduction.md) | 交易流程哲学、预测与执行、优势（Edge）的本质 |
| **第1章** | [01. 期权定价与 BSM 模型的局限](ch01_option_pricing.md) | Black-Scholes-Merton 假设推导、波动率常数假设的缺陷 |
| **第2章** | [02. 波动率统计测量与估计器对比](ch02_volatility_measurement.md) | Close-to-Close / Parkinson / Garman-Klass / Rogers-Satchell / Yang-Zhang、高频日内数据方差 |
| **第3章** | [03. 隐含波动率动态学与微笑结构](ch03_implied_volatility_dynamics.md) | 隐波动态学、水平移动、微笑曲线（Smile/Skew Dynamics）生成机制 |
| **第4章** | [04. 动态对冲与离散调仓摩擦](ch04_hedging.md) | Delta 对冲策略、定期对冲 vs 阈值对冲、Whalley-Wilmott 渐进对冲边界 |
| **第5章** | [05. 对冲期权头寸与路径依赖性](ch05_hedged_positions.md) | 离散对冲损耗（Discrete Hedging）、Gamma 路径依赖、真实 PnL 分布 |
| **第6章** | [06. 资金管理与凯利准则应用](ch06_money_management.md) | 连续变动环境下的 Kelly 仓位配比、防破产最优比例与近似估算 |
| **第7章** | [07. 交易评估与夏普比率局限](ch07_trade_evaluation.md) | 风险调整后收益指标、Sharpe 衰减、目标设定与业绩持久性检验 |
| **第8章** | [08. 交易心理学与行为金融陷阱](ch08_psychology.md) | 自我归因偏差、过度自信、损失厌恶、锚定效应与确认偏差 |
| **第9章** | [09. 一笔期权交易的完整生命周期](ch09_trade_lifecycle.md) | 真实案例全流程复盘：盘前分析、建仓执行、动态追踪、盘后归因 |
| **附录A** | [附录A: 无模型隐含方差与 VIX 指数](appendix_a_vix.md) | Model-Free Implied Variance 数学推导与 CBOE VIX 编制原理 |
| **附录B** | [附录B: Black-Scholes-Merton 方程与 Greeks](appendix_b_bsm.md) | BSM 偏微分方程完整公式集与 Delta/Gamma/Vega/Theta 一阶与二阶敏感度 |

---

### 与《Orange期权实战知识体系》的互补关系

* **本专著（Sinclair《波动率交易》）**：提供严谨的**数学统计工具箱**（5 种波动率估计器对比）、离散对冲损耗模型（Whalley-Wilmott）以及科学的仓位凯利公式；
* **《Orange期权体系》**：提供**中国商品期权本土实战方案**（五层信号金字塔、Orange双击暴赚隐波模型、权利金-50%硬止损规程）。
