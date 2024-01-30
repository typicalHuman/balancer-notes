Actually Vault can store not just pool tokens - it can store the tokens of the user/contract. It's called internal balance.

With that you can swap/join/exit with much less gas consumption, because you don't need to transfer the tokens to the vault. This allows you to do smarter arbitrages

`ETH` Cannot be stored as internal balance.

`UserBalance.sol` is responsible for the internal balance logic.
### Example:
"An arbitrageur that holds `WETH` and `USDC` as internal balances in the Vault can perform an extremely low gas cost swap with no token transfers and then complete the other leg of the arb on a centralized exchange."

---

- Internal Balance management features batching, which means a single contract call can be used to perform multiple operations of different kinds, with different senders and recipients, at once.
- Internal Balance withdrawals can always be performed by an authorized account at any time (even if.