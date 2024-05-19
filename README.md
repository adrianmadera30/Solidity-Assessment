MyToken Smart Contract

Overview

`MyToken` is a simple ERC-20-like token implemented in Solidity. This smart contract allows for basic token management functions including minting and burning tokens. The contract is written for the Ethereum blockchain and adheres to the Solidity version 0.8.18.

Features

- **Token Name:** 2KEN
- **Token Abbreviation:** 2KN
- **Total Supply:** Dynamic, initially set to 0
- **Minting:** Increase the total supply by creating new tokens and assigning them to an address
- **Burning:** Decrease the total supply by destroying tokens from an address balance

Public Variables

- **`tokenName`** (`string`): The name of the token (2KEN).
- **`tokenAbbrv`** (`string`): The abbreviation or symbol of the token (2KN).
- **`totalSupply`** (`uint`): The total number of tokens in circulation, initialized to 0.

Mappings

- **`balances`** (`mapping(address => uint)`): Keeps track of the number of tokens each address holds.

Functions

### mint

```solidity
function mint (address _address, uint _value) public
```

The `mint` function allows new tokens to be created and assigned to a specific address. This increases both the `totalSupply` and the balance of the specified address.

- **Parameters:**
  - `_address` (`address`): The address to which the new tokens will be assigned.
  - `_value` (`uint`): The number of tokens to be created.

- **Behavior:**
  - Increases `totalSupply` by `_value`.
  - Increases the balance of `_address` by `_value`.

### burn

```solidity
function burn (address _address, uint _value) public
```

The `burn` function allows tokens to be destroyed, effectively reducing the total supply and the balance of a specified address. This function can only be executed if the address has enough tokens to burn.

- **Parameters:**
  - `_address` (`address`): The address from which the tokens will be burned.
  - `_value` (`uint`): The number of tokens to be burned.

- **Behavior:**
  - Decreases `totalSupply` by `_value`.
  - Decreases the balance of `_address` by `_value`, but only if `_address` has at least `_value` tokens.

License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

Author
- Adrian B. Madera
