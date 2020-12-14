# English Site

Please update contents according to [repo-structure.md](../repo-structure.md)

Please finish the contents of English first before add contents for other languages


## Architecture

- [API](api/README.md)
  - main api
  - XChain api
- monitor (deposit)
- secure vault
  - collection
  - payout
- core (validator)

## Monitor

每个链均有各自的检测程序，检测程序会基于币种信息来检测系统内对应地址的收款情况。


## Secure Vault

### Collection

资金归并程序，每个链均有各自的归并程序；

- 归并方式
  - native
    针对类似 ETH/NEW 的资金，直接转账到离线钱包
  - burnable
    针对可销毁的token，采用burn来销毁token，不进行归并，一般针对跨链后的币种
  - transfer
    一般token采用transfer到离线钱包

### Payout

每个链均有一个支出程序，给用户兑付相应的token

- native
  原生coin采用普通转账方式，由 MainAddress 统一转出
- mintable
  针对可铸币的token，由 MainAddress 调用mint函数进行铸币
- transfer
  针对普通token，由 MainAddress 从自己地址转出token到目标地址

### 费用管理

- GasPrice
  GasPrice采用链上实时GasPrice值，调用链的 eth_gasPrice 方法
- GasLimit
  - 针对普通转账，强制采用 90000 ，避免目标地址为合约地址导致转账失败的情况
  - 针对token转账，强制使用 100000， 避免合约内部逻辑复杂导致token转账失败

## core (validator)

NewBridge Core用来协调各条区块链程序的用户充值、手续费、兑付等程序；

### 架构

- 输入
  - 用户充值地址
  - 系统内收币地址
  - 金额
- 输出
  - 用户收币地址
  - 金额













