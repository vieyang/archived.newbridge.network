# Create Account

```proto
rpc CreateAccount (CreateAccountRequest) returns (CreateAccountReply) {}
```

## API parameters

### Required

```proto
message CreateAccountRequest {
    string name = 1;
}
```

| **Name** | **Type** | **Description**            |
| -------- | -------- | -------------------------- |
| name     | string   | 另一个链上的用户的收款地址 |

### Response

```proto
message CreateAccountReply {
    string name = 1;
    string address = 2; // the address to deposit
}
```

| **Name** | **Type** | \*Description\*\*          |
| -------- | -------- | -------------------------- |
| name     | string   | 另一个链上的用户的收款地址 |
| address  | string   | 当前链上的用户的存款地址   |
