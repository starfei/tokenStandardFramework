区块链代币的标准框架

本文介绍了一个旨在基于<底层源代码及其技术实现>评估区块链代币的基本框架。第一节解释了框架及其标准集。第二部分将此框架应用于一组现有的区块链代币系统。

## 1. 框架定义
本小节讨论并介绍了一个多标准框架，该框架基于底层源代码及其技术实现来分析和区分代币。

### (1) 区块链和网络层级

第一个标准是指代币发行的区块链系统。例如，USD Coin（USDC）是一种资产，仅在以太坊区块链上运行。

相反，一些资产存在于多个区块链上。美元稳定币Tether在四个不同的网络上运行：比特币（通过Omni层）、EOS、以太坊和Tron。类似地，Binance GBP 稳定币（BGBP）运行在以太坊和Binance链上。

此外，代币可以在第一层和第二层网络上发行。

代币发行在第一层的例子包括USDC（在以太坊上）或BTT（在tron上），而发行在第二层的代币包括USDH（基于简单分类协议上，在比特币现金上运行）和USDT（基于omni层，在比特币上构建）。

### (2) 所有权模式：基于UTXO或基于账户模型

第二个标准涉及代币的所有权。

以太坊或NEO等许多区块链都使用基于「账户」的模式。代币所有权通过每个地址的余额来表示。

比特币、Plasma则使用utxo（未花费输出）模型。上一笔交易的输出会作为下一笔交易的输入。

### (3) 原生或构造

「原生标准」指该区块链支持在其链上创建特定的代币，使用BEP-2标准的Binance Chain是个很好的例子。例如，从代码的角度来看，在Binance Chain上构建的代币都是以原生（基于BEP-2标准）的方式运行的。

因此，BNB（binance-chain native token）与根据BEP-2标准（例如MITH）发布的其他代币类似，都在Binance链上原生运行。

「构造标准」是指该区块链的代币基于智能合约部署运行。以太坊的ERC-20和tron的TRC-20是两个较为熟知的「构造标准」。例如，ERC-20代币不是原生运行在区块链上，而是运行在虚拟机（例如以太坊虚拟机）上的。

### (4) 同质化状态

另一个关键的标准是代币的同质化状态。代币分为同质化、非同质化和部分同质化代币。

同质化代币是指其值相同且彼此间无不同特征的代币。简而言之，同质化代币是可互换的。

非同质化代币（nft）是一种特殊类型的令牌，它表示一些独特的东西（例如，一个cryptokitty）。因此，NFT（即使来自同一类型）是不可互换的。

部分同质化代币是一种所有权可划分为不同分区，分区包含同质的和非同质形式的代币。例如证券型代币，其中非同质化的分区可能具有特定契约（例如，授予代币所有者特定的归属期限）。

### (5) 转让和所有权限制

从代码的角度来看，实用型代币和证券型代币之间的主要区别在于是否对转让和所有权有限制。

突出的例子包括以太坊的ERC-1400标准集，它可以通过对如两个地址之间的限制性转让或地址黑名单来施加限制。另一方面，绝大多数ERC-20代币不包含所有权或转让限制。

### (6) 稀缺性：可铸造或存在最大发行量

代币可以是固定供应，也可以随时间变化供应。智能合约中可以包含不同的功能（原生），例如允许在未来更改供应的销毁和铸币功能。
此外，还有一个区别，即哪个地址可以有效地调用这些“供应变化函数”。这些功能可以由单个地址（“中心调用模型”）或多个地址（“开放调用模型”）执行。

### (7) 可分割性和精度

有一些关于代币是否可分割以及最大精度的标准。
一些同质化的代币是不可分割的，另外一些则允许特定精度的代币分割，如小数点后18位。另一方面，非同质化代币（NFT）本质上是不可分割的，因为每个代币都是独一无二的。

### (8) 隐私功能
该标准是指令牌是否可以进行隐私转账。一些隐私功能是基于区块链本身的（例如，Dusk网络），另外一些是通过二层网络实现的。

### (9) 治理和其他功能

最后还有一个因素，涉及代币智能合约中是否构建了其他函数。一些代币具有投票权或治理功能。例如，Maker（MKR）持有人可以参与链上治理过程，为CDP设定稳定费用（[债务抵押头寸]（https://cdp.makerdao.com/help/what-is-a-collateralized-debt-position-cdp））。

## 2. 案例参考

在这一部分中将随机选择六个代币，并通过Binance的代币框架（前面已经定义）进行分析。

### 2.1 Basic Attention Token (BAT)

-   Blockchain(s): [Ethereum](https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef)

-   Account-based
    
-   ERC-20 - Constructed Standard
    
-   Fungible Token
    
-   Utility purpose with no transfer/ownership restriction
    
-   Fixed Maximum Supply: 1,500,000,000 units
    
-   Divisibility: Yes, 18 decimals

-   Privacy: No
    
-   Additional functions: Yes ([https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef#readContract](https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef#readContract))
    

### 2.2 Enjin Coin (ENJ)

-   Blockchain(s): [Ethereum](https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c)

-   Account-based

-   ERC-20 - Constructed Standard
    
-   Fungible Token
    
-   Utility purpose with no transfer/ownership restriction
    
-   Fixed Maximum Supply: 1,000,000,000 units
    
-   Divisibility: Yes, 18 decimals

-   Privacy: No
    
-   Additional functions: Yes ([https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c#readContract](https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c#readContract))
    

### 2.3 Binance GBP Stablecoin (BGBP)

-   Blockchain(s): [Ethereum](https://etherscan.io/address/0xc9a2c4868f0f96faaa739b59934dc9cb304112ec#code), [Binance Chain](https://explorer.binance.org/asset/BGBP-CF3)
    
-   ERC-20 - Constructed Standard / BEP-2 - Native Standard

-   Account-based
    
-   Fungible Token
    
-   Transfer and ownership restriction with the possibility to freeze funds (Ethereum token).
    
-   Fixed Maximum Supply: No. Minting/Burning functions.
    
-   Divisibility: Yes, 18 decimals (Ethereum). 8 decimals (Binance Chain)

-   Privacy: No
    
-   Additional functions: No
    

### 2.4 BitTorrent (BTT)

-   Blockchain(s): [Tron](https://tronscan.org/#/token/1002000)

-   Account-based
    
-   TRC-10 - Native Standard
    
-   Fungible Token
    
-   No transfer/ownership restriction
    
-   Fixed Maximum Supply: 990,000,000,000 units
    
-   Divisibility: Yes. 6 decimals.

-   Privacy: No
    
-   Additional functions: No
    

### 2.5 Mithril (MITH)

-   Blockchain(s): [Binance Chain](https://explorer.binance.org/asset/MITH-C76)

-   Account-based

-   BEP-2 - Native Standard
    
-   Fungible token
    
-   No transfer/ownership restriction
    
-   Fixed Maximum Supply: Yes. 994,903,806 units
    
-   Divisibility: Yes. 8 decimals.

-   Privacy: No
    
-   Additional functions: No
    

### 2.6 CryptoKitty (#4334)

-   Blockchain: [Ethereum](https://etherscan.io/token/0x06012c8cf97bead5deae237070f9587f8e7a266d?a=4334#inventory)

-   Account-based 
    
-   ERC-721 - Constructed Standard
    
-   Non-fungible token
    
-   No transfer/ownership restriction
    
-   Fixed Maximum Supply: N/A
    
-   Divisibility: No

-   Privacy: No
    
-   Additional functions: No
 

  

