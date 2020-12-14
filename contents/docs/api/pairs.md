
# `GET` Pairs Info

**`GET` /v1/newbridge/pairs

return the account base info

## API parameters

### Required

- NULL


```bash
curl -v https://replace-api-domain.ext/newbridge/pairs
```

## Response

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

| Name                 | Type          | Desc                                                         |
| -------------------- | ------------- | ------------------------------------------------------------ |
| newchain_asset | Token  | the newchain asset |
| ethereum_asset | Token |  the ethereum asset |
| new2eth_min_deposit_amount | string        | the min deposit amount of `new2eth` direction |
| eth2new_min_deposit_amount | string | the min deposit amount of `eth2new` direction |
| new2eth_fee_percent | string | the fee percent of amount for `new2eth` direction. ActualFee = max(`new2eth_fee_percent`, `new2eth_fee_min_amount` ) |
| eth2new_fee_percent | string | the fee percent of amount for `eth2new` direction. ActualFee = max(`new2eth_fee_percent`, `new2eth_fee_min_amount` ) |
| new2eth_fee_min_amount | string | the min amount of `new2eth` direction |
| eth2new_fee_min_amount | string | the min amount of `eth2new` direction  |



The type of `Token` is as follow:

| Name        | Type   | Desc                                                         |
| ----------- | ------ | ------------------------------------------------------------ |
| address     | string | contract address, 0x format for ethereum and NEW format for newchain. empty for native coin(NEW/ETH) |
| raw_address | string | contract address, raw address in format of 0x |
| name        | string | the name of token |
| symbol      | string | the sympbol of token |
| decimals    | uint8  | the deicmals of token, decimals must be the same on two chain |
| asset_type  | string | asset type, NewChain: `Coin`,`ERC6`, Ethereum: `Coin`,`ERC20` |
| chain_id    | int    | The chain id                                                  |
| sub_network | string | sub name of chain，newchain: `Mainnet`,`Testnet`, ethereum: `Mainnet`,`Rinkeby` |



### Error Codes

| **Status** | **Code**                     | **Description**                              | **Params**                                                   |
| ---------- | ---------------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| **400**    | account_not_found            | Acount was not found                         |                                                              |
| **400**    | address_is_in_invalid_format | Requested address format is not valid        | { "type" => "newchain_address" } or  { "type" => "ethereum_address" } |
| **429**    | too_many_requests            | Too many requests have been made to the api. |                                                              |
| **500**    | internal_server_error        | Internal server error                        |                                                              |
| **503**    | service_unavailable          | Service is temporary unavailable             |                                                              |