# Simple Lottery Contract

A decentralized lottery smart contract that allows users to enter the lottery by sending Ether and enables the contract owner to draw a random winner.

## Description

This project is a smart contract written in Solidity for a simple lottery system. Participants enter the lottery by sending exactly 0.1 Ether. The contract owner can draw a winner once the lottery is active. The winner receives the entire balance of the contract. The contract uses require(), assert(), and revert() statements to ensure security and correctness.

## Getting Started

### Installing

Clone the repository:
sh
Copy code
git clone https://github.com/yourusername/simple-lottery.git
Navigate to the project directory:
sh
Copy code
cd simple-lottery
Install dependencies:
Ensure you have Node.js and npm installed. Then, run:
sh
Copy code
npm install
### Executing program

Deploy the contract:
Use Remix, Truffle, or Hardhat to deploy the SimpleLottery contract to your desired Ethereum network.
sh
Copy code
npx hardhat run scripts/deploy.js --network <network-name>
Enter the lottery:
Participants can enter the lottery by sending 0.1 Ether to the contract using the enter function.
sh
Copy code
npx hardhat console --network <network-name>
const Lottery = await ethers.getContractFactory("SimpleLottery");
const lottery = await Lottery.attach("your_contract_address");
await lottery.enter({ value: ethers.utils.parseEther("0.1") });
Draw a winner:
The contract owner can draw a winner using the drawWinner function.
sh
Copy code
await lottery.drawWinner();
End the lottery:
The contract owner can end the lottery if no players have entered.
sh
Copy code
await lottery.endLottery();


## Help

If you encounter any issues, ensure you have the correct versions of Node.js and npm installed. Common issues might include incorrect network configurations or insufficient Ether for transactions.

For more detailed debugging:

sh
Copy code
npx hardhat console --network <network-name>

## Authors

*John Benedict Miranda


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
