**Security**
----------------

Security and decentralisation have been top of mind from ideation through to delivery.

The Smart Contracts have been designed to be as permissionless as possible.

This page details the admin functionalities, audits and any other security related information.

.. important::
    The Flashstake Protocol has achieved over 95% test coverage within internal unit tests.

    The protocol has been audited by PeckShield and Openkertify/Secure3 with no major items found.

    Over 2,000 users tested the protocol on testnet generating over 250,000 individual interactions.

Audit
======

The Flashstake Protocol has been audited by two third party companies in isolation. No major issues were found
with the audited code. Medium and Low items have been addressed.

PeckShield: :download:`pdf <peckshield_flashstake_audit.pdf>`

Openkertify / Secure3: :download:`pdf <secure3_flashstake_audit.pdf>`

Testnet Competition
===================

Blockzero Labs have run testnet competitions with their community which allowed the Flashstake Protocol to be
deployed and tested on Kovan. This allowed the protocol to be tested with over 2,000 participants generating in excess
of 250,000 individual interactions with the contracts.

These testnet runs have allowed us to find and resolve the following Smart Contract bugs:

#. FlashNFT's were being burned when early unstaking
#. Unable to Flashstake and redirect all yield to another address (transaction fail)

Testnet competition articles can be found here: |location_link_security_a1|, |location_link_security_a2| and
|location_link_security_a3|.


.. |location_link_security_a1| raw:: html

   <a href="https://medium.com/flashstake-protocol/flashstake-protocol-testnet-announcement-b394506ebd0f" target="_blank">round 1</a>

.. |location_link_security_a2| raw:: html

   <a href="https://medium.com/flashstake-protocol/flashstake-testnet-tournament-round-2-92edd3180105" target="_blank">round 2</a>

.. |location_link_security_a3| raw:: html

   <a href="https://medium.com/flashstake-protocol/flashstake-testnet-tournament-round-2-762d112c5761" target="_blank">round 3</a>



Admin Functionality
===================

The Flashstake Protocol contract has one admin function named setMintFeeInfo. This function can be used to update the
percentage fee taken whenever fTokens are minted as well as the address they are sent to. There is a maximum limit of
20% that has been hardcoded into the contract.

You can read more about this on the :doc:`./smart-contracts/flash-protocol` page.

.. important::
    Flash Strategies which work with the Flash Protocol can be developed by anyone and registered with the protocol. It
    is important to ensure you interact with trusted Flash Strategies only.

The Flashstake team have developed one strategy which will be available on launch. These is the
:doc:`./strategies/aavev2-v1` which allows staking of DAI, USDC and other tokens from the AAVEv2 market.
There are limited admin functionalities within these - none which allow movement of user funds.

Unit Tests
==========

The Flashstake Protocol has a vast array of unit tests to ensure the protocol behaves as intended. The total code coverage
is over 95%.

These can be found within the Flash Protocol GitHub: https://github.com/BlockzeroLabs/flashv3-contracts
