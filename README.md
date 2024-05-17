
# Token Smart Contract

## Overview

This repository contains a custom ERC20 token contract implemented using the OpenZeppelin library. The contract includes additional features such as minting, burning, transferring tokens, and changing ownership.

## Features

- **Minting**: Allows the owner to mint new tokens.
- **Burning**: Allows token holders to burn their tokens.
- **Ownership Management**: Allows the owner to transfer or renounce ownership.
- **Event Logging**: Emits events for key actions such as token transfers, minting, burning, and ownership changes.

## Contract Details

- **Name**: CustomToken
- **Symbol**: CTK
- **Decimals**: 18 (default for ERC20 tokens)
- **Initial Supply**: Set during contract deployment

## Contract Functions

### Public Variables

- `address public ownerAddress`: The address of the current owner of the contract.

### Events

- `event TokensMoved(address indexed sender, address indexed beneficiary, uint256 amount)`: Emitted when tokens are transferred, minted, or burned.
- `event OwnershipChanged(address indexed oldOwner, address indexed newOwner)`: Emitted when the ownership of the contract changes.

### Modifiers

- `modifier onlyOwner()`: Ensures that only the contract owner can call certain functions.

### Constructor

- `constructor(uint256 initialSupply)`: Deploys the contract with an initial supply of tokens and assigns ownership to the deployer.

### Functions

- `function mintTokens(address beneficiaryAddress, uint256 issuedAmount) external onlyOwner`: Mints new tokens to a specified address. Can only be called by the owner.
- `function burnTokens(uint256 destroyedAmount) external`: Burns a specified amount of the caller's tokens.
- `function transferTokens(address receiver, uint256 transferAmount) external returns (bool)`: Transfers a specified amount of tokens to another address.
- `function transferOwnership(address newOwner) external onlyOwner`: Transfers ownership of the contract to a new address. Can only be called by the owner.
- `function abandonOwnership() external onlyOwner`: Renounces ownership of the contract. Can only be called by the owner.

## Usage

### Minting Tokens

To mint new tokens, the owner can call the `mintTokens` function:

```solidity
mintTokens(address beneficiaryAddress, uint256 issuedAmount)
```

### Burning Tokens

To burn tokens, any token holder can call the `burnTokens` function:

```solidity
burnTokens(uint256 destroyedAmount)
```

### Transferring Tokens

To transfer tokens to another address, use the `transferTokens` function:

```solidity
transferTokens(address receiver, uint256 transferAmount)
```

### Transferring Ownership

To transfer ownership of the contract, the current owner can call the `transferOwnership` function:

```solidity
transferOwnership(address newOwner)
```

### Abandoning Ownership

To renounce ownership, the current owner can call the `abandonOwnership` function:

```solidity
abandonOwnership()
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

