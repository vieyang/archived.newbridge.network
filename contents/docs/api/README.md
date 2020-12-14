# API

## Main API

main api is the for users or web ui to access newbridge

* [history](history.md)
* [account](account.md)
* [pairs](pairs.md)

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

* [CreateAccount](create-account.md)

