
# `GET` Account Info

**`GET` /v1/newbridge/account

返回account的账户基本信息

## API parameters

### 请求参数

| **Name**         | **In** | **Type** | **Description**                                              | **Enum** | **Default** |
| ---------------- | ------ | -------- | ------------------------------------------------------------ | -------- | ----------- |
| direction | query  | string   | `new2eth`或者`eth2new`之一，强制接口指定跨链方向，防止地址与方向混淆。 |          |             |
| ethereum_recipient_address | query  | string   | `new2eth`方向上，用户在ethereum链上的收币地址。 |          |             |
| newchain_recipient_address | query | string   | `eth2new`方向上，用户在newchain链上的收币地址，可以是NEW开头的地址或者0x开头的原生格式。 | | |


```bash
curl -v https://replace-api-domain.ext/newbridge/account?ethereum_recipient_address=0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c&direction=new2eth
```

## 返回参数

```json
{
"ethereum_recipient_address": "0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c",
"newchain_recipient_raw_address": "",
"direction": "new2eth",
"newchain_deposit_address": "NEW17zLJnGFnhi9b3yPUanjiieXknCirQhNwWE1",
"newchain_deposit_raw_address": "0x5741E7e542828DF38A888bcc9b8f9500e4331420"
}
```

| 名称                 | 类型          | 描述                                                         |
| -------------------- | ------------- | ------------------------------------------------------------ |
| ethereum_recipient_address | string  | `new2eth`方向，用户在ethereum链上的收币地址。 |
| newchain_recipient_address | string   | `eth2new`方向，用户在newchain链上的收币地址，NEW开头的地址。 |
| newchain_recipient_raw_address | string        | `eth2new`方向，用户在NewChain链上的收币地址的Raw格式，0x开头          |
| direction                      | string | `new2eth`或者`eth2new`之一                                   |
| ethereum_deposit_address       | string | `eth2new`方向，ethereum链上的冲币地址                        |
| newchain_deposit_address       | string | `new2eth`方向，newchain链上的冲币地址，NEW开头的地址         |
| newchain_deposit_raw_address   | string | `new2eth`方向， newchain链上的冲币地址，0x开头的原生格式     |



### Error Codes

| **Status** | **Code**                     | **Description**                              | **Params**                                                   |
| ---------- | ---------------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| **400**    | account_not_found            | Acount was not found                         |                                                              |
| **400**    | address_is_in_invalid_format | Requested address format is not valid        | { "type" => "newchain_address" } or  { "type" => "ethereum_address" } |
| **429**    | too_many_requests            | Too many requests have been made to the api. |                                                              |
| **500**    | internal_server_error        | Internal server error                        |                                                              |
| **503**    | service_unavailable          | Service is temporary unavailable             |                                                              |