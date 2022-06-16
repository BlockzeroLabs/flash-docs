Protocol Overview
===================

The Flashstake protocol is a novel financial infrastructure that allows users to receive yield
on deposited assets instantly  with a fixed rate over a set  duration.

Key concepts
--------------

Strategy
^^^^^^^^^

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
The provided principal must always be returned as the same token at the end of the flashstaking period.


fToken
^^^^^^^

An *fToken* is an ERC-20 token, created through the FlashFTokenFactory contract,
using the FlashFToken contract (which is an ERC-20 contract), when a strategy is registered.

When staking with the :doc:`Flash Protocol </smart-contracts/flash-strategy>` fTokens are minted using the strategy's contract.
If you Flashstake your stake, then the minted fTokens are immediately burned for yield.
The amount of fToken tokens a user receives is dependent on the amount of both time and principal provided
Strategy creators can develop custom formulas that determine the minting of fToken to accommodate their strategy.
Once deployed, the Flashstake smart contract takes over the actual minting of fToken.

The minting scheme used in the strategies at launch is:

.. math::

    fTokenamount = Deposit * StakeDuration_{(seconds)} * \frac{31,709,792,000}{10^{18}}

Strategy profits accumulate over time in a strategy's yield pool and can be claimed for upfront yield by burning fToken against the strategy through the Flashstake smart contract.
The assets received are proportional to the relative ownership of that specific strategy's total fToken supply and the size of the yield pool.
The formula to determine the number of tokens received as return upfront is denoted as:

.. math::

    Return_{upfront} = YieldPool * \frac{fToken_{burned}}{fToken_{totalSupply}}

Yield is typically referenced as a percentage of the employed capital and can be expressed as APR or APY.
The following formula represents the upfront APR calculation:

.. math::

    APR_{upfront} = \frac{Return_{upfront} * 31,536,000}{Deposit * StakeDuration_{(seconds)}}