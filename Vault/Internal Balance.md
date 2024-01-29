Actually Vault can store not just pool tokens - it can store the tokens of the user/contract. It's called internal balance.

With that you can swap/join/exit with much less gas consumption, because you don't need to transfer the tokens to the vault. This allows you to do smarter arbitrages

`ETH` Cannot be stored as internal balance.
### Example:
"An arbitrageur that holds `WETH` and `USDC` as internal balances in the Vault can perform an extremely low gas cost swap with no token transfers and then complete the other leg of the arb on a centralized exchange."

  

