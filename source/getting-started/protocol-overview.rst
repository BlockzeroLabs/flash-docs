Protocol Overview
===================

.. image:: ../protocol-overview-sequence.png
    :alt: Protocol Overview (Sequence)
    :align: center

The Flashstake Protocol is a cutting-edge financial platform that allows users to effortlessly earn a fixed return
on their deposited assets **instantly and up-front**. By utilizing Flash Strategies that integrate with renowned protocols like
AAVE, Lido and Yearn, the protocol enables a dynamic marketplace that caters to the needs of different users,
whether they prioritize immediate yield or are willing to wait for higher returns.

To participate in the Flashstake process, users first choose a Flashstake Strategy and then proceed to Flashstake
by sending their principal tokens to the Flashstake Protocol. The Flashstake Protocol then transfers these tokens
to the selected Flashstake strategy, which redirects the tokens to an underlying protocol, such as AAVE, Lido, or
Yearn, where they begin to earn yield typically block by block. This process is referred to as staking,
as detailed :doc:`here </core-concepts/ftokens>`.

.. note::
    The principal deposited into the Flashstake Protocol can be represented by a unique, non-fungible
    token (:doc:`FlashNFT </core-concepts/flashnft>`) that enables the transfer of stake ownership between wallets.

The upfront yield rate (APR) is determined by several factors, including the staked token quantity, stake duration,
available yield in the related Flashstake Strategy's yield pool, and the availability of more efficient yield
redemption routes. All available options are evaluated to ensure the Flashstaker receives the highest possible
APR, as described in the process referred to as FlashBurn, which is detailed :doc:`here </core-concepts/flashburn>`.

.. note::
    **Flashstakers have the option to unstake early by returning a proportional amount of the instant up-front
    yield in the form of fTokens.**

    For instance, consider the case of Bob, who Flashstakes 1,000 USDC for 365 days and mints approximately
    1,000 fUSDC, which he redeems for yield through the most efficient route. If Bob decides
    to unstake after only one month, he must return 900 fTokens to withdraw his initial 1,000 USDC, as the
    number of fTokens required to be returned is directly proportional to the amount of time that has elapsed.

    It's important to note that when redeeming yield through any route, the fTokens will leave Bob's wallet since
    fTokens are the entitlement to yield.

This is a high-level overview of the Flashstake Protocol and does not cover the detailed intricacies
involved in the process of :doc:`staking </core-concepts/ftokens>` to mint fTokens or
:doc:`redeeming </core-concepts/flashburn>` these for yield.

For a comprehensive understanding of the Flashstake Protocol, please refer to the core concepts linked below.

#. :doc:`Flash Strategies </core-concepts/strategies>`
#. :doc:`Minting fTokens </core-concepts/ftokens>`
#. :doc:`Redeeming fTokens </core-concepts/flashburn>`
#. :doc:`Flashstake (Mint+Redeem) </core-concepts/flashstake>`

