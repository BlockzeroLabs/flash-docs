Flash Strategies
===============

*Strategies* are yield generating vaults that contain arbitrary logic.
They can be registered with the Flash Protocol smart contract
if they adhere to the minimum requirements as laid out in our technical documentation.

On a technical level, a strategy consists of a smart contract inheriting the :doc:`Flash Strategy interface </smart-contracts/flash-strategy>`.
It uses one or more DeFi protocols (e.g. AAVE, Convex...) to stake a specific token (e.g. DAI, ETH...).
The :doc:`Flash Protocol </smart-contracts/flash-strategy>` uses the strategy to instantly mint fTokens when staking.

The registry of a new strategy in the Flashstake smart contract results in the creation of a strategy specific ERC20 token, called **fToken**.
This token facilitates the conversion of any type of yield into fixed upfront yield, representing the future yield of the deposit.

A typical strategy requires accounting for yield separately from users' principal.
This accounting separation of yield is referred to as “yield pool”.
If the yield of the underlying strategy is generated over time (for example through lending out the principal on spot lending markets)
the amount of yield available in the yield pool grows continuously.
The claiming process of upfront yield involves burning fToken for a proportional share of the yield pool.
For example, if a user owns 10% of the total supply of the strategy specific fToken and burns them against the yield pool,
the returned upfront yield is equal to 10% of capital in the yield pool.

Strategies only accept one input token (principal).
The same token must accumulate in the yield pool and be used as upfront yield.
If a strategy involves yield farming, where one or more third party tokens are collected,
then the strategy needs to ensure conversion back into the principal token to make it available in the yield pool.
