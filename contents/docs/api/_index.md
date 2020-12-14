---
title: API Docs
description: Newton Project has provided a public API for user or 3rd-party Apps to use and lookup data in NewBridge.
weight: 5
---

# NewBridge API Docs

Welcome to NewBridge API documents for Developers.

## Introduction

Join the developers who are building the next generation of cross-chain services. Our comprehensive documentation and guides help you explore the NewBridge API and features, and get integrated to use NewBridge as soon as possible.

## Browse APIs

{{< section-list >}}

## XChain API

XChain api is backend api for `Main API` and `NewBridgeCore`,
chainapi is defined in [grpc](https://grpc.io)

The Chain API server is defined as follow:

```grpc
// The ChainAPI service definition.
service ChainAPI {
    rpc CreateAccount (CreateAccountRequest) returns (CreateAccountReply) {}
}
```

- [CreateAccount](create-account.md)
