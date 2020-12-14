---
title: Account API
description: "To lookup account in chains"
author: "Vie Yang"
---

# Account API

## `GET` Account Info

**`GET` /v1/newbridge/account**

返回 account 的账户基本信息

Returns a JSON structure with details of one account's address in bridged network.

## API parameters

### Required

| **Name**                   | **In** | **Type** | **Description**                                                                                  | **Enum**            |
| -------------------------- | ------ | -------- | ------------------------------------------------------------------------------------------------ | ------------------- |
| direction                  | query  | string   | Specify NewBridge network direction.                                                             | `new2eth` `eth2new` |
| ethereum_recipient_address | query  | string   | Reciving account on ethereum in `new2eth` direction. Must be address starting with `0x`          |                     |
| newchain_recipient_address | query  | string   | Reciving account on ethereum in `eth2new` direction. Can be address starting with `NEW` or `0x`. |                     |

```bash
curl -v https://replace-api-domain.ext/newbridge/account?ethereum_recipient_address=0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c&direction=new2eth
```

## Response `200`

```json
{
  "ethereum_recipient_address": "0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c",
  "newchain_recipient_raw_address": "",
  "direction": "new2eth",
  "newchain_deposit_address": "NEW17zLJnGFnhi9b3yPUanjiieXknCirQhNwWE1",
  "newchain_deposit_raw_address": "0x5741E7e542828DF38A888bcc9b8f9500e4331420"
}
```

| **Name**                       | **Type** | **Description**                                                |
| ------------------------------ | -------- | -------------------------------------------------------------- |
| ethereum_recipient_address     | string   | Receiving address in on ethereum for `new2eth` direction.      |
| newchain_recipient_address     | string   | Receiving address in on newchain for `eth2new` direction.      |
| newchain_recipient_raw_address | string   | Receiving address in `0x` on newchain for `eth2new` direction. |
| direction                      | string   | NewBridge network direction                                    |
| ethereum_deposit_address       | string   | Deposit address on ethereum for `eth2new` direction.           |
| newchain_deposit_address       | string   | Deposit address on newchain for `new2eth` direction.           |
| newchain_deposit_raw_address   | string   | Deposit address in `0x` on newchain for `new2eth` direction.   |

### Error Codes

| **Status** | **Code**                     | **Description**                              | **Params**                                                           |
| ---------- | ---------------------------- | -------------------------------------------- | -------------------------------------------------------------------- |
| **400**    | account_not_found            | Acount was not found                         |                                                                      |
| **400**    | address_is_in_invalid_format | Requested address format is not valid        | { "type" => "newchain_address" } or { "type" => "ethereum_address" } |
| **429**    | too_many_requests            | Too many requests have been made to the api. |                                                                      |
| **500**    | internal_server_error        | Internal server error                        |                                                                      |
| **503**    | service_unavailable          | Service is temporary unavailable             |                                                                      |
