# Module-Challenge-20
## Step 1: Create a Joint Savings Account Contract in Solidity
### We start by creating contract named JointSavings, with five distinct variables: address payable accountOne; address payable accountTwo; address public lastToWithdraw; uint public lastWithdrawAmount; and lastly uint public contractBalance;. 

### Within the contract withdraw function, the following code was included to require the input to be one of the two appropriate accounts, check for valid balances within the accounts, make appropriate balance checks, transfer the withdrawal amount, and settle the address balances:

### function withdraw(uint amount, address payable recipient) public {

  
###        require(recipient == accountOne || recipient == accountTwo, "You don't own this account!");
  
###        require(contractBalance > amount, "Insufficient funds!");

     
###        if (lastToWithdraw != recipient) {
###            lastToWithdraw = recipient;
###        }

        
###        recipient.transfer(amount);

        
###        lastWithdrawAmount = amount;

        
###        contractBalance = address(this).balance;
###    }


### We next make a public payable function named deposit, with the same contractBalance = address(this).balance within the function as above.

### We next make a public function named setAccounts that receive the two 'address payable' arguments as account1 and account2. Lastly to finish the code, we add the default fallback function for ether sent from outside the deposit function with:

### function() external payable {
        
###    }

## Step 2: Compile and Deploy Your Contract in the JavaScript VM 
### Please see screenshots

## Step 3: Interact with Your Deployed Smart Contract
### Please refer to screenshots
### Note: I am missing the screenshot for the 5 eth withdrawal contract balance, but do have the 10 eth one to show the process validation. 
