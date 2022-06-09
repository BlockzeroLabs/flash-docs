Flash Receiver
===============

Whenever a user stake he can choose the destination of the yield. The yield destination, can be either EOA (externally owned account) or a contract.

If the yield destination is EOA (externally owned account), then the yield is simply transferred to this address.

However, if the yield destination is a contract, then a specific contract interface is invoked.

This functionality allows anyone to build their own dApp with their own flash receiver on top of the Flash Protocol. 

Anatomy of the receiver
-----------------------

If the receiver is a contract, the following interface should be exposed by that contract.

.. code-block:: solidity

    function receiveFlash(
        bytes32 id, 
        uint256 amountIn, 
        uint256 expireAfter, 
        uint256 mintedAmount, 
        address staker, 
        bytes calldata data)
    external returns (uint256);


- **id:** this is the stake id. With the stake id you can fetch the stake data from the protocol.
- **amountIn:** this is the $FLASH amount that the user has staked.
- **expireAfter:** the time after which the stake will expire.  
- **mintedAmount:** the amount of minted $FLASH - this is basically the yield being redirected to the Flash Receiver. 
- **staker:** the address of the user. 
- **data:** arbitrary data passed from the protocol - it's up to the dApp what kind of data is passed.