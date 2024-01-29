
`poolId` consists of 3 parts:

- 0-42 **pool address**
- 42 - 46 **pool specialization** (0 - GENERAL, 1 - MINIMAL_SWAP_INFO, 2 - TWO_TOKENS)
- 46 - end: unique pool **nonce** (Each Pool is assigned a unique ID based on an incrementing nonce. This assumes there will never be more than, 2\*\*80 Pools, and the nonce will not overflow.)

Pool IDs have the following layout:

*| 20 bytes pool contract address | 2 bytes specialization setting | 10 bytes nonce |*