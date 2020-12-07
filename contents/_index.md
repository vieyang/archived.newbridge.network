---
title: Introduction
type: docs
---

# `GET` Account History

**`GET` /v1/newbridge/history**

Returns a JSON structure with details of the NewBridge transfer history of the specified accounts.

## API parameters

### Required

| **Name**         | **In** | **Type** | **Description**                                              | **Enum** | **Default** |
| ---------------- | ------ | -------- | ------------------------------------------------------------ | -------- | ----------- |
| newchain_address | query  | string   | At least one parameter should be provided in `newchain_address` and `ethereum_address`. NewChain address can be starting with `NEW` or using raw hex address starting with `0x`. |          |             |
| ethereum_address | query  | string   | At least one parameter should be provided in `newchain_address` and `ethereum_address`. Ethereum address should be starting with `0x`. |          |             |

### Optional

| **Name**  | **In** | **Type** | **Description**             | **Enum** | **Default** |
| --------- | ------ | -------- | --------------------------- | -------- | ----------- |
| page_id   | query  | integer  | Page number.                |          |             |
| page_size | query  | integer  | Number of results per page. |          |             |

```bash
curl -v https://replace-api-domain.ext/newbridge/history?newchain_address=0x97549E368AcaFdCAE786BB93D98379f1D1561a29&page_size=1
```

## Response `200`

```json
{
  "newchain_address": "NEW17zS9ZvgGV1EaT8KT2tLjqRvQbcApjFot8xj",
  "newchain_raw_address": "0x97549E368AcaFdCAE786BB93D98379f1D1561a29",
  "page_id": "1",
  "page_size": "1",
  "total_page": "6",
  "total_history": "53",
  "list": [
    {
      "from_network": "Ethereum",
      "from_sub_network": "Rinkeby",
      "from_chain_id": "4",
      "to_network": "NewChain",
      "to_sub_network": "Testnet",
      "to_chain_id": "1007",
      "from_address": "0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c",
      "from_raw_address": "0xad61cc6653B62b7C05Bd2F593Bc49d22Fb901A9c",
      "to_address": "NEW17zS9ZvgGV1EaT8KT2tLjqRvQbcApjFot8xj",
      "to_raw_address": "0x97549E368AcaFdCAE786BB93D98379f1D1561a29",
      "from_tx_hash": "0xad9716fdd2ae16840a96360e54dd683511a20a68c9e855c58ea333a3930206b2",
      "from_asset_type": "Token",
      "from_asset_name": "TestNet Launch",
      "from_asset_symbol": "TL",
      "from_asset_address": "0xCc5b1517bae326F8E147D6bEd17F5F53bc2f85c5",
      "to_tx_hash": "0x54b61d26348c2f6b71866620325c3ec39eaa8c5d1488cecc7f5b28422583bcc9",
      "to_asset_type": "Token",
      "to_asset_name": "TestNet Launch",
      "to_asset_symbol": "TL",
      "to_asset_address": "0x243a5C81C1F9970aa3e6f51d73fC13eE853FC338",
      "amount_requested": "14",
      "amount_fulfilled": "14",
      "fee": "0",
      "status": "Confirmed"
    }
  ]
}
```

| **Name**                 | **Type**          | **Description**                                                         |
| -------------------- | ------------- | ------------------------------------------------------------ |
| newchain_address     | String        | NewChain Address starting with `NEW`.  Only one of  `newchain_address` or `ethereum_address` will be returned. |
| ethereum_address     | String        | Ethereum Address starting with `0x`. Only one of  `newchain_address` or `ethereum_address` will be returned. |
| newchain_raw_address | String        | NewChain Address in raw hex format starting with `NEW`. |
| page_id              | int           | Page number.                     |
| page_size            | int           | Number of results per page.                      |
| total_page           | int           | Number of total page.            |
| total_history        | int           | Number of total results.       |
| list                 | BridgeHistory | Array type of `BridgeHistory`. |    

### Error Codes

| **Status** | **Code**                     | **Description**                              | **Params**                                                   |
| ---------- | ---------------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| **400**    | account_not_found            | Acount was not found                         |                                                              |
| **400**    | address_is_in_invalid_format | Requested address format is not valid        | { "type" => "newchain_address" } or  { "type" => "ethereum_address" } |
| **429**    | too_many_requests            | Too many requests have been made to the api. |                                                              |
| **500**    | internal_server_error        | Internal server error                        |                                                              |
| **503**    | service_unavailable          | Service is temporary unavailable             

# Acerbo datus maxime

```
curl -v https://replace-api-domain.ext/newbridge/history?newchain_address=0x97549E368AcaFdCAE786BB93D98379f1D1561a29&page_size=1
```

{{< columns >}}
## Astris ipse furtiva

Est in vagis et Pittheus tu arge accipiter regia iram vocatur nurus. Omnes ut
olivae sensit **arma sorori** deducit, inesset **crudus**, ego vetuere aliis,
modo arsit? Utinam rapta fiducia valuere litora _adicit cursu_, ad facies

<--->

## Suis quot vota

Ea _furtique_ risere fratres edidit terrae magis. Colla tam mihi tenebat:
miseram excita suadent es pecudes iam. Concilio _quam_ velatus posset ait quod
nunc! Fragosis suae dextra geruntur functus vulgata.
{{< /columns >}}


## Tempora nisi nunc

Lorem **markdownum** emicat gestu. Cannis sol pressit ducta. **Est** Idaei,
tremens ausim se tutaeque, illi ulnis hausit, sed, lumina cutem. Quae avis
sequens!




### Commander Go

```go
package cli

import (
	"context"
	"fmt"

	"github.com/ethereum/go-ethereum/common"
	"github.com/ethereum/go-ethereum/rpc"
	"github.com/newtonproject/newcommander/tracer"
	"github.com/spf13/cobra"
)

func (cli *CLI) buildTraceCmd() *cobra.Command {
	cmd := &cobra.Command{
		Use:                   "trace <txHash>",
		Short:                 "trace tx with hash and get internal txs",
		DisableFlagsInUseLine: true,
		Args:                  cobra.MinimumNArgs(1),
		Run: func(cmd *cobra.Command, args []string) {
			rpcclient, err := rpc.Dial(cli.rpcURL)
			if err != nil {
				fmt.Println(err)
				return
			}

			txHash := common.HexToHash(args[0])

			config := &tracer.TraceConfig{
				Tracer:  "",
				Timeout: nil,
				Reexec:  nil,
			}

			txs, err := tracer.TraceTransaction(rpcclient, context.Background(), txHash, config)
			if err != nil {
				fmt.Println("Trace error: ", err)
				return
			}
			for _, tx := range txs {
				txJson, err := tx.MarshalJSON()
				if err != nil {
					fmt.Println(err)
					return
				}
				fmt.Println(string(txJson))
			}
		},
	}

	return cmd
}
```
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required
### Required