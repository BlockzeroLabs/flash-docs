Burn fTokens (FlashBurn)
===============


.. important::
    The Strategy can implement arbitrary logic to determine the yield returned upon burning fTokens. The below is only
    true for strategies developed by the Flashstake team upon launch.


Strategy profits accumulate over time in a strategy's yield pool and can be claimed for upfront yield by burning fTokens
against the strategy through the Strategy smart contract.

The assets received are proportional to the relative ownership of that specific strategy's total fToken supply
and the size of the yield pool. This means a user who holds 45% of the total fToken supply can burn and redeem
these fTokens for 45% of all generated yield within the corresponding strategy.

.. note::
    Each time a Stake is made, new fTokens are minted. :doc:`You can read more about fTokens here. </core-concepts/ftokens>`

The formula to determine the number of tokens received as return upfront is denoted as:

.. math::

    Return_{upfront} = YieldPool * \frac{fToken_{burned}}{fToken_{totalSupply}}

Yield is typically referenced as a percentage of the employed capital and can be expressed as APR or APY.
The following formula represents the upfront APR calculation:

.. math::

    APR_{upfront} = \frac{Return_{upfront} * 31,536,000}{Deposit * StakeDuration_{(seconds)}}

