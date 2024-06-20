---

title: zkEVM Rollup：从理论到现实

date: 2023-02-20 12:00:00 +0800

categories: [Blockchain,Layer 2]

tags: [rollup, zkEVM]

math: true
---

为了解决区块链Layer 1网络的扩容问题，Rollup方案应运而生。结合零知识（ZK）技术，ZK Rollup成为Layer 2赛道中备受瞩目的解决方案。然而，对于大多数人而言，ZK、Rollup和EVM等相关概念可能有一定的理解难度。因此，本份研报的目标是用简洁易懂的语言，对zkEVM Rollup的一系列概念进行系统梳理，深入分析zkEVM Rollup技术的发展和现状，并详细解读其中的主要生态项目。通过这样的方式，旨在帮助您全面深入地了解和评估zkEVM Rollup赛道的发展趋势。

## 1 理解ZK

零知识证明（Zero-Knowledge Proof，简称ZK或ZKP）是一种密码学方法，它允许一方（证明者）向另一方（验证者）证明某个事实的正确性，而无需泄露任何与该事实相关的具体细节。因此，ZK技术在隐私保护领域提供了广阔的应用前景。

除了隐私保护方面的优势，ZK技术在ZK Rollup中还起到解决“验证难”问题的关键作用。在区块链中，“验证”过程至关重要，在以太坊这样的平台中，大部分计算过程都是为了满足验证需求。ZK Rollup通过利用ZK技术，极大地减少了节点网络在验证过程中所需的时间。举例来说，如果验证一个区块是否符合整个网络规则的过程耗时很长，那么可以由一个验证者首先验证并生成与该区块计算结果相关的“证明”，其他节点只需快速验证这个“证明”，而不需要进行复杂的原始区块计算即可达成区块验证的效果。

### 1.1 生成密钥、证明及验证

在ZK中，我们需要首先将待验证的问题转化为数学表达式，进而转化为多项式，并将其表示为算数电路的形式。当程序转换为算术电路时，它被分解为由加法、减法等基本算术运算组成的单个步骤。图 1 是一个电路图的示例，可以注意到在电路中所有的运算被拆分为最简单的基本运算。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/uTools_1689599221750.png" style="zoom: 67%;" />
_图1 电路示意图 | 图源：https://cs251.stanford.edu/lectures/lecture14.pdf_

使用电路和一些随机数作为输入，可以生成证明密钥（pk，proving key）和验证密钥（vk，verification key），用于后续的验证过程，如图 2 所示。

![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/zk过程1.png)
_图2 “公共参数”的生成_

我们的证明系统还需要两种类型的输入——私有输入和公开输入，与证明密钥一起生成证明。其中，私有输入（witness）是我们想要隐藏的秘密，而公开输入是可以公开的信息。当验证方接收到证明后，使用公开输入、证明和验证密钥来验证该证明，并返回验证结果（即是否验证成功）。图 3 是ZK-SNARK的证明和验证过程。实现零知识证明的协议和方式有很多，SNARK是比较容易理解的一种，也是现阶段多数项目的选择。后文也将阐述SNARK的优势和不足。

