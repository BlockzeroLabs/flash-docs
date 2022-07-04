F Tokens (Stake)
===============

An *fToken* is an ERC-20 token, created by the Flash protocol whenever a new strategy is registered. fTokens are specific
to a given strategy and represents the yield pool. This means 100% of the total fToken supply can be redeemed for
100% of the total yield in a given strategy.

Upon staking, it is possible for the user to mint a FlashNFT which will represent their stake. FlashNFT's can also be
created after the initial stake providing the Stake still has some number of Staked tokens.

.. danger::
    Transferring the FlashNFT means transferring all rights to the Stake. This means all staked tokens will belong to the
    new NFT owner.

The naming convention for fTokens that should be adhered to is based on the principal token and the first four letters
in the corresponding Strategy address - eg fDAI-0123. This is to ensure users can easily distinguish which underlying
Strategy a given fToken corresponds to.

.. important::
    Strategies have been designed to offer maximum flexibility which results in the possibility for custom strategies
    to have custom logic that determines how much of the yield pool is represented by the fToken, how many fTokens
    are minted and more!

Upon staking principal tokens with the :doc:`Flash Protocol </smart-contracts/flash-strategy>`, the protocol asks
the underlying Strategy for many fTokens to mint. These fTokens are then minted by the Flash Protocol and returned to
the user. If there is a fToken fee percentage specified in the Flash Protocol, this will be deducted from the total fTokens
minted with the fee being redirected into the Flash treasury and the remaining fTokens going to the user.

There is a hardcoded maximum of 20% the protocol can take in fees.

This means if a user stakes 1,000 principal tokens for 365 days the Flash Strategy could determine 1,000 fTokens should
be minted. If the Flash Protocol has a fToken fee of 20% set, 200 fTokens will be taken as the fee and the remaining
800 fTokens will go to the user.

Strategies typically use the number of principal tokens and time to determine how many fTokens should be minted.

.. important::
    The user can choose to Flashstake which involves burning these fTokens to redeem the underlying yield immediately.


The formula used to determine fToken created within strategies at launch:

.. math::

    fTokenamount = Deposit * StakeDuration_{(seconds)} * \frac{31,709,792,000}{10^{decimals}}

This means staking 1 principal token (18 decimals) for 365 days will result in 1 fToken being minted.

