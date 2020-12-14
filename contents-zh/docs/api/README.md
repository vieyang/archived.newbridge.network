# API

## Main API

`main api` 是为了用户方便及 web ui 使用

- [history](history.md)
- [account](account.md)
- [pairs](pairs.md)

## Chain API

Chain API 是运行在 `main api` 及 `newbridge core`后端的程序，其接口以 [grpc](https://grpc.io) 定义。

### 私钥

Chain API 是用来创建用户存款地址的，其运行在高可信安全环境中。

### API

`ChainAPI` 服务定义如下：

```grpc
// The ChainAPI service definition.
service ChainAPI {
    rpc CreateAccount (CreateAccountRequest) returns (CreateAccountReply) {}
}
```

- [CreateAccount](create-account.md)
