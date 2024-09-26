Contract myToken
This is a basic Solidity contract for a token named "Meta" with the symbol "MTA". The contract includes two public variables, tokenName and tokenAbbrv, which hold the token's name and abbreviation, respectively. Additionally, the totalSupply variable tracks the total amount of tokens in circulation.

Overview
This program is a simple smart contract written in Solidity, the programming language used for developing decentralized applications on the Ethereum blockchain. It also includes a mapping variable. The contract provides two main functions: mint and burn. The mint function allows adding tokens to the total supply and to the balance of a specific address. The burn function enables the removal of tokens from the total supply and the balance of a given address, provided the address has a sufficient balance to cover the burn amount.

Getting Started
Running the Program
To execute this program, you can use Remix, an online IDE designed for Solidity. Head to the Remix platform at Remix Ethereum. Once there, create a new file by clicking the "+" button in the left-hand menu. Save the file with a .sol extension. Copy and paste the following code into the newly created file:

solidity
Copy code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {

    string public tokenName = "Meta";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    mapping(address => uint) public balances;

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
Compiling and Deploying
To compile the contract, click on the "Solidity Compiler" option in the left-hand menu. Ensure the "Compiler" version is set to "0.8.18" (or a compatible one), and then press the "Compile mytoken.sol" button. Once compiled, head over to the "Deploy & Run Transactions" section, select the "contract mytoken" from the dropdown, and click "Deploy" to deploy your contract.
