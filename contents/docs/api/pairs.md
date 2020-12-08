---
title: Pairs Info API
description: "lookup pairs"
author: "Vie Yang"
---

# `GET` Pairs Info

**`GET` /v1/newbridge/pairs

返回account的账户基本信息

## API parameters

### 请求参数

- 无


```bash
curl -v https://replace-api-domain.ext/newbridge/pairs
```

## 返回参数

```json
{
    "pairs":[
        {
            "newchain_asset":{
                "address":"NEW17zFMb1iNPuFKbgW3ZPEJ3iLZrWvRjYmxCzG",
                "raw_address":"0x20F12218281F9CA566B5c41F17c6c19050125cD3",
                "name":"NewUSDT",
                "symbol":"NUSDT",
                "decimals":6,
                "asset_type":"NRC6",
                "chain_id":"1007",
                "sub_network":"Testnet"
            },
            "ethereum_asset":{
                "address":"0x0f3229fEEEB7e96493482b70DF3024822F01AA01",
                "raw_address":"0x0f3229fEEEB7e96493482b70DF3024822F01AA01",
                "name":"Tether USD",
                "symbol":"USDT",
                "decimals":6,
                "asset_type":"ERC20",
                "chain_id":"4",
                "sub_network":"Rinkeby"
            },
            "new2eth_min_deposit_amount":"10",
            "eth2new_min_deposit_amount":"1",
            "new2eth_fee_percent":"0.000000",
            "eth2new_fee_percent":"0.000000",
            "new2eth_fee_min_amount":"1",
            "eth2new_fee_min_amount":"0"
        }
    ]
}
```

| 名称                 | 类型          | 描述                                                         |
| -------------------- | ------------- | ------------------------------------------------------------ |
| newchain_asset | Token  | 交接对中newchain资产 |
| ethereum_asset | Token | 桥接对中ethereum的资产 |
| new2eth_min_deposit_amount | string        | `new2eth`方向最小充值金额 |
| eth2new_min_deposit_amount | string | `eth2new`方向最小充值金额                     |
| new2eth_fee_percent | string | `new2eth`方向手续费的百分比。实际手续费为 `new2eth_fee_percent` 和 `new2eth_fee_min_amount`计算后得到的最大值。 |
| eth2new_fee_percent | string | `eth2new`方向手续费的百分比。实际手续费为 `eth2new_fee_percent` 和 `eth2new_fee_min_amount` 计算后得到的最大值。 |
| new2eth_fee_min_amount | string | `new2eth`方向手续费最小值 |
| eth2new_fee_min_amount | string | `eth2new`方向手续费的最小值 |



其中， Token 类型定义如下：

| 名称        | 类型   | 描述                                                         |
| ----------- | ------ | ------------------------------------------------------------ |
| address     | string | 合约地址。ethereum里0x格式，newchain里NEW开头格式。如果为原生币（ETH/NEW），则为空。 |
| raw_address | string | 合约地址原生格式，0x格式                                     |
| name        | string | token的名称                                                  |
| symbol      | string | token的符号                                                  |
| decimals    | uint8  | token的精度，一般取值范围为 [0,18]。两个链上的精度必须一致。 |
| asset_type  | string | 资产类型，newchain链取值为 ： `Coin`,`ERC6`, ethreum链取值为 `Coin`,`ERC20` |
| chain_id    | int    | 链的ChainID                                                  |
| sub_network | string | 链的子名称，newchain链可取值有： `Mainnet`,`Testnet,`ethereum链可取值为：`Mainnet`,`Rinkeby` |



### Error Codes

| **Status** | **Code**                     | **Description**                              | **Params**                                                   |
| ---------- | ---------------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| **400**    | account_not_found            | Acount was not found                         |                                                              |
| **400**    | address_is_in_invalid_format | Requested address format is not valid        | { "type" => "newchain_address" } or  { "type" => "ethereum_address" } |
| **429**    | too_many_requests            | Too many requests have been made to the api. |                                                              |
| **500**    | internal_server_error        | Internal server error                        |                                                              |
| **503**    | service_unavailable          | Service is temporary unavailable             |                                                              |