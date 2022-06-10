FAQ
===

**Basics**
----------

What is Flashstake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Flashstake is a permissionless protocol allowing anyone to earn instant upfront yield through different strategies.
Because of its permissionless nature, it will exist for as long as Ethereum does.


How does Flashstake work?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol can be separated out into two main modules, the protocol and the strategy. The two of these
modules are used in tandem to accept tokens from users which are then deposited into a strategy. The strategy over time
accumulates yield from the underlying protocol - the Flashstake AAVE V2 strategy uses the AAVE V2 protocol as the
underlying protocol.

We will be focusing on the Flash AAVE V2 strategy but all strategies work in a similar way.

Upon depositing tokens (eg DAI) into the Flashstake Strategy, these tokens are registered and deposited directly into
AAVE. This action mints fTokens (eg fDAI) where the number of tokens minted is a function of stake duration and staked
amount.

These fTokens can then be used at any point in time to redeem for available yield. If the user holds 20% of all the
fTokens in existence for a given strategy, they are entitled to redeem their fTokens for 20% of all the available
yield in the strategy - this is called Flashburn.

Flashstake is simply performing all these actions in one transaction which results in instant upfront yield.


Is Flash Protocol fully permissionless?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
x

Does Flash Protocol charge any fees at the protocol layer?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
x

Is there a Flash Protocol token?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
x

**Miscellaneous**
-----------------

Does using Flash Protocol generate taxable events?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
We cannot provide tax or accounting advice. Tax regulations are specific
to jurisdiction where you or your company reside. For any legal or tax
matters we recommend consulting your own attorney.

Are there risks in using Flashstake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Flashstake smart contracts have been designed with security as a top
priority. The core protocol code has been reviewed and audited by
XXXX (of course, we cannot guarantee that bugs won’t be found in the
future.)

The Flash Protocol contracts are not upgradeable (though other
third-party Pool implementations might be), and there aren't any
backdoors.
