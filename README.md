# Project Title

Solidity Smart Contract

## Description

This project consists of a Solidity smart contract named JBSmartContract, which serves as an educational example for understanding error handling mechanisms in Solidity. The contract includes functions to demonstrate the usage of require(), assert(), and revert() statements for input validation and error handling. Users can interact with the contract to set and retrieve a value, while the contract ensures that certain conditions are met before executing the desired operations.

## Getting Started

### Installing

To use this contract, follow these steps:

Download or copy the provided Solidity contract code.
Open a Solidity development environment such as Remix IDE.

### Executing program

Follow these steps to deploy and interact with the contract:

Deploy the contract:

Compile the JBSmartContract.sol file using the Solidity compiler.
Deploy the contract on an Ethereum network of your choice (e.g., JavaScript VM, Rinkeby, etc.).
Interacting with the contract:

Use the provided functions to interact with the contract:
setValue(uint256 _newValue): Set a new value for the value state variable. Ensure that the new value is greater than zero.
assertExample1(uint256 _num): Test the assert() statement functionality by providing a non-zero number.
revertExample1(uint256 _num): Test the revert() statement functionality by providing a non-zero number.

// Deploy the contract
deploy();

// Set a new value (replace <newValue> with a non-zero number)
setValue(<newValue>);

// Test assert functionality (replace <num> with a non-zero number)
assertExample1(<num>);

// Test revert functionality (replace <num> with a non-zero number)
revertExample1(<num>);


## Help

If you encounter any issues while deploying or interacting with the contract, ensure the following:

Use the correct Solidity compiler version (0.8.0 or above).
Provide non-zero values where required.
Check the Remix console for detailed error messages if the contract functions do not behave as expected.

## Authors

*John Benedict Miranda


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
