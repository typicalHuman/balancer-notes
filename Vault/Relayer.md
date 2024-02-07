https://docs.balancer.fi/concepts/advanced/relayers.html

Relayer is basically imitation of the user, the user can give permission to another contract/user to perform certain operations or just do any operation on his behalf. 

There are 2 types of relaying:
- user lever - when you basically saying - this user can do anything with my money
- protocol level - when you allow the relayer to do only certain things (like join/exit/swap)

Permission for protocol level is working via `actionId` mechanism which is basically saying that: *this user can perform an action for this signature methods*.

To generalize a bit more, a Solidity snippet like this can calculate an `actionId` given a `target` address and a function definition `fn` such as `"swap((bytes32,uint8,address,address,uint256,bytes),(address,bool,address,bool),uint256,uint256)"`.

```
function generateActionId(address target, string calldata fn) public pure returns (bytes32) {
    bytes32 disambiguator = bytes32(uint256(address(target)));
    bytes4 selector = bytes4(keccak256(bytes(fn)));
    return keccak256(abi.encodePacked(disambiguator, selector));
}
```