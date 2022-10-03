# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a script that deploys that contract.

Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat run scripts/deploy.js
```

uniswap v1 只允许ERC20和ETHER之间交换

Token.sol创建一个ERC20标准代币

Exchange.sol创建交易所智能合约
>其中getAmount函数代表的数学公式为

>当存入ether换取token的时候 $(e+\Delta e)*(t-\Delta t)=e*t$,解得$(\Delta t)=(t*\Delta e)/(e + \Delta e)$

>当存入token换取ether的时候 $(e-\Delta e)*(t+\Delta t)=e*t$,解得$(\Delta e)=(e*\Delta t)/(t + \Delta t)$
