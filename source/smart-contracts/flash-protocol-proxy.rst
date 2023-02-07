FlashProtocolProxy
===============
+------------+---------------------------------------------+
| Network    | Contract Address                            |
+============+=============================================+
| Ethereum   | 0xF597A396950f5fadAB570502dE3f780864fFc946  |
+------------+---------------------------------------------+
| Optimism   | 0x7Efcd4C1Ff21fFcBa1b6a245A9e385b4Ff45D6DD  |
+------------+---------------------------------------------+
| Goerli     | 0xd6965f5aeEa4B7Cf094C9F4103a1e7cD2727e84B  |
+------------+---------------------------------------------+

The FlashProtocolProxy smart contract, introduced as part of the CHRONOS update, provides supplementary functionality
to users by wrapping the Flashstake Protocol smart contract. This was necessary due to the immutable nature of the
Flashstake Protocol smart contract.

Specifically, this smart contract enables the following capabilities:

1. Stake and Flashstake ETH into a WETH strategy.
2. Sign token approvals for tokens that comply with EIP-2612 when staking and Flashstaking.
3. Automatically swap fTokens via a Uniswap V3 route during Flashstaking.
4. Automatically swap a portion of fTokens via a Uniswap V3 route and burn a portion of fTokens against the strategy when Flashstaking.
5. Automatically swap a portion of fTokens via a Uniswap V3 route and burn a portion of fTokens
6. Sign fToken approvals in conjunction with the actions described in 4 and 5 above.
7. Sign fToken approvals when burning against a strategy.
