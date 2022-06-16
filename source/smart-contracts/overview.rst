Overview
===============

Key concepts
--------------

Strategy
^^^^^^^^^

A *strategy* is a smart contract inheriting the :doc:`Flash Strategy interface </smart-contracts/flash-strategy>`.
It uses one or more DeFi protocols (e.g. AAVE, Convex...) to stake a specific token (e.g. DAI, ETH...).
The :doc:`Flash Protocol </smart-contracts/flash-strategy>` uses the strategy to instantly mint fTokens when staking.

fToken
^^^^^^^

An *fToken* is an ERC-20 token, created through the FlashFTokenFactory contract,
using the FlashFToken contract (which is an ERC-20 contract).

When staking with the :doc:`Flash Protocol </smart-contracts/flash-strategy>` fTokens are minted using the strategy's contract.
If you Flashstake your stake, then the minted fTokens are immediately burned for yield.

If you hold fTokens, you can also use the strategy contract to burn them at any time to withdraw principal from the yield pool
(see :doc:`Flashburn </user-interface/flashburn>`).


Addresses
-----------

Kovan
^^^^^

.. csv-table::
   :header: "Contract", "Address"
   :widths: 10, 30

   "Flash Token", "0x9887281FC23CA955bbbBeC3cDbB8BFc4999290E4"
   "Flash Protocol", "0x93213162Dd8A23c83d4D7E25f1282C94d2890528"
   "Flash NFT", "0xD0479ecc19Cb748d1a4778c906bE11012c9dd5cC"
   "Flash fToken Factory", "0x781CEC894BCBa85330F53a3C205Ee8e93D46922d"
   "Flash AAVE Strategy", "0x0d9A751D9cEFab7d2eb14c0D0c888faD2A98Cfeb"
   "fDAI-0d9A-Cfeb", "0x0d9A751D9cEFab7d2eb14c0D0c888faD2A98Cfeb"
   "FlashBack", "0x44Ecd42C5fBa48eE507f8b7DeB0C1e8b0034A71e" 



