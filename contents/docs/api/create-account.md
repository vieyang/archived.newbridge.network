---
title: Create Account
description: API Addresses for different Networks
weight: 1
---

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

| **Name**         | **Type** | **Description**   |
| ---------------- | ------ | -------------------------------------------|
| name | string   | the nick name for the acccount to be created, in newbridge, this is the user's recipient address of another chain  |       


### Response

```proto
message CreateAccountReply {
    string name = 1;
    string address = 2; // the address to deposit
}
```

| **Name**         | **Type** | *Description** |              
| ---------------- | ------ | ------------------------------------------|
| name | string   | the nick name for the acccount to be created, in newbridge, this is the user's recipient address of another chain   
| address | string | the address of current chain |