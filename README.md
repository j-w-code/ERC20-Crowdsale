# *KaseiCoin Crowdsale*
---
## Smart Contract for KaseiCoin
This project constructs a smart contract for a blockchain based crowdsale token. It utilizes Solidity, the Remix IDE, and Ganache testing environments to create a test contract. 

>"Is there life on Mars?"- David Bowie

## Technologies

This project uses Solidity, Remix IDE, and Ganache testing software to create the smart contract and deploy a testnet. 

[Solidity](https://github.com/ethereum/solidity)
[Remix](https://remix.ethereum.org/)
[Ganache](https://github.com/trufflesuite/ganache)

### Installation Guide

In order to use this program please import and utilie the following libraries and dependencies: 

```pragma solidity ^0.5.0;```

## Usage
The following blocks of code are fundamental in executing the program. 

```solidity 
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20Detailed.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/token/ERC20/ERC20Mintable.sol";
```
These imports initialize the inheritances for the ERC20 protocols our crowdsale will use. 

```solidity
contract KaseiCoin is ERC20, ERC20Detailed, ERC20Mintable {
    constructor(
        string memory name,
        string memory symbol,
        uint initial_supply
    )
        ERC20Detailed(name, symbol, 18)
        public
    {
        mint(msg.sender, initial_supply);
    }
}
```
This code initializes our token contract. 

```solidity
contract KaseiCoinCrowdsale is Crowdsale, MintedCrowdsale { 
    constructor(
        uint rate,
        address payable wallet,
        KaseiCoin token

    ) public Crowdsale(rate, wallet, token) {
        // constructor can stay empty
    }
}
```
This code constructs the contract for our crowdsale. It has inheritances from the token contract and other ERC20 contracts. 

## Evaluation Evidence

![<alt text>](https://i.postimg.cc/VvmbtBtK/Screen-Shot-2022-09-10-at-12-23-24-PM.png)

KaseiCoin being Deployed.


![<alt text>](https://i.postimg.cc/gcg04Wbz/Screen-Shot-2022-09-10-at-1-15-02-PM.png)

KaseiCoin import into Metamask and symbol "KSCN".

![<alt text>](https://i.postimg.cc/251JpnV9/Screen-Shot-2022-09-10-at-12-24-12-PM.png)

KaseiCoin balance check. 

![<alt text>](https://i.postimg.cc/ncMqG25W/Screen-Shot-2022-09-10-at-12-38-44-PM.png)

KaseiCoin Crowdsale deployment success. 

![<alt text>](https://i.postimg.cc/L6h0gzV9/Screen-Shot-2022-09-10-at-1-00-10-PM.png)

Token purchase transaction from within KaseiCoin Crowdsale contract. 

![<alt text>](https://i.postimg.cc/4x6vYdj4/Screen-Shot-2022-09-10-at-12-59-22-PM.png)

Transaction hash on local ganache testnet. 

## Further Evaluation Evidence


![<alt text>](https://i.postimg.cc/L4jjJ1s0/Screen-Shot-2022-09-13-at-6-26-41-PM.png)

Purchase from Deployer contract. 

![<alt text>](https://i.postimg.cc/pr1mwRZ4/Screen-Shot-2022-09-13-at-6-26-54-PM.png)

BalanceOf fucntion call. 

[![Screen-Recording-2022-09-13-at-6.29.30-PM.gif](https://s5.gifyu.com/images/Screen-Recording-2022-09-13-at-6.29.30-PM.gif)](https://gifyu.com/image/SwOYm)

Recording showing successful purchase, Metamask integration, and wei raised function call. 


![<alt text>](https://i.postimg.cc/DZjmt7fs/Screen-Shot-2022-09-13-at-6-28-15-PM.png)

Ganache devnet transaction hash.

## Contributors

Jeffrey J. Wiley Jr

## License

MIT
