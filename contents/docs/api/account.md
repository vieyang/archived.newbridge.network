
# `GET` Account Info

**`GET` /v1/newbridge/account

return account base info

## API parameters

### Required

| **Name**         | **In** | **Type** | **Description**                                              | **Enum** | **Default** |
| ---------------- | ------ | -------- | ------------------------------------------------------------ | -------- | ----------- |
| direction | query  | string   | `new2eth` or `eth2new` |          |             |
| ethereum_recipient_address | query  | string   | only for `new2eth`, the recipient address on ethereum |          |             |
| newchain_recipient_address | query | string   | only for `eth2new`, the recipient address on newchain, prefix can be NEW or 0x | | |


```bash
curl -v https://replace-api-domain.ext/newbridge/account?ethereum_recipient_address=0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c&direction=new2eth
```

## Response

```json
{
"ethereum_recipient_address": "0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c",
"newchain_recipient_raw_address": "",
"direction": "new2eth",
"newchain_deposit_address": "NEW17zLJnGFnhi9b3yPUanjiieXknCirQhNwWE1",
"newchain_deposit_raw_address": "0x5741E7e542828DF38A888bcc9b8f9500e4331420"
}
```

| Name                 | Type          | Desc                                                         |
| -------------------- | ------------- | ------------------------------------------------------------ |
| ethereum_recipient_address | string  | only for `new2eth`, the recipient address on ethereum |
| newchain_recipient_address | string   | only for `eth2new`, the recipient address on newchain, prefix is NEW |
| newchain_recipient_raw_address | string        | only for `eth2new`, the recipient raw address on newchain, prefix is 0x |
| direction                      | string | `new2eth` or `eth2new` |
| ethereum_deposit_address       | string | only for `eth2new`, the deposit address on ethereum |
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