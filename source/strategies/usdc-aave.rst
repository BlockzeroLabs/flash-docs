AAVE V2 USDC (Ethereum)
===============

.. csv-table::
   :widths: 10, 30


   "Strategy address", "0x15c32F81Df9B00b97B68148B6BdeB72D57f24845"
   "fToken Name", "fUSDC-15c3"
   "fToken address", "0xe221bBf1D5960FC420D451206cF2ee0539398aAC"

This flashstaking strategy accepts USDC from users and pays upfront yield in USDC.

Users can early unstake their principal deposit at any time if in possession of the required amount of fUSDC-15c3.
The full amount of accumulating interest is available for redeeming fUSDC-15c3 or direct flashstaking.
The deposited USDC is redirected to the USDC AAVE V2 lending pool on Ethereum to generate interest.

Exhaustive description of contract owner powers
^^^^^^^^^^^^^

The contract owner cannot change anything in the contract.
