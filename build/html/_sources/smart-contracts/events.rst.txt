Events
======

A list of all events emitted by the Flash Protocol

Staked
------

.. code-block:: solidity

    event Staked(
            bytes32 id,
            uint256 amountIn,
            uint256 expiry,
            uint256 expireAfter,
            uint256 mintedAmount,
            address indexed staker,
            address indexed receiver
        );


- **id:** this is the stake id. With the stake id you can fetch the stake data from the protocol.
- **amountIn:** this is the $FLASH amount that the user has staked.
- **expiry:** the time after which the stake will expire (e.g. 86400 = 1 expiration)  
- **expireAfter:** the block timestamp after which the stake will expire.  
- **mintedAmount:** the amount of minted $FLASH - this is basically the yield being redirected to the Flash Receiver. 
- **staker:** the address of the user. 
- **receiver:** the address of the yield destination. 

Unstaked
--------

.. code-block:: solidity

    event Unstaked(bytes32 id, uint256 amountIn, address indexed staker);

- **id:** this is the stake id. With the stake id you can fetch the stake data from the protocol.
- **amountIn:** this is the $FLASH amount that the user has staked.
- **staker:** the address of the user. 


Subgraph
--------

This section explains everything you need to know about the Flash Protocol Subgraph. 
The Flash Protocol Subgraph listens for events from one or more data sources (Smart Contracts) on the Ethereum Blockchain.
It handles indexing and caching of data which can later be queried using an exposed GraphQL API, providing an excellent developer experience.

The Flash Protocol Subgraph is powered by `The Graph <https://thegraph.com/>`_

.. seealso::

   The Graph is a protocol for building decentralized applications (dApps) quickly on Ethereum and IPFS using GraphQL.


Data Sources
~~~~~~~~~~~~~
- Flash Protocol - <TODO: FLASH_PROTOCOL_ADDRESS>

Resources
~~~~~~~~~~
- Flash Protocol Subgraph Explorer: <TODO: THE_GRAPH_URL>
- Flash Protocol Subgraph Source: <TODO: GITHUB_URL>
    

Queries
~~~~~~~~

This page provides various query examples.
You can test any of the queries, or write your own, on the Flash Protocol Subgraph Explorer.


- TBD_1

- TBD_2