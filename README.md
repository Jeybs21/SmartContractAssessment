// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract SafeBank {
    // Mapping to keep track of each user's balance
    mapping(address => uint256) public balances;

    // Event to log deposits
    event Deposit(address indexed user, uint256 amount);

    // Event to log withdrawals
    event Withdrawal(address indexed user, uint256 amount);

    // Function to deposit Ether into the bank
    function deposit() public payable {
        require(msg.value > 0, "Deposit amount must be greater than zero");

        // Update the balance of the sender
        balances[msg.sender] += msg.value;

        // Emit a deposit event
        emit Deposit(msg.sender, msg.value);
    }

    // Function to withdraw Ether from the bank
    function withdraw(uint256 _amount) public {
        require(_amount > 0, "Withdrawal amount must be greater than zero");
        require(balances[msg.sender] >= _amount, "Insufficient balance");

        // Update the balance of the sender
        balances[msg.sender] -= _amount;

        // Transfer the amount to the sender
        (bool success, ) = msg.sender.call{value: _amount}("");
        require(success, "Withdrawal failed");

        // Emit a withdrawal event
        emit Withdrawal(msg.sender, _amount);
    }

    // Function to check the contract's balance
    function checkContractBalance() public view returns (uint256) {
        // Use assert to check for an invariant condition
        uint256 contractBalance = address(this).balance;
        assert(contractBalance >= 0);
        return contractBalance;
    }

    // Function to force a revert for demonstration purposes
    function forceRevert() public pure {
        // Force a revert with a custom error message
        revert("This is a forced revert for demonstration purposes");
    }
}
