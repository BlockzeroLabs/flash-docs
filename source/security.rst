**Security**
----------------

Security and decentralization were a top priority throughout the ideation and development process. The
smart contracts were created with the goal of being as decentralised as possible. This page provides
information on administrative capabilities, security audits, and other related security information.

It's important to note that the Flashstake Protocol has undergone extensive internal testing, resulting in
over 95% test coverage. The protocol has also been professionally audited by PeckShield and Openkertify/Secure3,
with no major security issues detected. Additionally, the protocol was thoroughly tested by over 2,000 users
on the testnet, with over 250,000 interactions conducted.

Audit
======

Two third-party companies independently audited the Flashstake Protocol, and no significant problems
were discovered in the code. Any medium and low-level issues that were identified have since been addressed. You
can view the associated Audit documents below.

PeckShield: :download:`pdf <peckshield_flashstake_audit.pdf>`

Openkertify / Secure3: :download:`pdf <secure3_flashstake_audit.pdf>`

Testnet Competition
===================

Blockzero Labs conducted testnet competitions with its community, resulting in the deployment and
testing of the Flashstake Protocol on the Kovan network. Over 2,000 participants were involved,
generating more than 250,000 individual interactions with the contracts.

These testnet exercises uncovered and fixed the following smart contract bugs:

#. FlashNFTs were accidentally burned during early unstaking
#. It was previously not possible to Flashstake and redirect all yield to another address, which resulted in transaction failure.

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

The Flashstake Protocol contract features a single administrative function named "setMintFeeInfo." This function
enables the update of the percentage fee taken each time fTokens are minted and the address they are sent to.
The contract has a hardcoded maximum fee limit of 20%.

For more information, visit the :doc:`./smart-contracts/flash-protocol` page.

.. important::
    Anyone can develop and register Flash Strategies which work with the Flash Protocol. It's crucial to
    only interact with trustworthy Flash Strategies.

Information on Flashstake Strategies developed by the Flashstake Core team can be found in the sidebar. The individual
pages explain how each strategy functions as well as admin controls and risks involved.

Unit Tests
==========

The Flashstake Protocol has been thoroughly tested to ensure its correct functioning. The unit tests for
the protocol have reached a coverage rate of more than 95%. The tests can be accessed on the Flash Protocol
GitHub repository at https://github.com/BlockzeroLabs/flashv3-contracts.

.. important::
    The information on this page is specific to the Flashstake Protocol and may not apply to
    all :doc:`Flashstake Strategies </core-concepts/strategies>`.
