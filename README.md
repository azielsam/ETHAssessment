# Creating a Token

In order to represent, share, and manage different digital assets or rights in a decentralized, secure, and transparent manner, a token is created on a blockchain. This enables a wide range of applications across industries.

## Description

Creating tokens on a blockchain involves setting up a smart contract with parameters like Token Name, Abbreviation, and Total Supply. To produce and distribute tokens, you will need a mint function, and to destroy them, a burn function. Importantly, the burn function has conditionals that check to see if the address has enough tokens to burn, maintaining supply integrity.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Here is an example code of my token:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
string public tokenName = "AZIEL";
string public tokenAbbrv = "AZ";
uint public totalSupply = 0;

    // mapping variable here
mapping(address => uint) public balances;

    // mint function
function mint (address token_address, uint token_value) public{
    totalSupply += token_value;
    balances[token_address] += token_value;
}

    // burn function
function burn (address token_address, uint token_value) public{
    if (balances[token_address] >= token_value){
        totalSupply -= token_value;
        balances[token_address] -= token_value;
        }
    }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar and then click on the "Compile [file_name].sol" button. Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Under deployed contracts, you should see the token name, token abbreviation and current total supply of your choice.

To check if the code works as it should, copy the default address
and paste it under mint and mint an amount of your choice. Then, click on transact and check the total supply. Also, copy the address to the balances.

Now, try to burn tokens doing the same process. Check the total supply and balances if it has been reduced by the amount of your choice.

Lastly, try to check if you cannot burn more than what you have, the total supply and the balances should not change.

Thank you!

## Authors

Aziel Samaniego

202011004@fit.edu.ph
