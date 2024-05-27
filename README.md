# Smart Contract
This Solidity program is a "Money Lending" smart contract. This program inherits from OpenZepelin ERC20 contract. This program has its main function, mint, burn, and transfer

## Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.

## Getting Started  
### How to run this program?
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., getLoan2.sol). Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract getLoan is ERC20 {
    address public loaner;

    constructor(string memory name, string memory symbol) ERC20(name, symbol) {
        loaner = msg.sender;
    }

    function mint(address to, uint256 amount) public {
        require(msg.sender == loaner, "Only the owner can mint tokens");
        _mint(to, amount);
    }

    function transfer(address recipient, uint256 amount) public override returns (bool) {
        return super.transfer(recipient, amount);
    }

    function approve(address spender, uint256 amount) public override returns (bool) {
        _approve(msg.sender, spender, amount);
        return true;
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }
}

```



To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Loan.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "getLoan2" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint, burn, approve, transfer, transferFrom, totalSupply, name, symbol, loaner, decimal, allowance, and balanceOf functions.


## Author
Daniel Burgos


## License
This project is licensed under the MIT License - see the LICENSE.md file for details


