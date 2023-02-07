FlashNFT
===============

+------------+---------------------------------------------+
| Network    | Multisig Address                            |
+============+=============================================+
| Ethereum   | 0x3b090839C26fE3b2BdfA2F4CD7F3ab001ccdF73F  |
+------------+---------------------------------------------+
| Optimism   | 0x3b090839C26fE3b2BdfA2F4CD7F3ab001ccdF73F  |
+------------+---------------------------------------------+

The Flashstake Protocol has been designed to be robust and integratable as a building block in the
decentralized finance industry. It has several features to enable third-party protocols to interact with it on-chain,
one of which is the implementation of the FlashNFT.

The FlashNFT represents a user's stake in the Flash Protocol and can be minted at the time of staking or
later. The NFT can be transferred to another address, which transfers the ownership of the stake.

.. caution::
    Minting a FlashNFT will transfer the ownership of your stake into the NFT. This means if you mint an NFT
    and send to a address you do not control, you lose ownership of the stake and the associated principal.

    Once the NFT has been minted, the stake cannot be withdrawn or modified (unstake early) without the NFT.

Developers can use the NFT token ID to access all information related to the corresponding
stake in the Flashstake Protocol.


