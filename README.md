# MyToken

MyToken is a simple ERC-20-like token implemented in Solidity. It allows for basic token functionalities such as minting and burning tokens.

## Requirements

1. **Public Variables**: The contract has public variables that store details about the token:
    - Token Name
    - Token Abbreviation
    - Total Supply
2. **Mapping of Addresses to Balances**: The contract maintains a mapping to keep track of balances for each address.
3. **Mint Function**: The contract includes a mint function to increase the total supply and the balance of a specified address.
4. **Burn Function**: The contract includes a burn function to decrease the total supply and the balance of a specified address. It includes conditionals to ensure that the balance is sufficient to burn the specified amount.

## Contract Details

### Public Variables

- `string public tokenName = "Student";`
- `string public tokenAbbrv = "Stu";`
- `uint public totalSupply = 0;`

### Mapping

- `mapping (address => uint) public balances;`

### Mint Function

The mint function allows for increasing the total supply and the balance of the specified address.

```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}

function burn(address _address, uint _value) public {
    if(balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
