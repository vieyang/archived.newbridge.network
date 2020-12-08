---
title: FAQ
menu: 
  main:
    name: FAQ
    weight: 3
---

# FAQ

## What is NewSwap?

NewSwap is an application protocol built on Newton's NewChain, which realizes the exchange between NEW and the NRC6 token issued based on NewChain. Any two NRC6 tokens can also be exchanged on it.

Its characteristics are: system automatic pricing, fast and convenient exchange process, each transaction fee is automatically transferred to the liquidity provider, decentralized, safe and reliable, users can fully control their assets by controlling their own private keys, and the threshold is extremely low. it has global liquidity.

## How does NewSwap work?

NewSwap is an automatic liquidity agreement. There is no need to bid and match transactions, and there are no centralized organizations and facilities to guarantee transactions. Each trading pool is controlled by a smart contract, which supports operations such as the exchange of tokens and the increase or decrease of liquidity. Each fund pool uses the formula x*y=k to guarantee transactions. x=token 1, y=token 2, k=constant.

## What tokens are supported for exchange?

It supports the exchange between NEW and NRC6 certificates, as well as the exchange between NRC6 and NRC6 tokens.

## What determines the price?

The price is determined by the relative number of tokens in each fund pool. The smart contract maintains a constant formula: x*y=k, under this condition, x=token 1, y=token 2, k=constant. Each transaction will withdraw a certain number of tokens in exchange for the quantity of another token. During this period, the constant k remains unchanged and the balance is updated. Therefore, each transaction will adjust the balance of the token, thereby changing the price.

## Why does my exchange fail?

If the slippage tolerance is set too small during exchange, the exchange will fail. You can increase the slippage tolerance through the advanced settings window when redeeming, and the wallet account should have enough balance to ensure the successful transaction.

## What is the NewSwap exchange fee?

A transaction fee of 0.3% needs to be paid. After liquidity mining is started, 0.25% of the 0.3% transaction fee belongs to the token liquidity provider. The remaining 0.05% is used to support the value of NST. For example, if 1000 tokens A are exchanged for NEW, you need to pay 0.3% of 1000 tokens A namely 3 tokens of A as transaction fees, of which 2.5 tokens belong to the liquidity provider. To exchange 1000 NEW for token 2, you need to pay 3 NEW as a transaction fee.

## What is the initial price for creating a fund pool?

The initial price is determined by the first person to create a capital pool and increase liquidity. If the price is unreasonable, users will transfer more to fill in the price difference.

## How to calculate the token ratio for adding/deleting fund pools?

When adding/deleting the liquidity of an asset pool, it needs to be added or deleted according to the ratio of the number of tokens and NEW in the current fund pool. For example, the number of tokens in the fund pool: NEW number=1:100, the ratio of the number of tokens you add and delete to NEW must be 1:100.

## How to issue a token and to be listed on NewSwap Default Token List?

First, use the NewChain token issuing tool NewGenerator to issue the token, open the link: newswap.org, click "NewGenerator" in the “More”, and fill in the relevant information in the blanks.

After the issuance of the token, the token with the actual business model and purpose can apply for listing on NewSwap for trading. Open NewSwap official website newswap.org, click "Apply Listing for Default Token List", to submit your request.

After passing the review, the applicant will receive the list information via email and be able to see the token in the Default Token List. Then create a trading pair and add a fund pool on NewSwap for other to be able to trade.