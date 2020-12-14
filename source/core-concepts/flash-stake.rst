Flash Stake
===========

Flash stakes are a way to stake your $FLASH for certain amount of time and get upfront yield instantly.

For end-users, staking is intuitive: a user picks an amount and staking time and the protocol calculates how much yield they’ll receive. 
The user can also pick the destination of the yield - can be any valid Ethereum address.

If the yield destination is EOA (externally owned account), then the yield is simply transferred to this address.
However, if the yield destination is a contract, then a specific contract interface is invoked.
This opens a lot of different use cases and opportunities. The Flash Protocol does not know and does not care what happens in the destination contract.

Anatomy of a stake
------------------

At the most basic level all stakes in the Flash Protocol happen with a single function, aptly named `stake`

.. code-block:: solidity

    function stake(uint256 amountIn, uint256 expiry, address receiver, bytes calldata data)

- **amountIn:** this is the $FLASH amount that the user is going to stake.
- **expiry:** the time after which the stake will expire.  
- **receiver:** the address of the yield destination - externally owned accounts or a contract. 
- **data:** arbitrary data passed to the receiving contract - it's up to the dApp what kind of data is passed.


To learn more about the flash receiver, please refer to :doc:`./flash-receiver`
