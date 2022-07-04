Flashback
-------------

Flashbacks are a way to reward FLASH token holders,
by allowing them to stake their FLASH to receive yield in FLASH. Unlike Flashstakes,
Flashbacks are not about receiving upfront yield: the rewards are received only after the staking time is over.

Flashbacking is as easy as Flashstaking. Just follow these five easy steps:

#. `Select the staking amount`_
#. `Select the staking duration`_
#. `Check the rewards`_
#. `Approve tokens to the smart contract`_
#. `Start your Flashback`_


In this page, we'll go over each of these steps in detail.

.. _Select the staking amount:

.. image:: /images/flashback/amount.png
    :alt: Amount field
    :align: center

This first field lets you select the amount of FLASH you wish to Flashback.
You may directly select 25%, 50% or all of the FLASH balance in your wallet with the bottom buttons.
The amount must be greater than 0 and lower or equal to your wallet's FLASH balance.

.. _Select the staking duration:

.. image:: /images/flashback/duration.png
    :alt: Duration field
    :align: center

This second field lets you select how much time your Flashback will last.
You will receive your FLASH rewards only after the time you select here, when the stake is finished.

The only time unit available is days, and the value may range from 10 days to 365 days,
as defined in the Flashback smart contract.

.. _Check the rewards:

Once a valid staking amount and staking duration have been selected,
the FLASH rewards are automatically displayed as the third step, and update whenever the amount or time is changed.

.. image:: /images/flashback/rewards.png
    :alt: Rewards field
    :align: center

.. note::
    In the Flashback smart contract, FLASH rewards are calculated using this formula (simplified):
    amount * (rewardRate * duration), where rewardRate is a constant set so that,
    if the duration is 365 days, rewardRate * duration equals 1.
    This means that if you stake for one year, your rewards will be equal to the amount you staked i.e. you get a 100% APR.

.. _Approve tokens to the smart contract:

To enable the Flashback smart contract to stake your FLASH, you need to give it permission to use your FLASH.
To do this, simply click the APPROVE $FLASH button and validate the approval with your wallet.

.. _Start your Flashback:

Once a valid staking amount and duration have been entered,
and the approval for the stake token and fToken have been granted to the Flash Protocol,
it is possible to click the Flashstake button to create a Flashstake.
All that is required in this step is validating the transaction with your wallet.

Et voilà, your first Flashstake has been created! Check your wallet to see the instant rewards you just received.

To see your Flashstake(s) click on STAKE DASHBOARD at the bottom of the box.
You might have to refresh the page to update the list and see your newly create Flashstake.
:doc:`More on the Dashboard in the next page! </user-interface/flashback-dashboard>`
