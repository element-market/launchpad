# Launchpad

### Contract Address

  <table>
  <tr>
  <th>Network</th>
  <th>Contract Address</th>
  </tr>

  <tr><td>Ethereum Mainnet</td><td>
    <a href="https://etherscan.io/address/0x4cc4752155877f4333f25bb9a6f8880567ee1231#code">0x4cc4752155877F4333f25bB9A6F8880567ee1231</a>
  </td></tr>

  <tr><td>Ethereum Goerli</td><td>
  <a href="https://goerli.etherscan.io/address/0x8873e78a66d906959a49527868010ee7ffc01d12#code">0x8873E78A66D906959a49527868010ee7ffc01d12</a>
  </td></tr>

  <tr><td>Bsc Mainnet</td><td>
    <a href="https://bscscan.com/address/0xdc21de4bfd34d4b308419c27d779e331d15a7064#code">0xDC21dE4BFd34d4b308419c27D779E331D15A7064</a>
  </td></tr>

  <tr><td>Bsc Testnet</td><td>
  <a href="https://testnet.bscscan.com/address/0xeb6d3020456181cfc5383688f3e94166d4d80f84#code">0xeB6d3020456181cfC5383688f3E94166d4D80F84</a>
  </td></tr>

  <tr><td>ZkSync Era Mainnet</td><td>
    <a href="https://explorer.zksync.io/address/0x0F739c53D910C3eF246f670C3dbE7c8d8bdFD72b#contract">0x0F739c53D910C3eF246f670C3dbE7c8d8bdFD72b</a>
  </td></tr>

  <tr><td>ZkSync Era Testnet</td><td>
    <a href="https://goerli.explorer.zksync.io/address/0x29BDefA9a2f636FE54607904235FfEeCF485D45F#contract">0x29BDefA9a2f636FE54607904235FfEeCF485D45F</a>
  </td></tr>

  <tr><td>Arbitrum One</td><td>
    <a href="https://arbiscan.io/address/0x20Baa25Bbe6b3216148Bb87ED0e1022CC632a80E#code">0x20Baa25Bbe6b3216148Bb87ED0e1022CC632a80E</a>
  </td></tr>

  <tr><td>Arbitrum Goerli</td><td>
    <a href="https://goerli.arbiscan.io/address/0xac7321CBD3742B3eFC736d077B136DA769463B9D#code">0xac7321CBD3742B3eFC736d077B136DA769463B9D</a>
  </td></tr>

  <tr><td>Polygon Mainnet</td><td>
    <a href="https://polygonscan.com/address/0xf48EdDEe2273b2af0718EE781eb1E53a4bFebEf7">0xf48EdDEe2273b2af0718EE781eb1E53a4bFebEf7</a>
  </td></tr>

  <tr><td>Base Mainnet</td><td>
    <a href="https://basescan.org/address/0x26Df6Fea89f1C9e4A3A2bfc2128542B7a05FbA8E#code">0x26Df6Fea89f1C9e4A3A2bfc2128542B7a05FbA8E</a>
  </td></tr>

  <tr><td>Base Testnet</td><td>
    <a href="https://goerli.basescan.org/address/0xa803a0a2aE6b53bB03713B4ba60b760aA4718825#code">0xa803a0a2aE6b53bB03713B4ba60b760aA4718825</a>
  </td></tr>

  <tr><td>OpBNB Mainnet</td><td>
    <a href="https://mainnet.opbnbscan.com/address/0x734026dE65E9A8dd0141992dBB60153Df5DF2b57?p=1&tab=Contract">0x734026dE65E9A8dd0141992dBB60153Df5DF2b57</a>
  </td></tr>

  <tr><td>Scroll</td><td>
    <a href="https://scrollscan.com/address/0xBF80D65d44A03539B57d36c6763C97eC224Ad4ac">0xBF80D65d44A03539B57d36c6763C97eC224Ad4ac</a>
  </td></tr>

  <tr><td>Manta Pacific</td><td>
    <a href="https://pacific-explorer.manta.network/address/0x26Df6Fea89f1C9e4A3A2bfc2128542B7a05FbA8E/contracts#address-tabs">0x26Df6Fea89f1C9e4A3A2bfc2128542B7a05FbA8E</a>
  </td></tr>

  <tr><td>Mantle</td><td>
    <a href="https://explorer.mantle.xyz/address/0xec9Acf4Ca6dad2720be6d0b5bCb6DDF56728Bb57/contracts#address-tabs">0xec9Acf4Ca6dad2720be6d0b5bCb6DDF56728Bb57</a>
  </td></tr>

  <tr><td>Optimism Mainnet</td><td>
    <a href="https://optimistic.etherscan.io/address/0xF9c0EE3059d2227A9bf6d966Ce833411033797C0#code">0xF9c0EE3059d2227A9bf6d966Ce833411033797C0</a>
  </td></tr>
  
  </table>

### Api Docs

You need implement one of the following methods, allowing our launchpad contract to mint ERC721 to the user address.

Note that the mint method name can be changed to another one according to your requirements, as long as the parameter list is consistent.

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
/// @param amount The quantity purchased by the user.
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
