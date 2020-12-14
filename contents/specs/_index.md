---
menu:
  main:
    name: Architecture
    weight: 5
title: Architecture
---

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

Each chain has its own `monitor` program, which will detect the payment status of the address in the system based on token information.

## Secure Vault

### Collection

Each chain has its own `collection` program

- native
  for native assets such as ETH or NEW, general transfer
- burnable
  for burnable token，use burn function to burn token
- transfer
  transfer token to system offline wallet

### Payout

Each chain has its own `payout` program

- native
  native coin user general transfer, from MainAddress to payout
- mintable
  for mintable token, call mint function by MainAddress
- transfer
  for token, call transfer function by MainAddress

### fees

- GasPrice
  call `eth_gasPrice` to get gas price
- GasLimit
  - Force use 90000 for general transfer
  - Force use 100000 for token transfer

## core (validator)

NewBridge Core is used to coordinate the user deposit, handling fee, payout;

- Input
  - User deposit address
  - System receipt address
  - Amount
- Out
  - User receipt address
  - Amount
