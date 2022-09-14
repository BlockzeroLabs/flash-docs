FlashStake
===============

It takes only a few simple steps to create a Flashstake and receive instant yield:

#. `Select the staking amount`_
#. `Select the staking duration`_
#. `Check the rewards`_
#. `Approve tokens to the smart contract`_
#. `Start your Flashstake`_


In this page, we'll go over each of these steps in detail.

.. note::
    This page explains how to create a simple Flashstake, with our default strategy (DAI-AAVE).
    Other strategies are available, as well as more advanced staking options, in the Advanced mode.


.. _Select the staking amount:

Select the staking amount
~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. image:: /images/flashstake/amount.png
    :alt: Amount field
    :align: center

This first field lets you select the amount of tokens that you wish to Flashstake.
You may directly select 25%, 50% or all of the tokens in your wallet with the bottom buttons.
The amount must be greater than 0 and lower or equal to your wallet balance.

On the right side is the ticker and logo of the token that will be Flashstaked.
Which token it is depends on the strategy: for the default strategy, WETH-AAVE, the default token is WETH.

.. tip::
    By clicking on the token's logo on the right side of the field,
    you can access the strategy selection modal. :doc:`More on strategy selection here. </user-interface/flashstake-advanced-mode>`

.. image:: /images/flashstake/wethToggle.png
    :alt: Amount field
    :align: center

If the selected strategy's stake token is WETH (or the wrapped version of the network's native token if you not on mainnet),
you have the option to stake ETH instead of WETH. To do this, simply switch the toggle from WETH to ETH.

.. note::
    If you choose to stake ETH, before signing your flashstaking transaction, you will have to sign a wrapping transaction,
    to convert the amount of ETH you wish to stake into WETH. Therefore, you will be making two transactions instead of one.

.. _Select the staking duration:

Select the staking duration
~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. image:: /images/flashstake/duration.png
    :alt: Duration field
    :align: center

This second field lets you select how much time your Flashtake will last.
No matter how long you decide to make your Flashstake, you will receive the rewards outright.

You can select any time in minutes, hours or days, so long as it is under the maximum duration and above 60 seconds.

.. note::
    The maximum duration is different for each strategy. For the DAI-AAVE strategy (default), the maximum duration is 730 days.

.. _Check the rewards:

Check the rewards
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Once a valid staking amount and staking duration have been selected,
the instant rewards are automatically displayed as the third step,
and update whenever the amount or time is changed.

.. image:: /images/flashstake/rewards.png
    :alt: Rewards field
    :align: center

Your rewards are in the same token that you Flashstake,
and will be sent directly to your wallet when the Flashstake is created.

.. note::
    Flashstake Strategies start with very little to no yield available to users.
    Because of this, early adopters are rewarded with additional FLASH tokens when performing a Flashstake.

.. _Approve tokens to the smart contract:

Token approval
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Before Flashstaking, you need to give the Flash Protocol smart contract approval for the stake token.
To do so, simply click the "APPROVE [Token symbol]" button and validate the transaction with your wallet.

.. _Start your Flashstake:

Start your Flashstake
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once a valid staking amount and duration have been entered,
and the approval for the stake token and fToken have been granted to the Flash Protocol,
it is possible to click the Flashstake button to create a Flashstake.
All that is required in this step is validating the transaction with your wallet.

Et voilà, your first Flashstake has been created! Check your wallet to see the instant rewards you just received.

.. image:: /images/flashstake/dashboard.png
    :alt: Dashboard button
    :align: center

To see your Flashstake(s) click on STAKE DASHBOARD at the bottom of the box.
You might have to refresh the page to update the list and see your newly create Flashstake.
:doc:`More on the Dashboard in the next page! </user-interface/flashstake-dashboard>`
