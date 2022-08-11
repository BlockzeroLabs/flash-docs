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
    Both FlashBack and FlashBackLM contracts have fixed Staking and Reward tokens. They also have fixed minimum and
    maximum durations. None of these variables can be changed after deployment.

The reward a given stake is entitled to is calculated as shown when staking Flash for Flash (FlashBack):

.. math::
    reward = \frac{((duration**2) * (maxAPR * stakedTokens))} {(10000 * 994519296000000)}

The reward a given stake is entitled to is calculated as shown when staking Flash LP tokens for Flash (FlashBackLM):

.. math::
    reward = \frac{((flashInLP * 2) * \frac{((duration**2) * (maxAPR * stakedTokens))} {(10000 * (31536000 * maximumStakeDuration))})} {lpTotalSupply}

.. important::
    In the event the above calculations are higher than remaining rewards, "reward" will be equal to remaining rewards.

The maxAPR is configurable by the Owner of the contract and can be increased or decreased at any point in time. The
maxAPR variable has been designed to be an integer between 1 and 10,000 which signifies 0.01% and 100%. This variable
can be configured to be higher than 10,000 which results in an annual return rate of over 100%.

The FlashBackLM contract has two additional variables that can be updated by the Owner: flashInLP and lpTotalSupply.

.. note::
    The changing of parameters such as maxAPR, lpTotalSupply and flashInLP only effect new stakes.

Users are able to unstake early at any point after the minimum staking duration has ended. The FlashBack and three FlashBackLM
contracts have their own minimum and maximum staking durations.
