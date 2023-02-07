Flashstake (Mint+Redeem)
===============

The Flashstake Protocol provides a feature called FlashStake which enables users to both stake their
principal tokens to :doc:`mint fTokens </core-concepts/ftokens>` and
:doc:`redeem the received fTokens for yield </core-concepts/flashburn>` in a single transaction.

The Flashstake function also gives users the option to set a slippage value to protect against frontrunning. This is
typically configured in the Flashstake Dapp Frontend.

Users can interact with the Flash Protocol and Stake principal tokens into one of the registered Strategies. The
strategy determines the number of fTokens to mint and the Flash Protocol mints these to the user's wallet.

.. note::
    fTokens represent the yield the user is entitled to.

    :doc:`You can read more about minting fTokens here. </core-concepts/ftokens>`

Users can then burn or swap these fTokens for some amount of instant upfront yield.

.. note::
    :doc:`You can read more about redeeming fTokens here. </core-concepts/flashburn>`
