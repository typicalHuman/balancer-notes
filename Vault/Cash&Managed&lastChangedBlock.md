==**CASH** - is the number of tokens the Vault currently holds for the Pool.==

==**MANAGED** - is the number of tokens withdrawn and held outside the Vault by the Pool's token Asset Manager.== 
==**LAST CHANGED BLOCK** - just blocknumber when last balance change happened.== 

The Pool's total balance for `token` equals the sum of `cash` and `managed`.

The balance stored with this format:

The 'cash' portion of the balance is stored in the least significant 112 bits of a 256 bit word, while the 'managed' part uses the following 112 bits. The most significant 32 bits are used to store the block

*| 112 bits cash balance | 112 bits managed balance | 32 bits last changed block |
