Flash Token
===========

Flash Token (**$FLASH**) is an Ethereum token that enables interacting with the Flash Protocol. 

FLASH contract address is: **0x20398ad62bb2d930646d45a6d4292baa0b860c1f**

The Flash Token does not have a fixed supply. **$FLASH** is minted on every stake and it's burned on every unstake (only if the staking period has not been elapsed).
The process of minting can only be achieved using the Flash Protocol.

The inflation rate of the token is corelated to the usage of Flash protocol, the **FPY** (Flash Percentage Yield) and the matching ratio.

The token follows the ERC20 standard with few extensions:
    - ERC-3009 - transfer with authorization, which enables gasless transactions
    - an exposed mint() and burn() functions which can be invoked only by the flash protocol
