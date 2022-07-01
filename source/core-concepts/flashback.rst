FlashBack
===============

FlashBack allows users to choose some number of ERC-20 tokens and the duration they wish to stake for. These
parameters are used to determine how many ERC-20 reward tokens are reserved for the Stake. The reward is always paid out
at the end of the Stake. FlashBack stakes can be withdrawn at any point in time however if this is done before the staking
period ends, all reward tokens are forfeited and only Staked tokens are returned.

The Staking token and Reward token can be the same ERC-20 token or different.

.. note::
    Each FlashBack contract has a fixed Stake token and Reward token.

The reward a given stake is entitled to is calculated as shown:

.. math::
    reservedReward = \frac{(stakedTokens * (rewardRate * durationSecs))}{(10**18)}

.. important::
    In the event the above calculation is higher than remaining rewards, reservedReward will be equal to remaining rewards.

The rewardRate is configurable by the Owner of the contract and can be increased or decreased at any point in time.

.. note::
    Increasing/decreasing rewardRate only effects new Stakes.
