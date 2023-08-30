# Token-Creation
MyToken is an Ethereum-based ERC-20 token contract that allows for minting and burning tokens. It follows the standard ERC-20 specifications while providing additional functionality for creating and destroying tokens.
# Description
Custom Token Details: The contract includes public variables to store essential details about the token:

tokenName: A string representing the name of the token (e.g., "Meta").
tokenAbbrv: A string for the token's abbreviation (e.g., "met").
totalSupply: An unsigned integer tracking the total supply of the token.
Balance Tracking: The contract maintains a mapping that associates Ethereum addresses with their respective token balances:

balances: A mapping where addresses are keys and their corresponding token balances are values.
Mint Functionality: The contract introduces a mint function that allows the contract owner to create new tokens. The function takes two parameters:

_address: The Ethereum address to which the newly minted tokens will be credited.
_value: The amount of tokens to be minted and added to the total supply and the balance of _address.
Burn Functionality: The contract includes a burn function that empowers the contract owner to destroy tokens. This function takes two parameters:

_address: The Ethereum address from which tokens will be debited.
_value: The quantity of tokens to be burned, resulting in a reduction of the total supply and _address balance.
Safety Checks: The burn function features conditional checks to ensure that token burning only occurs when the sender's balance is equal to or greater than the specified burn amount. This prevents unauthorized token destruction.

Events for Transparency: The contract emits events for both minting and burning tokens, allowing external observers to track these operations:

TokensMinted: Emitted when tokens are minted, providing details about the account and amount minted.
TokensBurned: Emitted when tokens are burned, indicating the account and amount burned.
Owner Access Control: The contract includes an ownership mechanism through a modifier onlyOwner, ensuring that only the contract owner can execute certain functions, such as minting and burning tokens.
# Getting Started
This guide will walk you through the process of deploying and interacting with the MyToken Solidity smart contract on the Ethereum blockchain. Follow these steps to get started:

Prerequisites
Before you begin, ensure you have the following prerequisites:

An Ethereum wallet: You can use wallets like MetaMask or other Ethereum-compatible wallets.
Solidity development environment: Install the necessary tools to compile and interact with Ethereum smart contracts.
# Deployment
Clone the repository to your local machine using the following command:

git clone https://github.com/naavy-jain/Token-Creation
Navigate to the cloned directory:

bash
Copy code
cd Token-Creation
Compile the Solidity contract using your preferred Solidity compiler. You can use tools like Remix or local development environments like Truffle or Hardhat.

Deploy the compiled contract to the Ethereum blockchain using a development network or a testnet. Make sure to note the deployed contract's address for future interactions.
# License
This license is licensed under the MIT License -see the LICENSE.txt file for details.
