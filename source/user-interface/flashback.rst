Flashback
-------------

Flashbacks are a way to reward FLASH token holders,
by allowing them to stake their FLASH to receive yield in FLASH. Unlike Flashstakes,
Flashbacks are not about receiving upfront yield: the rewards are received only after the staking time is over.

Flashbacking is as easy as Flashstaking. Just follow these five easy steps:

#. `Select the stake token`_
#. `Select the staking amount`_
#. `Select the staking duration`_
#. `Select the best LP tier`_
#. `Check the rewards`_
#. `Approve tokens to the smart contract`_
#. `Start your Flashback`_


In this page, we'll go over each of these steps in detail.

.. _Select the stake token:

Select the stake token
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: /images/flashback/selectModal.png
    :alt: Select token modal
    :align: center

There are two tokens available for Flashbacking: FLASH tokens and ETH/FLASH Liquidity Pool tokens (referred here as *LP*).
By default, FLASH is selected. You can change the staking token by clicking the dropdown at the top of the page.
This opens a modal from which you can select either FLASH or LP.

.. hint::
    There is one smart contract for Flashbacking FLASH, but three separate ones for Flashbacking LP,
    each corresponding to a different tier.
    To select either of the three tiers, see :ref:`this part <Select the best LP tier>`.

.. _Select the staking amount:

Select the staking amount
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: /images/flashback/amount.png
    :alt: Amount field
    :align: center

This first field lets you select the amount of FLASH you wish to Flashback.
You may directly select 25%, 50% or all of the FLASH balance in your wallet with the bottom buttons.
The amount must be greater than 0 and lower or equal to your wallet's FLASH balance.

.. _Select the staking duration:

Select the staking duration
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: /images/flashback/duration.png
    :alt: Duration field
    :align: center

This second field lets you select how much time your Flashback will last.
You will receive your FLASH rewards only after the time you select here, when the stake is finished.

The only time unit available is days, and the value may range from 10 days to 365 days,
as defined in the Flashback smart contract.

.. _Select the best LP tier:

Select the best LP tier
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. note::
    This part only applies to **staking LP**, not to staking FLASH.
    :ref:`You can select the staking LP option here <Select the stake token>`.

.. image:: /images/flashback/tier.png
    :alt: LP tier selection
    :align: center

In this part, you can select either of the three LP Flashback contracts, referred to a *tiers*.
Tier 1 is selected by default.
Tiers may have a different APRs and max/min durations from one another.
Therefore, you may select the tier that best fits your needs in terms of staking time or APR.

.. _Check the rewards:

Check your rewards
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once a valid staking amount and staking duration have been selected,
the FLASH rewards are automatically displayed as the third step, and update whenever the amount or time is changed.

.. image:: /images/flashback/rewards.png
    :alt: Rewards field
    :align: center

.. _Approve token to the smart contract:

Approve token to the smart contract
~~~~~~~~~~~~~~~~~~~~~~~~~~~

To enable the Flashback smart contract to stake your FLASH or LP, you need to give it permission to use your FLASH or LP.
To do this, simply click the APPROVE button and validate the approval with your wallet.

.. note::
    The approval of LP only counts towards a specific tier contract.
    To Flashback with another tier you will have to approve LP separately.

.. _Start your Flashback:

Start your Flashback
~~~~~~~~~~~~~~~~~~~~~~~~~~~

To see your Flashback(s) click on STAKE DASHBOARD at the bottom of the box.
You might have to refresh the page to update the list and see your newly created Flashback.
:doc:`More on the Dashboard in the next page! </user-interface/flashback-dashboard>`
