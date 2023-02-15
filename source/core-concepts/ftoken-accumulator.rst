fToken Accumulator
==================

.. important::
    fToken accumulator interaction user guide :download:`pdf </ftokenaccumulatorv2.pdf>`

    This user guide will be updated frequently, ensure you visit this page for the latest version.

    This user guide may be outdated. For the latest information join our discord.

+------------+---------------------------------------------+
| Network    | Contract Address                            |
+============+=============================================+
| Ethereum   | 0x142fd6279E0F3ab28801267497C47116bE1F46FC  |
+------------+---------------------------------------------+
| Optimism   | 0xFD49a007D9fADf8904849edbef1B3344E42142Ff  |
+------------+---------------------------------------------+
| Goerli     | 0x8373dd2efCaeA8174136E9d5F729219e47ee94ca  |
+------------+---------------------------------------------+

The Flashstake Protocol allows for the collection of a fee in the form of fTokens during the minting process when a
user (:doc:`stakes </core-concepts/ftokens>`) into the protocol. This fee is directed towards the fToken Accumulator and is owned by Flash token holders.
As the protocol grows, various strategies will be developed by both the Flashstake DAO and external developers, resulting
in a large number of different fTokens being taken as fees.

The fToken Accumulator allows for the arbitrage of these fTokens in exchange for Flash tokens. This process is typically
carried out by arbitragers, who may accumulate a specific fToken within the fToken Accumulator in exchange for a fixed
amount of Flash tokens.

The fixed amount of Flash tokens is currently set to 100,000 but can be updated by the Flashstake DAO multisig.

For example, if Bob Flashstakes and 5,000 fTokens are minted, with a protocol fee of 1%, 50 fTokens would be taken as
a fee and directed towards the fToken Accumulator.

If Alice, an arbitrager, knows that 50 fTokens can be exchanged for 10,000 USDC if they are burned and redeemed
against the yield pool, and 100,000 Flash tokens are currently worth 9,500 USDC, she might buy 1,000 Flash tokens in
order to get the 50 fTokens and make a profit of $500 by accumulating them from the fToken Accumulator.

.. note::
    The protocol has a hardcoded maximum limit of 20% for the protocol fee, and the latest protocol fee can be retrieved
    by polling the subgraph (:doc:`read more </smart-contracts/overview>`).

    Flash tokens are currently sent to the Flashstake DAO multisig with plans in the near future to allow Flash token
    holders to earn.

Currently, the fToken Accumulator charges a fee to arbitragers in the form of fTokens, which are then directed to the
Flashstake DAO multisig. This fee is implemented to maintain a constant supply of fTokens and prevent potential
manipulation of a strategy's yield pool.
