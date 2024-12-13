---
title: 稳定币：金融生态的跨界之桥

date: 2024-10-23 12:00:00 +0800

categories: [RWA]

tags: [stablecoin,rwa]

pin: true

math: false

image: https://fanwb.oss-cn-beijing.aliyuncs.com/img/1000057449.jpg
---

稳定币已迅速成为加密经济的重要支柱，推动了近[半数](https://castleisland.vc/wp-content/uploads/2024/09/stablecoins_the_emerging_market_story_091224.pdf?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)的链上交易活动。稳定币巧妙地弥合了高波动的加密货币与传统法定货币之间的鸿沟，为用户提供了稳定可靠的交易媒介。通过与 Stripe 和 PayPal 等主流支付平台无缝整合，稳定币降低了加密货币的使用门槛，使普通用户无需深入技术细节即可参与加密经济。其快速、低成本的支付特性正在重塑汇款和跨境交易模式，在非洲等面临货币挑战的地区尤为显著。稳定币对加密货币新老用户的独特吸引力，正推动着数字金融的广泛普及，成为金融生态系统演进的关键驱动力。

**何谓稳定币**？

稳定币是一种旨在维持恒定价值的加密资产，通常与黄金或美元等资产按 1:1 比例锚定。这种设计使其非常适合日常交易和资金流转。

稳定币主要分为三种类型：
1. 法币抵押型：由法定货币直接背书，目前占据了稳定币市场的主导地位。代表性产品包括 Tether 的 USDT 和 Circle 的 USDC。
2. 加密抵押型：由加密资产背书，为对冲波动性，往往采用超额抵押机制。代表性产品如 MakerDAO 的 DAI。
3. 算法型：完全依靠算法和智能合约维持价格稳定，无需传统的资产储备，其价格锚定通过铸造和销毁机制来实现。代表性产品如 Aave 的 GHO。

## 抵押方式

稳定币通过特定的抵押策略和市场机制来抵御价格波动，以保持其价格稳定。

**法币抵押型**

法币抵押稳定币由 Tether 和 Circle 等中心化机构发行，其核心特征是由链下银行账户中的法定货币储备提供背书。以 Tether 为例，据其[透明度报告]([Transparency](https://tether.to/en/transparency/?tab=reports))所述：约 15% 的储备投资于比特币等资产及担保贷款，以获取额外收益，同时保持大部分资产为现金或等价物，确保随时满足赎回需求。

- 遵循严格的 1:1 锚定模式，每个代币均由等值的法币或现金等价物支持。1 USDC 即代表 1 美元的价值。
- 发行方保留随时清算储备的能力，以确保拥有充足的抵押品覆盖已发行代币，维护币值稳定。
- 设计的简洁性使法币抵押稳定币很适合在交易和 DeFi 抵押等需要高流动性的场景下使用。

 凭借其简单可靠的特点，法币抵押稳定币在市场上占据主导地位，仅 **USDT** 和 **USDC** 的市场份额就超过 1400 亿美元，占比超过 90%，如图 1 所示。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/stable001.png" style="zoom: 35%;" />
_图1 法币抵押稳定币市场份额 | 图源：TokenTerminal_

**加密抵押型**

加密抵押稳定币是去中心化金融生态系统中的创新产物，在无中央监管的环境中运作，依托智能合约和加密资产构建其稳定机制。

- 这类稳定币的核心策略是过度抵押：用户必须锁定超过铸造稳定币价值的加密资产，在市场波动中建立缓冲。
- 若抵押品价值跌破预设阈值，用户资产将自动划归协议，以保护币值锚定。价格预言机负责实时监控并触发自动清算，维护整体偿债能力。
- 尽管这种模式体现了去中心化的理想，但同时也面临复杂的技术挑战，对智能合约系统的健壮性要求极高。多重智能合约间的复杂交互存在潜在技术风险，需要精细的风险管理和技术审查。

MakerDAO 的 **DAI** 是此模式的典型代表。用户用 ETH 作为抵押品，协议通过**链上治理**动态调整利率，平衡供需以维持币价稳定。凭借其去中心化治理和内部管理机制，DAI 在上月处理了逾 1130 亿美元的资金流转，展现了其在加密金融生态中的重要地位，如图 2 所示。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/1733913791715.png" style="zoom: 80%;" />
_图2 DAI 去中心化运营带来的供应流入与流出 | 图源：Artemis_

**算法型**

算法稳定币的核心理念是在不依赖传统抵押品的情况下，通过智能合约和供应动态调整来维持币值稳定。

- 以 Ampleforth (AMPL) 为代表的协议根据市场价格的变化来调整代币的供应量来维持与 CPI 调整的美元等值。当代币价格突破锚定价格时，协议将增加总供应量；反之，则通过所谓的"rebasing"机制收缩供应。
-  还有一些设计，如曾经的 UST，则引入了另一种“债券”代币（如 LUNA）作为供应调节的辅助机制，来维持币值稳定。

然而，这些创新性尝试的可靠性远低于传统抵押模式。算法的细微缺陷或系统设计中的潜在问题，都可能导致不可预期的黑天鹅事件，UST 的惨烈崩盘就是最鲜明的警示。

## 使用情况

### 交易及兑换

稳定币凭借其可靠性，已成为加密货币交易生态系统中不可或缺的要素，兼具价值储存和交换媒介的双重功能。以市值最大的两种法币抵押稳定币为例，其应用趋势颇为明确。USDC 总供应量中约 **60%** 存储在外部账户 (EOA) 中，另有 **11%** 分布在中心化金融 (CeFi) 平台上，如图 3 所示。

<iframe  width="100%" height="360" src="https://dune.com/embeds/4409153/7387031/"></iframe>
![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/空.png)
_图3 USDC 在加密生态中的应用 | 数据源：Dune_

USDT 的分布呈现更为显著的集中态势，其中 **70%** 位于 EOA 中，**25%** 驻留在 CeFi 平台上。USDT 的广泛采用源于 Tether 在区块链部署上的灵活性和前瞻性，其迅速进入新兴区块链并与众多中心化平台建立深度整合，使其在稳定币市场中占据优势地位。

<iframe width="100%" height="360" src="https://dune.com/embeds/4409325/7387270/"></iframe>
![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/空.png)
_图4 USDT 在加密生态中的应用 | 数据源：Dune_

这种分布提现了稳定币的核心价值：提供金融稳定性。EOA（如 Metamask 和 Phantom 等非托管钱包）本质上是用户规避加密货币波动风险的避风港，让投资者能快速将资产转换为相对稳定的形态。而像 Binance 和 Coinbase 这样的 CeFi 平台不仅提供资产转换渠道，更为跨境交易构建了便捷桥梁。这点对 USDT 的众多网络上（尤其是 Tron）的广泛部署十分关键，使其成为了拉丁美洲和非洲新兴经济体用户的[理想选择](https://www.getorbital.com/news-media/the-importance-of-usdt-payments-on-tron-in-emerging-markets?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)。由此不难看出稳定币在保护投资和提供全球金融可及性两方面都扮演了重要角色。

### DeFi

在 DeFi 领域，法币抵押稳定币相较于去中心化稳定币存在感偏低，原因主要在于后者采用激励机制（如分发 AAVE、MKR 等原生协议代币）来推动其生态的发展。

但 PayPal 的 PYUSD 是一个特例。在进军 Solana 生态系统的过程中，PayPal 与 Kamino Finance 携手合作，为 PYUSD 存款提供高达 **[17%](https://www.dlnews.com/articles/defi/paypal-stablecoin-supply-hits-569-million-usd-on-solana/?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)** 的年收益率，显著高于 USDC 在 Solana 上年化 **9%** 的收益率。这一策略在初期颇有成效，推动 PYUSD 的市值迅速攀升至近 **10 亿**美元，其中近 **20%** 流通于去中心化交易所，用户通过提供流动性赚取收益。然而，当激励措施收缩时， PYUSD 的市值从 8 月的峰值骤降近 **40%**，凸显了收益驱动策略在挑战现有主流稳定币市场地位、塑造采用路径中的关键作用。

<iframe width="100%" height="360" src="https://dune.com/embeds/4412922/7392743/"></iframe>
![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/空.png)
_图5 PYUSD 在加密生态中的应用 | 数据源：Dune_

同样，得益于精心设计的激励机制，Aave 推出的超额抵押稳定币 GHO 也在 DeFi 领域引起了广泛关注。数据显示，约 80% 的 GHO 供应被用于借贷，另有5%在各大 DEX 中流通。这种独特的分布与 Aave 将 GHO 定位为其借贷市场核心的战略高度契合，进一步巩固了稳定币在整个 DeFi 生态中的地位，并促进了其更广泛的应用。

<iframe width="100%" height="360" src="https://dune.com/embeds/4413141/7393067/"></iframe>
![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/空.png)
_图6 GHO 在加密生态中的应用 | 数据源：Dune_

总体来看，如图 7 所示，稳定币在 DeFi 中的应用范围相当广泛，约占整个生态的 **25%**，涵盖去中心化交易所、借贷以及其他金融活动，为用户提供了多元化的价值捕获途径。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/6718c0c148654bb91e26bb76_ADKq_Nb2veD0mrGrH40OGadVxc6gGw63-pQXQwilX7dU4kQ5gTDzMuIfcnVPJKPmK0Qz-G5S4MqkxeABCSElHoDYdZLlneT2O2YvFsDPMhd4QtQRt71IuK2IciCsd4RSKTVFcyL27xyqBW2ArzQm35gHoI64z99tZ48X96gJsOtZZOyzvxv63QA32_MXZh.png" style="zoom: 60%;" />
_图7 按金融活动类型分类的稳定币交易量 | 图源：Visa_

### 汇款及支付

稳定币在跨境支付领域展现出显著的低成本优势，相较于传统国际汇款服务动辄 6% 的高额手续费，其成本优势尤为突出。
<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/stable002.png" style="zoom: 60%;" />
_图8 不同渠道的平均汇款成本（占汇款金额的百分比）| 图源：Coinbase_

区块链网络的交易费用差异显著，从几分之一美分到几美元不等。像 Solana、Fantom、Polygon 和 TON 等新一代区块链平均交易费用在一美分以下，而 BNB、Tron 和 Ethereum 等老一代网络的费用则可能需要数美分到数美元的费用。如图 9 所示。不过随着 Layer 2 解决方案的发展，Base、Arbitrum 和 Optimism 等基于 Ethereum 的平台在 Dencun 升级后，也已将交易成本压低至[不到一美分](https://www.growthepie.xyz/fundamentals/transaction-costs)，极大地改善了用户体验。
<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/stable003.png" style="zoom:30%;" />
_图9 主流 Layer-1 区块链的平均交易成本 | 图源：TokenTerminal_

即便是在费用相对较高的网络中，加密货币交易的成本仍远低于传统支付系统，这种成本效益直接反映在稳定币使用量的稳步增长上。过去四年间，尽管加密货币市场经历周期性波动，但稳定币的使用量却在持续攀升。从 2020 年第三季度至 2021 年底的牛市期间，稳定币使用量显著增长；随后即便进入熊市，从 2022 年到 2023 年第三季度，增长势头依然不减。尤为瞩目的是，每月稳定币发送者数量从 2020 年 10 月的约 **230 万**激增至如今的 **1200 万**，增长近 **600%**，充分显示了稳定币在加密生态之外的持续吸引力和实际价值。
<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/stable004.png" style="zoom:80%;" />
_图10 每月稳定币发送者数量 | 图源：TokenTerminal_

稳定币的应用正在发展中经济体掀起新的变革。一项针对巴西、印度、印度尼西亚、尼日利亚和土耳其 2541 名成年人的调查显示，**47%** 的受访者使用稳定币以获得更高储蓄利率，**43%** 的人看重其便捷的货币兑换功能，另有 **37%** 的人将其视为获取美元资产的途径。尽管调查样本有限，但这些数据仍表明稳定币在新兴市场正逐步发展成为一种跨越传统加密货币应用边界的多功能金融工具，在满足复杂经济需求方面发挥着越来越重要的作用。
<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/1733987805135.png" style="zoom: 60%;" />
_图11 用户使用稳定币的主要目的 | 图源：CastleIsland_

## 影响

Tether 对加密生态系统的影响显著，如图 12 所示，其用户数已达 **6000 万**，占到了整个行业 [**2.2 亿**](https://a16zcrypto.com/posts/article/state-of-crypto-report-2024/?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)活跃用户基数的 **27%** 以上，体现了稳定币在推动加密货币普及中的重要作用。
<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/stable005.png" style="zoom:80%;" />
_图12 稳定币持有者总数 | 图源：TokenTerminal_

USDT 作为网络活动的重要引擎，其影响力巨大：仅在 10 月 21 日单日，就在各个区块链上支付了超过 **700 万**美元的费用，由此也能看出稳定币在推动区块链生态系统增长中的重要作用。

更为显著的是，过去一个月中，USDT 在以太坊网络上的 gas 消耗位居[**第三**](https://www.theblock.co/data/on-chain-metrics/ethereum/top-20-gas-consuming-smart-contracts-30d?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)，贡献了网络总费用（约 [**40270 ETH**](https://tokenterminal.com/explorer/projects/ethereum?v=ZmI4ZjUwOGExM2Y1OGRmY2QxMDY2NTZh&utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)）的 5% 以上（约 [**2310 ETH**](https://www.theblock.co/data/on-chain-metrics/ethereum/top-20-gas-consuming-smart-contracts-30d?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)）。在 Tron 网络上，USDT 更是占据了每周 [**96%**](https://tronscan.org/?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email#/data/rankings/contracts) 的网络活动。如此大规模的费用通过补偿验证者直接支持了网络安全，更凸显了稳定币对区块链经济生态的深远影响。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/stable006.png" style="zoom:80%;" />
_图13 稳定币发行商每日 gas 费 | 图源：TokenTerminal_

## 监管格局

稳定币发行商已超越德国和韩国成为美国国债第 18 大持有者。随着应用的深化，稳定币的角色可能延伸至购买国债等领域，从而进一步融入主流金融体系。其日益增长的影响力凸显了对明确监管的迫切需求，如去年引入的《[支付稳定币透明度法案](https://www.congress.gov/118/bills/hr4766/BILLS-118hr4766ih.pdf?utm_campaign=Newsletter&utm_medium=email&_hsmi=309410475&utm_content=309410475&utm_source=hs_email)》和《[Lummis-Gillibrand 支付稳定币法案](https://www.gillibrand.senate.gov/wp-content/uploads/2024/04/LIP24254.pdf?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)》，以确保这一新兴领域的安全性和可信度。美国监管政策的模糊不清，加之地缘政治和宏观经济因素的影响，可能逐渐削弱美元计价稳定币的主导地位。

- **欧洲的《加密资产市场法规》(MiCA)** 将于 2024 年 12 月 30 日全面生效。该法规对中心化发行商进行了严格限制，要求发行商必须获得 MiCA 许可证，方可在欧盟内公开提供或交易资产参考代币或电子货币代币，且不设过渡期。如果 Tether 等公司未在 2024 年底前达到合规要求，则 USDT 等稳定币可能在欧盟交易所被下架。此外，为保护货币主权，MiCA 对与外币挂钩的稳定币使用进行了限制，当每日使用量“作为单一货币区内的交换手段超过 100 万笔交易和 2 亿欧元”时，必须停止发行。

- **泰国最古老的银行推出该国的首个稳定币**：暹罗商业银行与金融科技公司 Lightnet 合作，推出了泰国的首个用于跨境支付和汇款的稳定币。
- **阿联酋央行已原则上批准了 AED 稳定币**在其《支付代币服务监管框架》下的申请。若最终获准，AE Coin 将可在交易所和去中心化平台作为本地交易对，并可用于商品和服务支付。值得注意的是，这一监管进展发生在 Tether 宣布推出 AED 稳定币的数月之后，其 CEO 当时表示，这将“提供美元的替代选择”。

## 风险与挑战

- **中心化**：USDT 和 USDC 等法币抵押稳定币由中心化机构发行，用户需信任这些机构能保持足够的储备金。这种模式引入了显著的交易对手风险：储备不足可能导致流动性危机，使用户面临资金无法兑付的问题。此外，中心化还可能带来监管干预、管理不善或资金被冻结等风险。

- **透明度**：由于法币抵押稳定币的储备在链下，由现金或现金等价物支持，因此透明度对于维护信任至关重要。Tether 和 Circle 等发行商需要定期进行审计，并公布储备文件，如Tether 的 [透明度报告](https://tether.to/en/transparency/?tab=reports&utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)，以证明其偿债能力。对于加密抵押稳定币来说，透明度问题较小，因为所有资产都可以在链上验证。协议通常会提供仪表板，如 MakerDAO 的 [DAI 统计仪表板](https://daistats.com/?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email#/)，详细显示抵押率、总债务、抵押类型和贷款稳定性。

- **脱钩**：脱钩是指稳定币价值显著偏离预期锚定价格的情况。最著名的脱钩事件是 2022 年 5 月 UST 和 LUNA 的崩盘，此次事件也暴露出了算法稳定币的潜在风险。目前，尽管脱钩仍偶有发生，但稳定币整体的稳定性正在逐步提升，如图 14 所示，这主要归功于流动性的持续涌入、行业的成熟以及协议的久经考验。得益于充足的储备和活跃的链上治理社区，稳定币已具备了更强的流动性冲击抵御能力。
<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/coin-metrics-new-chart (2).jpeg" style="zoom:75%;" />
_图14 主流稳定币的价格稳定性 | 图源：CoinMetrics_

## 展望

央行利率下降催生了对稳定币的深入探讨。投资者追求更高收益的趋势已初露端倪，如下图所示，加密货币无抵押贷款平台 Maple Finance 的贷款总额已攀升至历史新高。

<iframe width="100%" height="360" src="https://dune.com/embeds/4414851/7395318/"></iframe>
![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/空.png)
_图15 MapleFinance 未偿贷款总额 | 数据源：Dune_

稳定币市场在收益模型方面正在酝酿创新。Ondo Finance 的 **[USDY](https://ondo.finance/usdy?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)** 和 Angle 的 **[stEUR](https://www.angle.money/steur?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)** 等代币化货币市场基金通过每日分红获得成功，可能激励其他发行商采用类似的利润分享模型。这一趋势旨在挑战 Tether 和 Circle 等既有玩家，后者目前主要通过将用户存款再投资于政府证券获利。新兴竞争者可能借助收入分享机制抢占市场份额，进而重塑稳定币生态，为用户提供更具吸引力的选择，例如 BitGo 即将推出的[稳定币](https://www.coindesk.com/markets/2024/09/18/bitgo-to-enter-stablecoin-market-with-reward-bearing-usds-coin?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)。但由于监管机构正致力于构建平衡创新、消费者保护和金融稳定的明确框架，这些创新模型短期内可能会面临监管审查压力。

受 **[Ethena](https://ethena.fi/?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)** 模型启发的 delta 中性策略也将持续演进。尽管在市场低迷期维持策略仍存挑战，但后续迭代可能将充分利用日益成熟的期货和期权市场。其目标是简化复杂策略，降低准入门槛，利用复杂的加密衍生品使高级金融产品大众化。

央行数字货币 (CBDC) 的发展可能将迎来转折。从提升金融包容性到改进支付效率，各国动机各异，但都面临复杂的设计抉择。考虑到法币抵押稳定币的简单性和有效性（过去十年中促成近 **[35 万亿](https://tokenterminal.com/explorer/metrics/stablecoin-transfer-volume?v=Y2E3YjNmYjljZjI5Y2E4ZDc4ZjAxN2Yx&utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)**美元的交易），各国央行可能会暂时选择将这类成熟解决方案整合至传统金融体系。正如如[加拿大](https://www.cato.org/commentary/australia-canada-colombia-were-right-pause-cbdc-plans?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)、[新加坡](https://www.mas.gov.sg/news/media-releases/2023/mas-finalises-stablecoin-regulatory-framework?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)和[英国](https://www.coindesk.com/policy/2024/04/15/uk-to-issue-new-crypto-stablecoin-legislation-by-july-minister-says?utm_campaign=Newsletter&utm_medium=email&_hsmi=330295260&utm_content=330295260&utm_source=hs_email)的实践所示，在就最佳 CBDC 模型达成共识前，这种务实方法或将成为权宜之计。



