# base-nft-factory
Optimized ERC-721 and ERC-1155 smart contract templates for digital collectibles and NFT minting on Base L2.

Production-ready smart contract templates for deploying highly efficient NFT collections on the Base network.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.12;

contract BaseCollectionNFT {
    string public name = "Base Explorer Club";
    string public symbol = "BEC";
    uint256 public nextTokenId;
    address public owner;

    mapping(uint256 => address) public tokenOwners;

    constructor() {
        owner = msg.sender;
    }

    function mintNFT(address to) public {
        require(msg.sender == owner, "Only owner can mint");
        tokenOwners[nextTokenId] = to;
        nextTokenId++;
    }
}
```
