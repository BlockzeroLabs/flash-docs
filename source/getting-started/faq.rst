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

- Strategy A currently has 1,000,000 staked DAI tokens that are increasing the size of the "yield pool" every block thanks to the underlying protocol (eg AAVE, Yearn, etc)

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


Do I have to burn fTokens?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Users are welcome to Stake tokens and hold onto their fTokens.

Burning fTokens is only required if you wish to redeem your fTokens against the "yield pool".


How is the APY/APR determined?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
The APY/APR is not determined by the Flashstake Protocol but instead based on the size of the "yield pool" within a
given strategy. This means the APY/APR is entirely dependent on the "yield pool" for a given strategy.


**Miscellaneous**
-----------------

Does using Flash Protocol generate taxable events?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
We cannot provide tax or accounting advice. Tax regulations are specific
to jurisdiction where you or your company reside. For any legal or tax
matters we recommend consulting your own attorney.

Are there risks in using Flashstake?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The Flashstake Protocol smart contracts have been designed with security as a top priority. The core protocol code
has been reviewed and audited by multiple auditors (of course, we cannot guarantee that bugs won’t be found in the
future.)

You can find more information about this on the :doc:`Security </security>` page.
