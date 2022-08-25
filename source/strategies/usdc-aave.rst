AAVE V2 USDC (Ethereum)
===============
You can read more about overall security and risks of using the Flashstake Protocol by heading over to :doc:`Security </security>`.

.. important::
    Flashstake Strategies are used by the Flashstake Protocol to facilitate where the staked tokens are directed towards
    as well as how up-front yield is generated when burning fTokens.

    Flashstake Strategies can be developed and registered with the Flashstake Protocol by anyone but the Flashstake
    DAO chooses which Strategies are listed on the frontend located at app.flashstake.io


Strategy Specific Information
------------------------------
.. csv-table::
   :widths: 10, 30

   "Strategy address", "0x15c32F81Df9B00b97B68148B6BdeB72D57f24845"
   "fToken Name", "fUSDC-15c3"
   "fToken address", "0xe221bBf1D5960FC420D451206cF2ee0539398aAC"

This Flashstake strategy accepts USDC from depositors and pays upfront yield in USDC.

Users can early unstake their principal deposit at any time if in possession of the required amount of fUSDC-15c3.
The full amount of accumulating yield is available for redeeming fUSDC-15c3 or direct flashstaking.
The deposited USDC is redirected to the USDC AAVE V2 lending pool on Ethereum to generate interest.

Exhaustive description of contract owner powers
^^^^^^^^^^^^^

This Strategy implements Ownable and is controlled by the Flashstake DAO. There are limited powers available over
this contract as explained below:

- Ability to withdraw any ERC20 token that is not the AAVE interest bearing token (aUSDC). This is to ensure users can be refunded if ERC20 tokens are accidentally sent to this address. Please note, principal tokens are never stored in this contract therefore cannot be withdrawn.
- Ability to claim AAVE rewards from the AAVE rewards pool.
