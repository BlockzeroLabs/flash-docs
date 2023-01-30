FAQ
===

**Basics**
----------

What is Flashstake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Flashstake is a permissionless protocol that allows anyone to earn instant upfront yield through various underlying
Flash Strategies.


How does Flashstake work?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
In a nutshell, each time a user stakes, they receive fTokens. These fTokens can be burned to proportionally redeem
yield in a given Flashstake strategy.

Example:

- Strategy A currently has 1,000,000 staked DAI tokens that are increasing the size of the "yield pool" every block
thanks to the underlying protocol (eg AAVE, Yearn, etc)

- Strategy A's corresponding fToken total supply is currently 100,000

- Strategy A's yield pool currently has 45,000 DAI tokens

.. note::
    fTokens are a representation of yield within the Flash Protocol.

Alice stakes 100,000 DAI tokens for 365 days and receives 100,000 fTokens. The total supply of fTokens is now
200,000 which means Alice owns 50% of the entire fToken supply for Strategy A.

This allows Alice to redeem (and burn) 100,000 fTokens which will result in receiving 50% of the "yield pool" (or 22,500 DAI).

This means Alice staked 100,000 DAI tokens for 365 days, received 100,000 fTokens, redeemed these fTokens immediately
to get back 22,500 DAI tokens. At the end of Alice's stake, Alice will be able to unstake the original 100,000 DAI tokens.

This means Alice staked and earned instant upfront yield at a rate of 22.5%.


What is the “yield pool” and how does it increase?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The “Yield Pool” is a concept within each Flash Strategy and it refers to the total yield available in a given strategy.

The Flash strategies developed on launch will take the Staked tokens from users and deposit these into an underlying
protocol such as AAVE which results in yield (or interest) being earned over time (block by block). The total amount
of yield available is referred to as the "yield pool".

.. note::
    Each Flash strategy has its own "yield pool".

.. important::
    Staked funds always belong to the Staker and are never used to pay new users. This means there is zero
    chance of a bank run making the Flashstake Protocol default.


Are there benefits to not burning the fToken?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The fTokens within a Flash strategy represent ownership over the yield pool, which is directly tied to the performance
of the underlying protocol, such as AAVE. If interest rates on the underlying protocol increase, the growth rate of
the "yield pool" will also increase. This means that when fTokens are burned, the yield rate received will also increase.

If the underlying protocol interest rate jumps from 5% to 10%, this means that all the TVL in a given Flashstake
strategy will now earn double the interest over time. As a result, the yield pool will grow at twice the speed. Despite
this, fToken holders will still have the same percentage ownership of the yield pool, effectively doubling the
value of their fTokens.

.. important::
    The upfront yield rate can fluctuate up or down over time.

How is the APY/APR determined?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The APY/APR is not determined by the Flashstake Protocol but instead based on the size of the "yield pool" within a
given strategy. This means the APY/APR is entirely dependent on the "yield pool" for a given strategy.


How does the protocol handle staking time?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol relies on using block timestamps rather than locking for a number of blocks.

This means when you select a duration to stake for, the funds will become available exactly at the end of that duration.



**Miscellaneous**
-----------------

Does using Flash Protocol generate taxable events?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
We cannot provide tax or accounting advice. Tax regulations are specific
to jurisdiction where you or your company reside. For any legal or tax
matters we recommend consulting your own attorney.


What are the risks of using the Flashstake Protocol?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol has been audited by multiple third-party firms as explained within the :doc:`Security </security>` page.
however this does not guarantee that there are no bugs. The code has been open-sourced and can be reviewed before use.

It is important to note the Flashstake Protocol has been designed as a marketplace which allows any third-party
developers to create their own Flash Strategies. We advise caution when using such strategies since it is possible
for a given strategy to have arbitrary logic on how funds are directed.

.. note::
    You can read more about Flash Strategies :doc:`here </core-concepts/strategies>`.

The Flashstake Protocol will initially be launched with a handful of Flash Strategies. Since these strategies use
underlying protocols such as AAVE, Yearn, Curve, etc there is the risk of these underlying protocols having bugs.
We have picked underlying protocols we believe are tried, tested and well known within the decentralised
finance industry.

There is no risk of the Flashstake Protocol defaulting upon a bank run but it is possible for the underlying
protocol (eg AAVE) to be subjected to a bank run. We cannot comment on whether the underlying protocol is
susceptible to this scenario.
