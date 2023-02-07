FAQ
===

**Basics**
----------

What is Flashstake Protocol?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol offers a permissionless solution for individuals to earn instant upfront yield through the
utilization of various Flashstake Strategies, which leverage the power of underlying protocols like
AAVE, Yearn, and Lido.


What is a FlashStake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol provides a feature called :doc:`FlashStake </core-concepts/flashstake>` which enables users to both stake their
principal tokens to :doc:`mint fTokens </core-concepts/ftokens>` and
:doc:`redeem the received fTokens for yield </core-concepts/flashburn>` in a single transaction.

A Flashstake provides the simplicity of allowing a user to never interact directly with
:doc:`fTokens </core-concepts/ftokens>`. The user
can stake a token of their choosing, for any duration they want, and receive upfront yield,
while their original staked token now remains locked up for that duration they chose, with no penalty
for early withdraw.

The Flashstake Protocol makes it easy for users to earn upfront yield without having to directly deal with
:doc:`fTokens </core-concepts/ftokens>`. The user can stake any token for the desired duration and receive
immediate rewards, while the original staked principal will be locked for the selected period without any
consequences for early withdrawal.


How does Flashstake Protocol work?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
See :doc:`Protocol Overview </getting-started/protocol-overview>`.


What is the “yield pool” and how does it increase?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The "Yield Pool" is the total available yield earned by a particular Flash Strategy. When users deposit their tokens
into the Flashstake Protocol, they are sent to a specific Flash Strategy which redirects them to an underlying
protocol, such as AAVE. This results in the earning of yield, or interest, over time, which is accumulated in
the strategy's "yield pool". It's important to note that each Flash strategy has its own unique yield pool.

.. note::
    Staked funds always belong to the staker and are never used to pay new users, making the
    Flashstake Protocol safe from potential bank runs.


Are there benefits to not burning the fToken?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The yield pool of a Flash strategy is represented by fTokens, linked to the performance of the underlying protocol
such as AAVE. If the interest rate of the underlying protocol increases, the yield pool will grow at a faster pace,
leading to a higher yield rate when fTokens are redeemed.

For example, if the interest rate of the underlying protocol doubles, the yield pool grows at twice the speed and
the value of fTokens will increase, while maintaining the same ownership percentage of the yield pool.

This means redeeming fTokens in the future can result in increased yield for the redeemer,
when compared to the possible yield redeemed in the past.

.. important::
    The upfront yield rate can fluctuate up or down over time.

How is the APY/APR determined?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The APY/APR is not determined by the Flashstake Protocol but instead based on the available yield of a given strategy:

- When burning fTokens for yield within the "yield pool"
- When swapping fTokens via a liquidity pool (open market)

See :doc:`Protocol Overview </getting-started/protocol-overview>`.

How does the protocol handle staking time?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol uses block timestamps instead of locking the funds for a specific number of blocks.
This means that when you stake for a chosen duration, your funds will become available precisely at the end of that period.


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

What are the risks to a user's staked principal?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
This depends on the code of each strategy. The official Flashstake Strategies (as seen on the sidebar)
deposit 100% of your tokens into underlying protocols such as AAVE and Lido, and grant you full
control of your tokens when it's time to unstake them. The official strategies do not put your tokens in
danger of liquidation or use them for lending, payment to other stakers, or any other risk-prone activities.

.. important::
    Unofficial strategies should be used at your own risk and discretion.

