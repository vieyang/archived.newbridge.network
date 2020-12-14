---
title: Pairs Info API
description: "lookup pairs"
author: "Vie Yang"
---

# Pairs Info API

## `GET` Pairs Info

**`GET` /v1/newbridge/pairs**

Returns a JSON structure with details of the NewBridge supported blockchain network and assets info.

## API parameters

```bash
curl -v https://replace-api-domain.ext/newbridge/pairs
```

## Response `200`

```json
{
  "pairs": [
    {
      "newchain_asset": {
        "address": "NEW17zFMb1iNPuFKbgW3ZPEJ3iLZrWvRjYmxCzG",
        "raw_address": "0x20F12218281F9CA566B5c41F17c6c19050125cD3",
        "name": "NewUSDT",
        "symbol": "NUSDT",
        "decimals": 6,
        "asset_type": "NRC6",
        "chain_id": "1007",
        "sub_network": "Testnet"
      },
      "ethereum_asset": {
        "address": "0x0f3229fEEEB7e96493482b70DF3024822F01AA01",
        "raw_address": "0x0f3229fEEEB7e96493482b70DF3024822F01AA01",
        "name": "Tether USD",
        "symbol": "USDT",
        "decimals": 6,
        "asset_type": "ERC20",
        "chain_id": "4",
        "sub_network": "Rinkeby"
      },
      "new2eth_min_deposit_amount": "10",
      "eth2new_min_deposit_amount": "1",
      "new2eth_fee_percent": "0.000000",
      "eth2new_fee_percent": "0.000000",
      "new2eth_fee_min_amount": "1",
      "eth2new_fee_min_amount": "0"
    }
  ]
}
```

| Name                       | Type   | Description                                    |
| -------------------------- | ------ | ---------------------------------------------- |
| newchain_asset             | Token  | Assets on NewChain                             |
| ethereum_asset             | Token  | Assets on Ethereum                             |
| new2eth_min_deposit_amount | string | Minium deposit amount for `new2eth` direction. |
| eth2new_min_deposit_amount | string | Minium deposit amount for `eth2new` direction. |
| new2eth_fee_percent        | string | Fee percentage for `new2eth` direction.        |
| eth2new_fee_percent        | string | Fee percentage for `eth2new` direction.        |
| new2eth_fee_min_amount     | string | Minium fee for `new2eth` direction.            |
| eth2new_fee_min_amount     | string | Minium fee for `eth2new` direction.            |

### Fee

The actual amount of fee will use the larger one in `fee_percent` and `fee_min_amount` after calculation.

### `Token` type definition

| Name        | Type   | Description                                                                                                       |
| ----------- | ------ | ----------------------------------------------------------------------------------------------------------------- |
| address     | string | Contract address. `0x` format for ethereum, `NEW` address for newchain. `null` for chain coin like `ETH` or `NEW` |
| raw_address | string | Contract address in `0x` format.                                                                                  |
| name        | string | Asset Name                                                                                                        |
| symbol      | string | Asset Symbol                                                                                                      |
| decimals    | uint8  | Asset Presision.                                                                                                  |
| asset_type  | string | Asset Type. `Coin` or `NRC6` for NewChain. `Coin` or `ERC20` for Ethereum.                                        |
| chain_id    | int    | ChainID                                                                                                           |
| sub_network | string | Sub Network Name. `Mainnet` or `Testnet` for NewChain, `Mainnet` or `Rinkeby` for Ethereum.                       |
