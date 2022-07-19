FlashBack
===============

.. important::
    FlashBack has been designed to help bootstrap the Flashstake Protocol and as such may not be available
    after the initial launch.


FlashBack allows users to choose some number of ERC-20 tokens and the duration they wish to stake for. These
parameters are used to determine how many ERC-20 reward tokens are reserved for the Stake. The reward is always paid out
at the end of the Stake. FlashBack stakes can be withdrawn at any point in time however if this is done before the staking
period ends, all reward tokens are forfeited and only Staked tokens are returned.

This means a user could choose to Stake 10,000 tokenA for an agreed 5,000 tokenB reward. The user can choose to unstake
at any point in time but when unstaking before the agreed duration is completed, all 5,000 reward tokens will be forfeited
and the user will get back their original 10,000 staked tokens.

The Staking token and Reward token can be the same ERC-20 token or different.

.. note::
    Each FlashBack contract has a fixed Stake token and Reward token.

The reward a given stake is entitled to is calculated as shown:

.. math::
    reservedReward = \frac{((duration**2) * (maxAPR * stakedTokens))} {(10000 * 994519296000000)}

.. important::
    In the event the above calculation is higher than remaining rewards, reservedReward will be equal to remaining rewards.

The maxAPR is configurable by the Owner of the contract and can be increased or decreased at any point in time. The
maxAPR variable has been designed to be an integer between 1 and 10,000 which signifies 0.01% and 100%. This variable
can be configured to be higher than 10,000 which results in an annual return rate of over 100%.

.. note::
    Increasing/decreasing maxAPR only effects new Stakes.
