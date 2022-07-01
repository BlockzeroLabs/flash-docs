F Tokens
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
    Custom strategies developed by external developers can have any arbitrary logic which determines how much of the yield
    pool is represented by the fToken!

Upon staking principal tokens with the :doc:`Flash Protocol </smart-contracts/flash-strategy>`, the protocol asks
the underlying Strategy how many fTokens to mint. These fTokens are then minted by the Flash Protocol and returned to
the user.

.. note::
    The :doc:`Flash Protocol </smart-contracts/flash-strategy>` can take up to a maximum of 20% fee upon minting fTokens.

Strategies typically use the number of principal tokens and time to determine how many fTokens should be minted.

.. important::
    The user can choose to Flashstake which involves burning these fTokens to redeem the underlying yield immediately.


The formula used to determine fToken created within strategies at launch:

.. math::

    fTokenamount = Deposit * StakeDuration_{(seconds)} * \frac{31,709,792,000}{10^{18}}

This means staking 1 principal token (18 decimals) for 365 days will result in 1 fToken being minted.
