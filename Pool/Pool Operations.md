
There are 4 types of operations:
- Deposit
- Withdraw
- Swap
- Update (what is it??)

## Deposit

Algorithm:
- vault.joinPool
- vault._joinOrExit
- vault._callPoolBalanceChange
- joinInfo = pool.onJoinPool
- vault._processJoinPoolTransfers(joinInfo)

## Exit
Algorithm:
- vault.exitPool
- vault._joinOrExit
- vault._callPoolBalanceChange
- exitInfo = pool.onExitPool
- vault._processExitPoolTransfers(exitInfo)
