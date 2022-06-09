Create a Flashstake
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
-----------------------

.. image:: /images/flashstake/amount.png
    :alt: Amount field
    :align: center

This first field lets you select the amount of tokens that you wish to Flashstake.
You may directly select 25%, 50% or all of the tokens in your wallet with the bottom buttons.
The amount must be greater than 0 and lower or equal to your wallet balance.

On the right side is the ticker and logo of the token that will be Flashstaked.
Which token it is depends on the strategy: for the default strategy, DAI-AAVE, the default token is DAI.

.. note::
    **Coming soon**: Users will be able to select a different staked token than the strategy's default,
    by clicking on the token's logo on the right side of the field.

.. _Select the staking duration:

Select the staking duration
-----------------------

.. image:: /images/flashstake/duration.png
    :alt: Duration field
    :align: center

This second field lets you select how much time your Flashtake will last.
No matter how long you decide to make your Flashstake, you will receive the rewards outright.

You can select any time in minutes, hours or days, so long as it is under the maximum duration and above 0.

.. note::
    The maximum duration is different for each strategy. For the DAI-AAVE strategy (default), the maximum duration is 730 days.

.. _Check the rewards:

Check the rewards
-----------------------

Once a valid staking amount and staking duration have been selected,
the instant rewards are automatically displayed as the third step,
and update whenever the amount or time is changed.

.. image:: /images/flashstake/rewards.png
    :alt: Rewards field
    :align: center

Your rewards are in the same token that you Flashstake,
and will be sent directly to your wallet when the Flashstake is created.

.. note::
    In the first few weeks after Flashstake's release, the rewards are not necessarily going to be 100% in the staked token, 
    because the token's amount in our pool might not be enough.
    To make up for this, the percentage of the rewards that cannot be delivered in the staked token will be delivered as an amount of FLASH tokens of equal value to the missing part.
    This partition will disappear once there is enough tokens in our pool.

.. _Approve tokens to the smart contract:

Token approval
-----------------------

Before Flashstaking, you need to give the Flash Protocol smart contract approval for two tokens:
the stake token and the fToken. The fToken is an ERC-20 token of equal value to the stake token;
for example, one fDAI equals one DAI. When you Flashstake,
the Flash Protocol mints and burns fTokens to generate the instant yield.

To approve the stake token, simply click the "APPROVE [Token symbol]" button and validate the transaction with your wallet.
Once this approval is granted, the button changes to "APPROVE f[Token symbol]".
To approve the fToken, click this button and validate the transaction with your wallet. Once both approvals are granted,
the Flashstake button become enabled.

.. _Start your Flashstake:

Start your Flashstake
-----------------------

Once a valid staking amount and duration have been entered,
and the approval for the stake token and fToken have been granted to the Flash Protocol,
it is possible to click the Flashstake button to create a Flashstake.
All that is required in this step is validating the transaction with your wallet.

Et voilà, your first Flashstake has been created! Check your wallet to see the instant rewards you just received.

To see your Flashstake(s) click on STAKE DASHBOARD at the bottom of the box.
You might have to refresh the page to update the list and see your newly create Flashstake.
:doc:`More on the Dashboard in the next page! </flashstake/flashstake-dashboard>`
