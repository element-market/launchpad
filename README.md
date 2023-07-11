# Launchpad Api Doc


You need implement one of the following method, allowing our launchpad contract to mint ERC721 to the user address.


```solidity
/// @dev Mint an erc721 to the user address.
/// @param to The user address.
/// @Note The method name can be changed to another, but the parameters cannot be modified.
function whitelistMint1(address to) external {
    // Check permissions.
    require(_inWhitelist[msg.sender], "Not in the whitelist");
    
    // Your other codes
    // ...
    
    // Mint erc721.
    _mint(to, _getTokenId());
}

/// @dev Mint erc721s to the user address.
/// @param to The user address.
/// @param to The user address.
/// @Note The method name can be changed to another, but the parameters cannot be modified.
function whitelistMint2(address to, uint256 amount) external {
    // Check permissions.
    require(_inWhitelist[msg.sender], "Not in the whitelist");

    // Your other codes
    // ...

    // Mint erc721s.
    for (uint256 i; i < amount; i++) {
        _mint(to, _getTokenId());
    }
}


```
