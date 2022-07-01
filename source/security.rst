**Security**
----------------

Security and decentralisation have been top of mind from ideation through to delivery.

The Smart Contracts have been designed to be as permissionless as possible.

This page details the admin functionalities, audits and any other security related information.

Audit
======

The Flashstake Protocol has been audited by two third party companies in isolation. Minor issues were found with the
initial submitted code but all items have been resolved.

PeckShield: https://github.com/peckshield/publications/tree/master/audit_reports/PeckShield-Audit-Report-Flashstake-v1.0.pdf

Openkertify / Secure3: xxx

.. important::
    This does not guarantee there are no bugs present.


Testnet Competition
===================

Blockzero Labs have kindly run testnet competitions with their community which allowed the Flashstake Protocol to be
deployed and tested on Kovan. This allowed us to have over 2,000 participants with in excess of 500,000 individual
interactions with our contracts.

There were XXXXX bugs found in total which were not caught in audit. These have been detailed below (and rectified):

#. FlashNFT's were being burned when early unstaking
#. Users were unable to Flashstake and redirect all yield to another address


Admin Functionality
===================

The Flashstake Protocol contract has one admin function named setMintFeeInfo. This function can be used to update the
percentage fee taken whenever fTokens are minted as well as the address they are sent to. There is a maximum limit of
20% that has been hardcoded into the contract.

You can read more about this on the :doc:`./smart-contracts/flash-protocol` page.

.. important::
    Flash Strategies which work with the Flash Protocol can be developed by anyone and registered with the protocol. It
    is important to ensure you interact with trusted Flash Strategies only.

The Flashstake team have developed two strategies which will be available on launch. These are the AAVE DAI strategy which
allows staking of DAI and the Convex Strategy which allows the staking of cvxCRV (cvxcrv-f). There are limited admin
functionalities within these - none which allow movement of user funds.

Unit Tests
======

The Flashstake Protocol has a vast array of unit tests to ensure the protocol behaves as intended. The total code coverage
is over 95%.

These can be found within the Flash Protocol GitHub: https://github.com/BlockzeroLabs/flashv3-contracts

.. note::
    The protocol code will be made public before it is deployed on mainnet.


