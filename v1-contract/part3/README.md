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

uniswap v1 part1 只允许ERC20和ETHER之间交换

Token.sol创建一个ERC20标准代币

Exchange.sol创建交易所智能合约
>其中getAmount函数代表的数学公式为

>当存入ether换取token的时候 $(e+\Delta e)*(t-\Delta t)=e*t$,解得$(\Delta t)=(t*\Delta e)/(e + \Delta e)$

>当存入token换取ether的时候 $(e-\Delta e)*(t+\Delta t)=e*t$,解得$(\Delta e)=(e*\Delta t)/(t + \Delta t)$

***

uniswap v1 part2

addLiquidity()添加流动性不能随意添加。

>如果还没有对应流动性池，可以随意加入代币。

>如果已经有对应的流动性池子，就需要按照当前池子内的ether和token代币的储备比率来添加。

为提供流动性的用户提供一定的激励。使用的方法是给流动性提供者提供LP-Token。

在每一次交易中收取1%作为手续费。
>当存入ether换取token的时候 从$(\Delta t)=(t*\Delta e)/(e + \Delta e)$变成$(\Delta t)=(t*\Delta e * 99)/(e * 100 + \Delta e * 99)$

>当存入token换取ether的时候 从$(\Delta e)=(e*\Delta t)/(t + \Delta t)$变成$(\Delta e)=(e*\Delta t * 99)/(t * 100 + \Delta t * 99)$

***

uniswap v1 part3

添加Factory contract