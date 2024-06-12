# [Wenbo]

[Hello，my name is Wenbo and I'm a undergraduate student who loves BlockChain and Deeplearning. I'm looking forward to learning about the Ethereum Protocol by attending intensive-study-group.ヾ(≧▽≦*)o]

## Notes
### 2024.4.14
1. 了解了 EIP-4844（thanks to derick）
    1. 引入「blob」数据块 本质上是大数据包，可以比当前以太坊使用的 calldata 更有效地处理和存储数据。这些 blob 可以存储大量信息，例如去中心化交易所的订单簿数据。
区块链验证的权衡：验证器节点（以前称为矿工）仍然需要完全验证交易本身，但他们可以選擇不下载和验证相关联的 blob 数据。这降低了运行以太坊节点所需的计算量和存储空间。
Rollup 是以太坊扩展解决方案的重要组成部分，它们将交易数据存储在链下，以降低成本并提高吞吐量。EIP-4844 将允许 rollup 使用这些 blob 来存储交易数据，而无需将其包含在主网上需要支付 gas 费用的每一笔交易中。
数据有效期有限：EIP-4844 规定了 blob 数据的有效期。这些数据块仅在共识层上存储有限的时间（通常约 18 天），然后将被删除。
    2. EIP-4844 如何降低 gas 费用？
它提出了一种新的交易类型，称为「blob携带交易 (blob-carrying transactions)」。这种交易类似于附加在以太坊交易上的「sidecar」，可以包含额外的信息块。这些 blob 的体积很大（最大可达 128 KB），但与当前的 calldata 相比费用更低。通过将这些 blob 临时存储在以太坊的共识层上，EIP-4844 旨在显着降低 rollup 向以太坊主网传输数据的成本，从而实现降低交易费用。
**为分片扩展奠定基础**：EIP-4844 的设计与以太坊未来的分片扩展路线图兼容。分片是一种将区块链数据分布到多个分片中的方法，可以显着提高可扩展性。EIP-4844 引入了分片所需的一些技术要素，例如 blob 和分离的交易数据。
    3. EIP-4844 的潜在影响
