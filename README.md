# Joint Savings Account Smart Contract - Readme

## Technologies Used:
Solidity: A programming language specifically designed for writing smart contracts on the Ethereum blockchain.

Remix IDE: An online Integrated Development Environment (IDE) for writing, testing, and deploying smart contracts on Ethereum.

JavaScript VM: A virtual environment in Remix IDE for compiling and deploying smart contracts for testing purposes.

## Languages Used:
Solidity: For writing the smart contract code.

JavaScript: For interacting with the deployed smart contract in the Remix IDE.

## Instructions:

### Step 1: Create a Joint Savings Account Contract in Solidity
Open the provided starter code file named joint_savings.sol in the Remix IDE.

Define a new contract named JointSavings.

Define the following variables in the new contract:

Two variables of type address payable named accountOne and accountTwo.
A variable of type address public named lastToWithdraw.
Two variables of type uint public named lastWithdrawAmount and contractBalance.
Define a function named withdraw that accepts two arguments: amount of type uint and recipient of type payable address. In this function, implement the following steps:

Use a require statement to check if the recipient is equal to either accountOne or accountTwo. If not, return the message "You don't own this account!"
Use a require statement to check if the contractBalance is sufficient for the withdrawal operation. If there are insufficient funds, return the message "Insufficient funds!"
Add an if statement to check if lastToWithdraw is not equal to recipient. If not equal, set lastToWithdraw to the current value of recipient.
Call the transfer function of the recipient, passing it the amount to transfer.
Set lastWithdrawAmount equal to amount.
Set the contractBalance variable equal to the balance of the contract using address(this).balance to reflect the new balance of the contract.
Define a public payable function named deposit. In this function, set the contractBalance variable equal to the balance of the contract using address(this).balance.

Define a public function named setAccounts that takes two address payable arguments, named account1 and account2. In the body of the function, set the values of accountOne and accountTwo to account1 and account2, respectively.

Add a fallback function so that your contract can store ether that’s sent from outside the deposit function.

### Step 2: Compile and Deploy Your Contract in the JavaScript VM
Compile your smart contract. If an error occurs, review your code, and make the necessary changes for a successful compilation.

In the Remix IDE, navigate to the "Deploy & Run Transactions" pane, and then make sure that "JavaScript VM" is selected as the environment.

Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.

### Step 3: Interact with Your Deployed Smart Contract
Now that your contract is deployed, it’s time to test its functionality! After each step, capture a screenshot of the execution, and then save it in a folder named Execution_Results. You’ll share this folder with your final submission.

To interact with your deployed smart contract, complete the following steps:

Use the setAccounts function to define the authorized Ethereum addresses that will be able to withdraw funds from your contract. You can use the provided dummy addresses or generate new ones using the Vanity-ETH website.

Dummy account1 address: 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb
Dummy account2 address: 0x7A1f3dFAa0a4a19844B606CD6e91d693083B12c0
Test the deposit functionality of your smart contract by sending the following amounts of ether. After each transaction, use the contractBalance function to verify that the funds were added to your contract:

Transaction 1: Send 1 ether as wei.
Transaction 2: Send 10 ether as wei.
Transaction 3: Send 5 ether.
Once you’ve successfully deposited funds into your contract, test the contract’s withdrawal functionality by withdrawing 5 ether into accountOne and 10 ether into accountTwo. After each transaction, use the contractBalance function to verify that the funds were withdrawn from your contract. Also, use the lastToWithdraw and lastWithdrawAmount functions to verify that the address and amount were correct.