![](https://fanwb.oss-cn-beijing.aliyuncs.com/img/zk过程2.png)
_图3 ZK-SNARK的证明过程和验证过程_

以一个记录账户状态的 Merkle Tree 的零知识证明为例。该 Merkle Tree 用于记录账户的地址和余额。当有新的交易需要更新 Merkle Tree 时，需要执行以下操作：

1. 验证交易的发送方和接收方是否在树的叶子节点上。

2. 验证发送方的签名。

3. 更新发送方和接收方的余额。

4. 更新 Merkle Tree 的根节点（即 Merkle Root），并将其作为最终输出。

在没有零知识证明的情况下，验证者需要重复这些步骤以确保计算的准确性。而使用零知识证明，则大有不同。

首先，需要确定私有输入和公开输入：

- 在上述过程中，只有新的交易信息、原 Merkle Root 和更新后的 Merkle Root 是公开输入。

- Merkle Tree 本身作为 witness（见证），不需要被验证者读取或处理。

其次，需要生成密钥和计算电路。我们将 Merkle Tree 的更新、输入输出地址的验证等计算过程构建成计算电路，以获得证明密钥和验证密钥。注意：该电路与输入的交易信息无关，也与现有的 Merkle Root 无关，因为 Merkle Tree 的计算方式是固定的。

在生成证明的阶段，我们将前后两个 Merkle Tree 和交易信息作为输入。在验证阶段，验证者可以在不获取 Merkle Tree 的情况下，仅凭输入来确保更新过程的可靠性。该电路就像一个稳固的黑盒，只要输入正确，就能得到正确的输出。

使用零知识证明，其他验证者可以快速验证 Merkle Tree 的生成过程是可信的，从而减少了网络上重复验证的时间，同时Merkle Tree的信息无需向验证者披露。

### 1.2 从ZK-SNARK到ZK-STARK

上述提到的证明协议是ZK-SNARK。“SNARK”代表“Succinct Non-interactive ARguments of Knowledge”，其中“Succinct”表示这种方式的简洁性，“Non-interactive”表示相对于其他证明方式，SNARK是非交互性质的证明，即验证者只需使用由证明者生成的证明即可获得验证结果。然而，ZK-SNARK存在一些问题。在密钥生成阶段，电路和随机数相当于一组初始的公共参数，这个公共参数的生成过程存在不可避免的中心化问题。

ZK-STARK在SNARK的基础上另辟蹊径，“STARK”代表“Scalable Transparent ARguments of Knowledge”，“Scalable”说明其具有可扩展性。在ZK-STARK中，证明生成时间与原始计算的耗时呈拟线性关系，而验证耗时与原始计算呈对数关系。这意味着在处理大量数据集的情况下，验证者所需的验证时间将大大缩短。

作为ZK-SNARK的升级版，ZK-STARK不仅提高了验证效率（理论效率为10倍），且不依赖椭圆曲线或可信设置，且无需生成初始公共参数的过程（即“Transparent”代表的透明性），从而消除了对可信设置的中心化需求。一些开发者认为，ZK-STARK中的哈希函数有助于抵御量子攻击。

然而，ZK-STARK的推出较晚，目前技术仍不够成熟，并且依赖哈希函数，这限制了其通用性。相比之下，ZK-SNARK仍是通用的证明算法。基于STARK的算法示例包括Fractal、SuperSonic等，而与之相关的项目方包括StarkWare、Polygon Miden等。

## 2 理解Rollup

除了零知识证明，我们还需要了解另一个概念，即Rollup。Rollup的意义在于解决底层网络的拥堵问题。

例如以太坊目前仍存在交易拥堵的问题。为了解决此问题，有两种方法可供选择：一种是增加区块链本身的交易处理能力，例如通过分片等技术扩展区块链的吞吐量。另一种方法是改变区块链的使用方式，即将大部分复杂计算由链上直接执行转移到在二层（Layer 2，简称L2）上执行，仅在底层链进行验证结算。在这种情况下，底层链上通常会部署一个智能合约负责处理存款和取款，并使用各种方法来读取链下数据，以保证链下的计算和执行符合规则。此方式可以形象地理解为在原有的小路上搭建高架桥，通过“二层”的扩展来解决拥堵问题。

当前，L2扩容主要有三种类型或方案，即状态通道（State Channel）、Plasma和Rollup。它们分别代表了三种不同的范式，各有其优点和缺点。所有L2扩容方案大致都可以归为这三个类别（尽管有些命名存在争议，例如Validium），其中Rollup具有一些独特的优势。

### 2.1 Rollup和数据可用性

相比于其他扩容方案，Rollup具有一定的优越性，其中一个比较直观的优势是解决了数据可用性的问题。

第二层扩展解决方案，例如Rollup，通过在链下处理交易来降低交易成本并提高以太坊的吞吐量。Rollup将大量的链下交易压缩成批次，并一次性发布到以太坊网络上。这样一来，基础层的拥堵问题得到缓解，用户也能够享受更低的手续费。

然而，要想信任发布到以太坊的“汇总”交易，我们需要能够独立验证并确认这些交易所引起的状态变更确实是执行所有链下交易而得出的结果。如果Rollup运营者不提供交易数据供验证，则可能向以太坊发送错误的数据。这就是数据可用性问题。

当前，Rollup方案将交易数据作为`calldata`永久存储在底层链上，而随着 Danksharding 的引入，区块中存放L2数据的空间将更大，并会使用临时的、成本更低的“blob”进行存储。但无论使用何种数据可用性方案，数据在链上这一点非常重要。需要注意的是，将数据存储在IPFS上是行不通的，因为IPFS并不提供共识层面的验证，无法保证给定数据是否可用。

在Plasma以及Channel这两种扩容方案中，数据和计算完全存放在L2网络中，当L2和以太坊进行交互时，L2链上的交易数据并不包含在内，从状态机视角来看，也就是没有包含L2链每一次状态变更的信息。这会导致以太坊如果脱离了Plasma等L2网络就无法复原之前状态变更的情况。如果恶意运营方在Plasma链上进行了无效转换，用户将不能对其发起挑战，底层链也无法独立验证并解决分歧，因为运营方可以扣留所需的数据。 Rollup通过迫使运营方在以太坊上发布交易数据来解决这个问题，使任何人都可以验证链的状态。

### 2.2 Rollup的机制

为了保证数据可用性，因此市场选择了Rollup，那么Rollup具体是如何工作的？

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/629e623fc30281c993b297c6_J00-_uw-59puy9rvPfUyjdx_O4IYTr-73mEEpUm5X15eOHL7SIcvHoaQx-yQBhq8o0PpbQ6O4d0s1EoqzGthuKVzFzJDjo1tDwAgEKDMfn_c5mBeBZsFNdmwXlA8Pg7ipZwmI_ZQxMDgcrbCWA.png"  />
_图4 L1合约中的State Root | 图源：https://vitalik.ca/general/2021/01/05/rollup.html_

在Rollup的设计中，主链上有一个Rollup合约，其中保存了一个状态根（state root）。可以把这个状态根看作是Merkle Tree的Merkle根的升级版，它存储了账户余额、合约代码等信息，图 4展现了Rollup合约中存储的状态根。

L2节点主要有三个功能：首先确定哪些交易应该优先被打包（通常该类节点或客户端被称为定序器Sequencer），其次需要对每个打包的数据给出证明，最后提交给L1上的Rollup contract由该合约进行验证。图 5展现了L2中定序器的作用。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/batch-1.png" style="zoom: 33%;" />
_图5 定序、证明和提交Batch是L2节点的主要功能_

具体而言，L2可以将一批数据（batch）传递给L1。这些数据可以是高度压缩的交易集合或合约运行后的状态变化。同时，这批数据还包括L1合约中存储的状态根（state root）以及经过L2处理后得到的新的后状态根（post-state root）。合约利用这些数据来验证新的后状态根的正确性。一旦验证通过，这批数据就会在L1层得到确认，完成了从L2到L1的上链过程。

为了确保提交的数据中的新后状态根是正确的，最直接的方法是让L1重新计算一次。然而，这种方法会给L1带来巨大的压力。为了解决这个关键问题，存在两种完全不同的优化方案，即Optimistic Rollup和ZK Rollup。

### 2.3 ZK Rollup和Optimistic Rollup

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/uTools_1689646341885.png" style="zoom: 67%;" />
_图6 Optimistic Rollup和ZK Rollup的对比_

图6展示了ZK Rollup和Optimistic Rollup运行机制的对比。

ZK Rollup采用有效性证明机制，通过诸如ZK-SNARK或ZK-STARK等加密协议来验证执行交易批次后状态根的正确性。无论L2中的计算量有多大，ZK Rollup都能够快速在L1上进行链上验证。

Optimistic Rollup使用欺诈证明的机制，在这种机制下，Rollup合约跟踪状态根的完整历史和每个批次的哈希值，合约会“乐观地”默认所有交易都是合法的，除非其被证明无效（无罪推定）。如果有验证者发现某个批次的后状态根不正确，他们可以发布一个错误性证明，证明该批次计算不正确。其他节点将一起验证该证明，并恢复该批次及其后续的所有批次。

图7总结了Optimistic Rollup和ZK Rollup的优劣势对比。值得注意的是，ZK Rollup在TPS（每秒交易处理量）方面表现出色，并且在提款周期方面具有显著优势。其劣势在于EVM兼容性和L2层的计算消耗：

1. Optimistic Rollup项目，如Optimism和Arbitrum，分别使用OVM和AVM，它们的虚拟环境与EVM基本相同，因此可以直接将L1层的合约迁移到L2上进行部署。然而，在ZK Rollup中，将ZK-SNARK用于证明通用的EVM执行是相当困难的，因为EVM并不是按照ZK证明计算的数学需求来开发的，所以需要对某一类的EVM客户端进行改造，以利用ZK技术来验证交易和合约运行。
2. 同时，即使经过相应的转化，ZK运算仍然需要大量的计算能力，因此在L2层的效率上ZK Rollup不及Optimistic Rollup。
3. ZK Rollup提供了比Optimistic Rollup更好的数据压缩功能，因此能够在L1上提交更小的数据。
4. 由于ZK中的证明验证过程更快捷，且具有更高的批处理密度，因此在L1层的计算消耗上ZK Rollup较低。可以理解为L2上的节点付出大大减轻了对L1节点的要求，从而显著提升了L1层的可扩展性。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/zkvsop.png" style="zoom: 50%;" />
_图7 两种Rollup方案的对比_

### 2.4 ZK Rollup 还是 zkEVM Rollup？

虽然ZK Rollup看起来很有吸引力，但在实际部署中存在诸多困难。目前，ZK Rollup仍然具有相当大的局限性，而Optimistic Rollup仍然是主流方案。大多数已实现的ZK Rollup也都是为某些特定应用程序定制的。

如何理解定制化的ZK Rollup？开发者为不同DApp构建专用电路（“ASIC”），如Loopring、StarkEx rollup和 zkSync 1.0，它们支持特定类型的支付、Token交换或者是NFT铸造，然而，它们的电路设计需要高度的技术知识，这导致了开发者体验的不佳。以特定类型的支付数据为例子，节点将交易数据提交给定序器，由定序器打包给提验证（proof）的节点作为公开的输入，证明过程和虚拟机上的合约执行过程无关，ZK只是负责将某个特定的执行结果的Rollup计算、压缩过程进行进行证明。

而zkEVM Rollup又代表了将虚拟机运行结果Rollup的能力。当在L2层运行通用的智能合约，需要证明合约运行前后状态转换的有效性时，便需要有一个虚拟环境能够支撑ZK算法的运行。因此，运行合约，输出最终状态，证明合约执行过程的有效性，并将交易记录，账户记录，状态变化记录数据一同rollup提交，这便是zkEVM的意义。而L1层只需要快速验证证明，开销较小，无需再次运行合约，图8说明了zkVM的作用。需要注意的是，zkEVM其实是运行在L2层的类EVM虚拟机，因此更为精确的说法是Zero Knowledge Virtual Machine，zkVM，只不过大家强调其兼容以太坊而称之为zkEVM。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/uTools_1689667759663.png" style="zoom:80%;" />
_图8 zkVM说明_

现有项目也在考虑逐渐放弃了为特定应用程序做优化，而升级转向支持运行通用合约即zkEVM Rollup。因此，zkEVM Rollup虽然作为ZK Rollup的下位概念，在大部分情况下，提起ZK Rollup时便指zkEVM rollup。

## 3 理解zkEVM

要理解zkEVM，首先需要对EVM（Ethereum Virtual Machine）的概念有一个基本的认知，才能更好地认识到当前zkEVM的局限性。

### 3.1 从EVM到zkEVM

在以太坊社区中关于EVM的经典表述：以太坊虚拟机由成千上万台运行着以太坊客户端、相互连接的计算机节点共同维护。以太坊协议的存在主要是为了保持这个独一无二的状态机连续、不间断、不可变地运行。EVM定义了如何在不断更迭的区块中定义标准的状态。它的行为类似于一个数学函数：给定一个旧的有效状态和一组新的有效交易T，EVM状态转换函数将生成一个新的有效状态。在这个图灵完备的状态机上，可以运行任何代码。

EVM按照一定的规则执行交易。首先，人类可读的编程语言（如Solidity和Move）将被编译为面向机器的16进制“低级”语言，称为EVM字节码（bytecode），最终按照操作码（Opcode）解析为顺序指令列表。

因此，zkEVM是一个至少在编程语言层面兼容EVM的zkVM。然而，EVM的设计存在一定的局限性，其中与本文最相关的是EVM无法与ZK相应协议兼容。因此需要对原有的EVM进行一定的改造，这种改造是相当具有挑战性的：

1. EVM对椭圆曲线的支持有限。
2. EVM基于256位整数运行，而零知识证明则“天然”基于素域运行。
3. EVM与传统虚拟机不同，具有许多特殊的操作码。
4. EVM是基于堆栈的虚拟机，而不是更高级别的零知识证明友好型中间表示（IR，Intermediate Representation，即计算机程序编译过程中源代码和目标代码之间的中间状态）。[1]

### 3.2 zkEVM兼容性：三种类型

在Vitalik的文章中对于改造程度和EVM兼容程度做了四个层面的划分，本文对其做更为明晰的理解。[2]

- 类型一：以太坊等效。zkEVM和EVM在共识层面兼容，这意味着在一定程度上，zkEVM可以完全融入L1作为等效的P2P节点进行协议通信，zkVM和EVM可以等效运行。在这种情况下，zkEVM可以在L1层面证明多个交易，加快其他节点对区块的验证。这意味着L1层本身具备扩容能力，无需建立围绕zkEVM的L2。这种类型的EVM效率非常低，仍处于“研究”阶段，并且大规模部署可被视为以太坊的升级。类似的情况还有另一种极端情况，即公链运行zkVM，L1证明本身数据而放弃以太坊原有架构，以减少生成证明的时间。

- 类型二：EVM等效。zkEVM和EVM在字节码层面兼容，但在共识层面不兼容，将大部分EVM操作码转化为电路。这种类型涵盖了目前项目范围最广的情况，根据Vitalik的博客，可细分为三种类型。这些类型在gas费用（满足ZK协议复杂操作的费用）、部分操作码兼容性、哈希函数类型、区块、交易树和状态树结构、证明时间等方面存在一定的差异。这些不同方面的不兼容性可能导致较高的证明/验证开销、较低的效率，或对开发者在合约部署和运行方面产生影响。然而，与类型一和类型三相比，类型二有着本质的区别。由于zkEVM项目目前正处于高速迭代阶段，技术细节的差异评估变得困难，因此笔者认为只需要关注项目之间的技术差异，而不必强求对类型的具体界定。

- 类型三：高级语言编译等效。这是最低层级的“兼容”方式，将流行的高级编程语言编译为ZK-SNARK友好的语言。在这种情况下，底层环境和虚拟机特性与EVM完全不同，最直接的体现是在字节码层面与EVM不兼容。开发者无法直接复制和修改EVM字节码，并且可能与以太坊技术支持脱节，缺乏一定的ERC标准，无法保持与EVM同步的安全性。

所谓兼容性，是在有限的ZK协议证明能力，网络协议设计难度，网络算力下，对运行效率、投入计算量和开发适配性的一个取舍。

- 运行效率针对链上用户而言，最为直观体现是交易速度，有关L1上验证者效率，L2上证明者效率，zkEVM硬件加速程度等；

- 投入计算量体现L1、L2层网络的gas费；

- 开发适配性从合约开发者角度，考虑合约兼容程度和基础设施通用性等，和特殊操作码、部分ERC协议是否适配等有关。

类型三的zkVM完全实现一个ZK友好型VM，在性能方面具有优势，但DApp开发者有相当高的迁移成本，同时无法同步以太坊的最新特性和安全性。而在类型二中，往往证明者证明速度（满足电路转化的要求）、计算量和基础设施通用程度（满足以太坊的要求）呈负相关。

### 3.3 当前ZK赛道梳理

围绕zkEVM的不同等效程度的优劣势，ZK赛道在以下几个方面逐渐兴起：

1. ZK以太坊兼容和电路编译：解决EVM兼容性的核心问题，是赛道焦点，各类其他生态项目均围绕其展开。
2. ZK公链，如Manta Network等：放弃Ethereum，建立新的zkVM，注重L1层的扩容问题，同时关注数据隐私问题。
3. ZK跨链桥和预言机：作为ZK赛道的基础设施，用于在多个zkEVM Rollup的L2之间进行资产迁移或获取链下数据。
4. ZK硬件加速：作为ZK赛道的基础设施，解决生存证明计算量大的问题。目前主要依赖GPU进行加速，预计在2023年年底之后，将出现支持zkEVM证明的专用硬件（ASIC），以及相对成熟可用的产品。
5. ZK工具类：根据兼容程度提供不同的开发工具，以支持不同类型的ZK应用。
6. ZK应用：虽然与本文关联较小，但更多关注于ZK隐私性的优势，探索在各个领域中应用ZK技术的潜力。

## 4 zkEVM Rollup项目概览

在关注2023年上半年涌现的各类zkEVM项目时，以下几个方面是关注重点：

1. 项目进展：关注项目的当前阶段，测试网和主网的预计上线时间，以及与其发展路线图的一致性。
2. 实际交互情况：通过与测试网或主网的交互，获取网络的TPS（每秒交易数）以及单笔交易确认时间等指标，以对网络性能有直观的了解。
3. zkEVM兼容性：这是最核心且最具挑战性的技术点，需要关注项目中的ZK协议、VM安全性和兼容程度等方面的表现，尤其是对于开源的项目，深入研究其VM层面的技术细节。
4. zkEVM Rollup架构：大多数项目都会公开其Rollup架构，关注其整体的去中心化程度，尽管这些项目在总体上相似，但也需要关注细微的差异。
5. 生态运营：考察项目的用户数量、活跃程度，链上应用生态的运营和孵化情况，以及开发者社区的维护等软性指标，以了解项目的运营状况。
6. 投融资情况：关注项目的融资状况和投资者的参与情况。

本文将主要聚焦在前四个方面，着重从技术角度对zkEVM Rollup项目的整体架构进行评估和考量。

### 4.1 Scroll

Scroll团队成立于2021年，专注于开发EVM等效的ZK Rollup以扩展以太坊。在过去的两年中，Scroll与Privacy and Scaling Explorations团队以及其他开源贡献者合作，共同努力构建与字节码兼容的zkEVM。在2月底，Scroll宣布他们的Alpha测试网已在Goerli上线，任何用户都可以参与技术测试，无需许可。测试网的平均出块时间为3秒，已经处理了超过2千万笔交易、150多万个区块和400万多个交互地址。同时，Scroll于4月11日推出了网站生态系统界面。

根据最近的信息披露，Scroll在实现类型二EVM等效的目标上取得了持续进展。他们已经完成了所有EVM操作码的兼容开发工作，并正在进行审计。下一个目标是兼容EIP2718交易。

从技术架构上看，Scroll的架构相对传统，这里将进行详细介绍。如图9所示，主要分为两个部分：核心部分是zkEVM，用于证明在L2上执行的EVM的正确性；但要将zkEVM变成完整的以太坊ZK Rollup，还需要构建一个完整的L2架构。目前的Scroll Alpha测试网络由Scroll Node、Bridge Contract和Rollup Contract组成。[3]

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/oLlyhIx.png" style="zoom:80%;" />
_图9 Scroll rollup整体架构 | 图源：https://scroll.io/blog/architecture_

1. Scroll Node：由Sequencer、Relayer和Coordinator组成。
   - Sequencer，即定序器，向用户和应用开放JSON-RPC，读取交易池中的交易并生成L2的区块和状态根。目前的Scroll定序器节点是中心化的，但在未来的升级中将逐渐实现去中心化。
   - Coordinator，负责在Roller和Scroll Node之间进行通信。当Sequencer生成新的区块时，Coordinator会在池中随机选择一个Roller进行证明生成。
   - Relayer，监测以太坊和Scroll链上的Bridge Contract和Rollup Contract。Rollup Contract保证L2数据在L1层面的数据可用性，确保在L1层可以恢复L2区块，L2层提交的区块经过L1层上Rollup Contract的有效性验证，该区块在L2才成为不可更改的最终状态。Bridge Contract在跨链时负责双链合约之间的通信，可实现双向消息传递，以及跨链资产的质押和提取操作。

<img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/Sajm1E2.png" style="zoom:80%;" />
_图10 Roller Network | 图源：https://scroll.io/blog/architecture_

2. Roller Network：Roller内置zkEVM，在网络中充当证明者，负责为ZK Rollup生成有效性证明，见图10。
   - Roller首先从Coordinator接收execution trace（即合约执行的具体操作和涉及的地址），然后将其转换为电路的witnesses（证明所需的信息）。
   - Roller为每个zkEVM电路生成证明，并最终聚合来自多个zkEVM电路的证明。

### 4.2 StarkWare

StarkWare是一家提供基于STARK的扩展解决方案的公司，旨在确保L2具备安全性、快速性和无缝用户体验。StarkWare支持多种数据可用性模式，并通过StarkNet作为其L2网络，以及StarkEx作为面向企业用户的Rollup验证服务，让DApp可以构建在StarkEx服务之上。然而，目前的实现仍然是针对特定DApp进行定制化的电路编写，而不是通用的zkEVM Rollup。StarkEx支持各种即插即用的服务，例如NFT铸造和交易、衍生品交易等。在生态方面，去中心化期货合约交易平台DYDX是StarkWare的忠实用户。

StarkNet本质上是zkVM，没有针对以太坊操作码进行ZK电路的设计，而是采用了一套更加ZK友好的汇编语言、AIR（代数中间表示）和高级语言Cairo。尽管StarkNet本身不兼容EVM，但可以通过其他方式（如Kakarot）与以太坊进行兼容。需要注意的是，StarkNet相对来说还是一个中心化的项目，无法与以太坊的安全性升级同步，因此需要集中的研发人员来弥补安全性方面的不足，并开发适配以太坊新协议。

StarkNet采用STARK作为其证明系统，相对于SNARK，STARK具有更多的创新。它不需要依赖“可信设置”，并且具有更简化的密码学假设，避免了对椭圆曲线、配对和指数知识的需求，仅依赖哈希和信息论，从而更具抗量子攻击能力。总体而言，STARK比SNARK更安全。在可扩展性方面，STARK具有显著的边际效应，证明规模越大，总体成本越低。

然而，在架构方面，目前系统中只有一个Sequencer（定序器），由StarkWare控制，并且只有一个Prover（生成ZK Proof的证明者），不仅为StarkNet生成证明，还为运行在StarkEx Rollup上的其他所有应用程序生成证明。

### 4.3 Validium和Volition

Validium是一种L2级别的扩展解决方案，类似于ZK Rollup，它利用计算证明（如ZK Rollup）来确保交易过程的完整性。然而，与ZK Rollup不同的是，Validium并不在以太坊主网上存储交易数据。虽然这种权衡会导致链上数据可用性的牺牲，但也带来了巨大的可扩展性改进，使Validium每秒可以处理约9000笔交易。

尽管Validium在处理交易效率上表现出色，但在笔者看来，它并不能被严格视为ZK Rollup。这个方案和Plasma类似，都没有实现L1层的数据可用性，因此也无法称为真正的Rollup。不过，Validium与Plasma的区别在于其采用了类似于OP Rollup的“七天退出机制”，而利用了ZK技术来缩短L2层对数据的验证时间，并避免将数据同步到L1层。

StarkWare率先推出了名为Volition的方案，使用户能够轻松在ZK Rollup和Validium之间切换。例如，对于一些应用程序，如去中心化衍生品交易所，可能更适合采用Validium，同时仍希望与ZK Rollup上的应用程序进行互操作，这时Volition提供了这种可切换性。这使得用户可以根据自己的需求和优势选择最适合的方案。

### 4.4 zkSync

与StarkNet类似，zkSync始终坚持选择上文提到的高级语言等效的zkVM，并且备受关注，其在市场上拥有相当高的热度和用户锁仓量。zkSync 1.0（zkSync Lite）于2020年6月15日在以太坊主网上启动，实现了约300 TPS的交易吞吐量，但不兼容EVM。而zkSync 2.0（zkSync Era）于2023年3月24日启动。

zkSync Era的目标是通过使用他们自定义的虚拟机（VM）进行优化，而不是追求EVM等效性，以实现更快的证明生成。它通过强大的LLVM编译器支持Solidity、Vyper、Yul和Zinc（rollup的内部编程语言），以此来实现大部分智能合约功能。由于采用了自研的虚拟机，zkSync Era支持原生账号抽象，使得任何账户都可以使用任何代币支付费用。

此外，通过应用zkPorter协议，结合ZK Rollups和分片技术，zkSync网络的吞吐量得到了指数级的增长，达到了20,000+ TPS（类似于Volition中的数据可用性切换）。

总体而言，zkSync是一个生态丰富的L2项目，备受开发者和投资者的关注。但目前仍存在一个问题，即开发者能否在高级语言等效的zkVM上获得良好的开发和迁移体验。目前仍然缺乏开发者角度的使用报告，如果开发者能够有良好的体验，那么其他类型努力兼容EVM的zkVM又有何意义呢？在这方面还需要更多时间来观察和评估。

### 4.5 Polygon zkEVM

Polygon于3月27日启动了zkEVM Rollup主网络的Beta版，该网络是以太坊等效的虚拟机，并开源了所有zkEVM代码。与zkSync相比，Polygon zkEVM的锁仓量较小，但生态系统中仍存在有趣且活跃的项目。

在Rollup的设计方面，Polygon与Scroll有所不同，他们采用了效率证明（PoE）模型来激励排序器（Sequencer）和聚合器（Aggregator），以应对去中心化和无许可验证器的挑战。在无需许可的排序器-聚合器两步模型中，任何排序器都可以申请打包批次并获得打包费用，但需要支付L1层的Gas费用并存入一定数量的代币；同时，聚合器需要设定自己的目标，以最大化每次证明生成的利润。此外，Polygon还与Volition（ZK Rollup和Validium）模式具有深度兼容的数据可用性模型，以为用户提供不同层次的服务。[4]

此外，Polygon在ZK协议方面也投入了相当的工作量，并取得了显著的成果。在他们的文档中，他们总结了自己的技术优势，主要包括以下几点：

1. 更高的兼容性：Polygon始终坚持采用EVM等效的zkVM，以降低开发者迁移dApp的成本。同时，尽管Polygon Miden采用了ZK-STARK协议，但仍支持运行Solidity合约。
2. 更容易的验证：ZK Rollup经常受到批评，因为生成有效性证明需要昂贵的专用硬件，而这些硬件的运营成本转嫁给了用户。Polygon ZK Rollup（如Polygon Zero）旨在简化证明方案，使得更低级别的设备可以参与其中，例如，在消费级PC上进行的Plonky2证明生成测试。
3. 更快的证明生成和验证过程：Polygon Zero可以在170毫秒内生成一个45kb的证明。[5]

## 5 理论与现实

本份研报主要介绍了ZK技术和Rollup机制，并着重强调了数据可用性的重要性。在区分ZK和zkEVM Rollup的问题上，对两者进行了界定。此外，详细梳理了zkEVM的三种类型以及相关的ZK赛道。最后，结合几个优势项目，回顾了其技术框架和现有生态。

在具体项目方面，高级语言等效EVM虽然在理论研究中有很大的局限性，却占据了当前的主流地位，StarkWare这类中心化较为严重的产品也博得了市场的青睐。相较之下，zkEVM的“通用性”似乎成为了一种累赘，我们无法分辨出“高效拓展”突破了哪些问题并实现了超越理论的效果。当然，很多参与者、投资人实际上并不关心项目背后的技术特点，这似乎不太Web3，却又很Web3。

Rollup技术的目的是进一步挖掘区块链的价值，但往往因为迫切需要成为市场上的“创新性概念”，而产生“开倒车”的现象，回归到中心化。这是当前市场存在的问题。

区块链的价值很容易被看到，谁不想要一台永恒的计算机呢？但核心问题是，当这台计算机的运行能力远远低于我们身边任何一台服务器，并需要大量资源投入，甚至使用价值远低于投入成本，那么作为一个“公共产品”，它还能吸引更多人加入使用吗？

当我们已经拥有了相当多国家、社会甚至个人的产品时，在什么情况下，我们愿意忽视高昂的使用成本，追求“永远在线，永远正确”的结果呢？我认为这是当今区块链行业需要思考的问题。Rollup技术在技术上可以改善这个问题，但还有一大部分问题需要留给浮躁的市场去解决。





**参考**：

[1] [zkEVM - HackMD](https://hackmd.io/@yezhang/S1_KMMbGt)

[2] [The different types of ZK-EVMs (vitalik.ca)](https://vitalik.ca/general/2022/08/04/zkevm.html)

[3] [Scroll’s Architecture Overview - Scroll](https://scroll.io/blog/architecture)

[4] [Polygon zkEVM Documentation - Hermez 1.0 Documentation](https://docs.hermez.io/zkEVM/Overview/Overview/)

[5] [Polygon ZK Rollups: Everything You Need to Know (alchemy.com)](https://www.alchemy.com/overviews/polygon-zk-rollups)