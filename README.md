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


### 
