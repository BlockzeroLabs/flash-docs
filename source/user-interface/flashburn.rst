FlashBurn
=============

If you hold fTokens (like fDAI), you can burn them for yield at anytime.
Indeed, holding fTokens make you entitled to a portion of the yield pool of a certain strategy.
The more fTokens you burn, the bigger portion of the yield pool you shall receive in your wallet.

And that's exactly what the Flashburn allows you to do! You just need to follow these steps:

#. `Select a strategy`_
#. `Select the amount to burn`_
#. `Change the slippage tolerance`_
#. `Approve fToken`_
#. `Launch Flashburn`_

.. _Select a strategy:

Select a strategy
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. note::
    Each strategy has one principal token and its unique yield pool and fToken.
    Make sure you burn the fToken for the related strategy to receive the desired yield.

To select a strategy, simply click the strategy dropdown, which opens a modal listing all the available strategies.
You can search them by name or address using the search bar.

.. image:: /images/flashburn/strategy.png
    :alt: strategies
    :align: center

.. _Select the amount to burn:

Select the amount to burn
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: /images/flashburn/amount.png
    :alt: amount field
    :align: center

In the burn amount field, select the amount of fTokens you'd like to burn for yield.
The value needs to be higher than zero and lower or equal to your fToken balance.
You can directly select 25%, 50% or all of your balance with the bottom buttons.

.. _Change the slippage tolerance:

Change the slippage tolerance
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Having a slippage tolerance for Flashburns is necessary, in case multiple users try to Flashburn at the same time.
That is because the frontend is sending the minimum returned yield to the smart contract (equal to the amount displayed in the reward box),
but if other users Flashburn in the time between reward estimation and Flashburning, the supply changes,
and therefore the minimum returned yield isn't up to date anymore, causing the Flashburn transaction to fail.
By selecting a slippage tolerance percentage,
you lower the chances of such failure by taking into account the possibility the minimum returned yield may end up lower.

To change the slippage tolerance, click on the cogwheel icon that is on Connect Wallet button,
at the right side of your truncated address.

.. image:: /images/flashburn/cogwheel.png
    :alt: cog icon
    :align: center

The slippage tolerance is set to 0.1% by default.
If you set it lower than 0.1%, the transaction may fail for above-mentioned reasons.
However, do not set it too high, else you may end up receiving an unsatisfying reward.

.. image:: /images/flashburn/slippage.png
    :alt: slippage tolerance
    :align: center

.. hint::
    You can use the buttons to select a slippage percentage (0.1, 0.5, 1 or 5),
    or edit it by typing in the text field directly.
    Don't forget to click confirm for the slippage change to go into effect.

.. _Approve fToken:

Approve fToken
~~~~~~~~~~~~~~~~~~~~~~~~~~~

For the strategy's smart contract to be able to burn your fTokens,
you need to grant it permission by clicking the APPROVE fTOKEN button and validate the approval with your wallet.

.. note::
    The approval of a fToken only counts towards a specific strategy.
    To Flashburn with another strategy you will have to approve the corresponding fToken separately.

.. _Launch Flashburn:

Flashburn your fTokens
~~~~~~~~~~~~~~~~~~~~~~~~~~~

To Flashburn, one a valid amount and slippage tolerance have been entered and the strategy's contract was given approval for fTokens,
simply click the FLASHBURN button and validate the transaction with your wallet.
You should see your principal token balance increase and your fToken balance decrease accordingly.
