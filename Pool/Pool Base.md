## `onJoinPool` - pool join logic, the function doesn't perform actual token transfer, but returns the values for the transfer

Called by the Vault when a user calls `IVault.joinPool` to add liquidity to this Pool. Returns how many of each registered token the user should provide, as well as the amount of protocol fees the Pool owes to the Vault. The Vault will then take tokens from `sender` and add them to the Pool's balances, as well as collect the reported amount in protocol fees, which the pool should calculate based on `protocolSwapFeePercentage`.

---
## `onExitPool` - pool exit logic, the function doesn't perform actual token transfer, but returns the values for the transfer

Called by the Vault when a user calls `IVault.exitPool` to remove liquidity from this Pool. Returns how many tokens the Vault should deduct from the Pool's balances, as well as the amount of protocol fees the Pool owes to the Vault. The Vault will then take tokens from the Pool's balances and send them to `recipient`, as well as collect the reported amount in protocol fees, which the Pool should calculate based on `protocolSwapFeePercentage`.

---

## `getScalingFactors` - ?

---

## `queryJoin` - ?

---

## `queryExit` - ?