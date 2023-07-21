# MyToken Smart Contract

This is a simple ERC20 token smart contract called `MyToken`, deployed on the Ethereum blockchain. The smart contract allows minting and burning tokens, as well as tracking token balances for different addresses.

## Token Details

- Name: podcast
- Symbol: bit

## Functions

### Mint Tokens

The `mint` function allows the contract owner to create and distribute new tokens to specific addresses. It increases the total supply by the specified value and increases the balance of the recipient address by that amount.

solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}


### Burn Tokens

The `burn` function allows token holders to burn their own tokens, reducing the total supply and their own balance. It ensures that the balance of the sender is greater than or equal to the amount to be burned before proceeding.

solidity
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}


## Token Balances

The contract maintains a mapping of addresses to token balances using the `balances` mapping.

solidity
mapping(address => uint) public balances;


## Ownership Management

The contract does not include any specific ownership management functionality. By default, the contract deployer is considered the owner, and only the deployer can execute the `mint` and `burn` functions.

## License

This smart contract is licensed under the MIT License. You can find the full text of the license in the `LICENSE` file.

