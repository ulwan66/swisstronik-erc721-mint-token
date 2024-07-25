# Swisstronik Tesnet Techinal Task 3 (Mint a ERC-721 Token)

link : [Click!](https://www.swisstronik.com/testnet2/dashboard)

Feel free donate to my EVM address

EVM :

```bash
0x6c34be1ec3f1d3a55d40cdedaeccd7772ac30d44
```

## Steps

### 1. Clone Repository

```bash
git clone https://github.com/ulwan66/swisstronik-erc721-mint-token.git
```

```
cd swisstronik-erc721-mint-token
```

### 2. Install Dependency

```bash
npm install
```

### 3. Set .env File

create .env file in root project

```bash
PRIVATE_KEY="a99a343b964580e8b199c7a86798201d4d746cf18296e444e754372ac80b962d"
```

### 4. Update Smart Contract (Skipp if you won't modify NFT name)

- Open contracts folder
- Open Nft.sol file
- Feel free to modify token name and token symbol

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

contract TestNFT is ERC721 {
    uint256 private _currentTokenId = 0;

    event NFTMinted(address recipient, uint256 tokenId);

    constructor() ERC721("KillwanNFT", "KILLNFT") {}

    function mintNFT(address recipient) public returns (uint256) {
        _currentTokenId += 1;
        uint256 newItemId = _currentTokenId;
        _mint(recipient, newItemId);

        emit NFTMinted(recipient, newItemId);

        return newItemId;
    }

    function burnNFT(uint256 tokenId) public {
        _burn(tokenId);
    }
}

```

### 5. Compile Smart Contract

```bash
npm run compile
```

### 6. Deploy Smart Contract

```bash
npm run deploy
```

### 7. Mint Token

```bash
npm run mint
```

### 8. Finsihed

- Open the deployed-adddress.ts (location in utils folder)
- Copy the address and paste the address into testnet dashboard
- Open the tx-hash.txt (location in utils folder)
- Copy the address and paste the tx hash link into testnet dashboard
- push this project to your github and paste your repository link in testnet dashboard

by :
github : [ulwan66](https://github.com/ulwan66)
twitter : @NardeTesi
telegram : @killwqn