EIP-4844 可以降低 Layer 2 rollup 解决方案的交易费用为以太坊未来更复杂的扩容方案（例如完整分片）奠定基础
### 2024.4.13
1. 继续学习 Stateless Ethereum
[Accessing Ethereum  访问以太坊](https://inevitableeth.com/home/ethereum/network/node/accessing-ethereum)
  > Think like this: 像这样思考：Consensus client: responsible for Proof of Stake (PoS), securing Ethereum with the value of $ETH共识客户端：负责权益证明（PoS），以 $ETH 的价值保护以太坊
Execution client: responsible for operating the computing platform of the World Computer (the EVM).执行客户端：负责运行世界计算机（EVM）的计算平台。
These clients are HEAVY DUTY pieces of software.这些客户端是重型软件。

### 2024.4.11
1. 快速过了：[Ethereum: The World Computer--以太坊：世界计算机](https://inevitableeth.com/en/home/ethereum/world-computer)，概论来的老东西
> Light Clients 轻客户端:Light clients are pieces of software that can directly, trustlessly access Ethereum without running a full Ethereum node.轻客户端是可以直接、无需信任地访问以太坊而无需运行完整以太坊节点的软件。Before we can support light clients, we first need to upgrade Ethereum to be stateless.在支持轻客户端之前，我们首先需要将以太坊升级为无状态。

> Statelessness  无国籍状态:Deep Dive: The Road to Stateless Ethereum深入探讨：通往无状态以太坊之路
Statelessness is a nuanced topic worth reading more about, but the idea can be summarized as "using cryptography to trustlessly access the EVM without having to store it locally."
无状态性是一个值得深入了解的微妙主题，但这个想法可以概括为“使用加密技术以无需信任的方式访问 EVM，而无需将其存储在本地”. But statelessness is not enough to support light clients - the EVM is not the only component of the World Computer. 但无状态性不足以支持轻客户端——EVM 并不是世界计算机的唯一组件。
> ![image](https://github.com/brucexu-eth/intensive-ethereum-protocol-study-group/assets/78262508/1fa7eeba-200b-4d19-b1ac-ce179b70f6da)

诶，第一次听，感觉挺有前景

### 2024.4.9
1. 在看：https://summerofprotocols.com/research/sop2024
  2. > To claim that the built environment is full of infrastructurally constrained coordination problems is another way of saying that cities have protocol problems. If protocols are coordination mechanisms supported by infrastructure, then cities are dense clusters of overlapping protocols—organizing processes that channel or filter physically grounded behavior in the pursuit of some overarching goal, such as traffic flow, public space usage, or the allocation of housing.
声称建筑环境充满基础设施限制的协调问题是城市存在协议问题的另一种说法。如果协议是基础设施支持的协调机制，那么城市就是密集的重叠协议集群——组织流程，引导或过滤物理基础行为，以追求某些总体目标，例如交通流量、公共空间使用或住房分配。
In his 1996 paean to the urban street grid, Ladders, Albert Pope argues that the widespread expansion of the grid in the 19th century “reconceived the city as an active process rather than a discrete urban plan.”9 As this has become even more true in the time since, the role of protocols in the built environment has grown accordingly.
阿尔伯特·波普 (Albert Pope) 在 1996 年对城市街道网格的赞歌《阶梯》中指出，19 世纪网格的广泛扩张“将城市重新视为一个活跃的过程，而不是一个离散的城市规划”。 9 从那时起，这一点变得更加正确，协议在建筑环境中的作用也相应增强。


### 2024.4.8
1. 快速过了：inevitableeth.com/en/home/background 和 inevitableeth.com/en/home/background/mass-comm, ![y](印刷技术传播图tps://github.com/brucexu-eth/intensive-ethereum-protocol-study-group/assets/78262508/4369768c-2735-4d2c-a6ce-12f205cad48c) 让我想起之前的分析说奥斯曼帝国对印刷术的各种严厉限制措施是中亚识字率甚至低于大清的主要原因。
2. 看了：inevitableeth.com/home/ethereum/upgrades/scaling/data
> Our primary goal: credible neutrality through decentralization. If we lose $ETH decentralization, we lose everything.

> PBS gives us the ability to propose our blobs, but we still need to address our biggest problem: how can we achieve 100% data availability without forcing any nodes to download 100% of the data?PBS 使我们能够提出 blob，但我们仍然需要解决最大的问题：如何在不强制任何节点下载 100% 数据的情况下实现 100% 数据可用性？
Well, we'll just distribute it across the P2P network!好吧，我们将通过 P2P 网络分发它！
Here's what's important: each node will download just a small data sample from each blob. No single node will be required hold an entire blob, just tiny fractions. These tiny fractions will be efficiently distributed across the network to ensure that it is always available.重要的是：每个节点只会从每个 blob 下载一个小数据样本。不需要单个节点保存整个 blob，只需要保存很小的部分。这些微小的部分将有效地分布在网络上，以确保它始终可用。
Upon request, the network will be able to quickly/efficiently reconstruct a blob. 根据请求，网络将能够快速/高效地重建 blob。

BT用户就很熟悉了。。。
想起来之前看的 telegra.ph/白话解读区块链不可能三角的变革性解决方案-03-17，感觉讲的更深入浅出一点，但现在结合来看又有新收获


### 2024.4.6
1. As hinted above, the main high level components of Ethereum are execution and consensus layer. These are 2 networks which are connected and dependent on each other.
如上所述，以太坊的主要高级组件是执行层和共识层。这是两个相互连接且相互依赖的网络。
2. Execution layer provides the execution engine, handles user transaction and all state (address, contract data) while consensus implements the proof-of-stake mechanism ensuring security and fault tolerance.
执行层提供执行引擎，处理用户交易和所有状态（地址、合约数据），而共识则实现权益证明机制，确保安全性和容错性。
3. The coordination mainly happens via regular calls which are scheduled in the PM repo. There are different kinds of developer calls with the biggest one being All Core Devs (ACD). This is where representatives of all involved teams come to discuss the current development of the consensus or execution layer.协调主要通过 PM 存储库中安排的定期调用进行。开发人员电话会议有多种类型，其中最大的一种是所有核心开发人员电话会议 (ACD)。所有相关团队的代表都在这里讨论共识层或执行层的当前发展。
4. Tried https://ethereum.org/zh/quizzes/, interesting :)

### 2024.4.5

> The Free Software movement is fundamental to Ethereum and all cryptocurrencies. The open, independent and collaborative development culture of Ethereum is strongly rooted in FOSS (Free and Open Source Software). Ethereum needs to be transparently implemented in software that gives full freedom to its users.

~~Pending....~~ Busy🥲

### 2024.4.4

Start
