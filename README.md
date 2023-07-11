# Launchpad

### Contract Address

  <table>
  <tr>
  <th>Network</th>
  <th>Contract Address</th>
  </tr>

  <tr><td>Ethereum</td><td>
    <a href="https://etherscan.io/address/0x4cc4752155877f4333f25bb9a6f8880567ee1231">0x4cc4752155877F4333f25bB9A6F8880567ee1231</a>
  </td></tr>

  <tr><td>Goerli</td><td>
  <a href="https://etherscan.io/address/0x8873e78a66d906959a49527868010ee7ffc01d12">0x8873E78A66D906959a49527868010ee7ffc01d12</a>
  </td></tr>

  </table>

### Api Docs

You need implement one of the following methods, allowing our launchpad contract to mint ERC721 to the user address.

```solidity

/// @dev Mint an erc721 to the user address.
/// @param to The user address.
/// @Note The method name can be changed to another one, but the parameters cannot be modified.
function mintMethod1(address to) external {
    // Check if the msg.sender is in the partner list.
    require(_inPartnerList[msg.sender], "minter not allowed");
    
    // Your other codes.
    // ...
    
    // Mint erc721.
    _mint(to, _getTokenId());
}

/// @dev Mint erc721s to the user address.
/// @param to The user address.
/// @param to The user address.
/// @Note The method name can be changed to another one, but the parameters cannot be modified.
function mintMethod2(address to, uint256 amount) external {
    // Check if the msg.sender is in the partner list.
    require(_inPartnerList[msg.sender], "minter not allowed");

    // Your other codes.
    // ...

    // Mint erc721s.
    for (uint256 i; i < amount; i++) {
        _mint(to, _getTokenId());
    }
}

```
