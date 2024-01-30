==**CASH** - is the number of tokens the Vault currently holds for the Pool.==

==**MANAGED** - is the number of tokens withdrawn and held outside the Vault by the Pool's token Asset Manager.== 
==**LAST CHANGED BLOCK** - just blocknumber when last balance change happened.== 

The Pool's total balance for `token` equals the sum of `cash` and `managed`.

The balance stored with this format:

The 'cash' portion of the balance is stored in the least significant 112 bits of a 256 bit word, while the 'managed' part uses the following 112 bits. The most significant 32 bits are used to store the block

*| 112 bits cash balance | 112 bits managed balance | 32 bits last changed block |


Alternative mode for Pools with the **Two Token** specialization setting.

Instead of storing cash and external for each 'token in' a single storage slot, Two Token Pools store the cash for both tokens in the same slot, and the managed for both in another one. This reduces the gas cost for swaps, because the only slot that needs to be updated is the one with the cash. However, it also means that managing balances is more cumbersome, as both tokens need to be read/written at the same time. The field with both cash balances packed is called sharedCash, and the one with external amounts is called sharedManaged. These two are collectively called the 'shared' balance fields. In both of these, the portion that corresponds to token A is stored in the least significant 112 bits of a 256 bit word, while token B's part uses the next least significant 112 bits.
