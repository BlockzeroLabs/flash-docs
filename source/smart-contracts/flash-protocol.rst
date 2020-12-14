Flash Protocol
==============

.. seealso::

    “Smart contracts are pretty difficult to get right.” Emin Gün Sirer.

Given the above quote, smart contracts are computer code that define how money moves, so we put the security and simplicity as top priority while building the Flash Protocol.


The Flash Protocol contract includes the core functionalities to perform a flash stake, along with interfaces to fetch all data that you'll ever going to need.

State functions
---------------

Those are the functions that require transacting on the Ethereum network.

Stake
~~~~~
.. code-block:: solidity

    function stake(uint256 amountIn, uint256 days, address receiver, bytes calldata data) external returns (uint256 mintedAmount, uint256 matchedAmount, bytes32 id);

Unstake
~~~~~~~
.. code-block:: solidity

    function unstake(bytes32 id) external returns (uint256 withdrawAmount);

Unstake Early
~~~~~~~~~~~~~
.. code-block:: solidity

    function stake(uint256 amountIn, uint256 days, address receiver, bytes calldata data) external returns (uint256 mintedAmount, uint256 matchedAmount, bytes32 id);

View functions
--------------

Those are the functions that can be used to fetch data from the protocol.

Get Stake Balance
~~~~~~~~~~~~~~~~~

.. code-block:: solidity

    function balances(address staker) external view returns (uint256);


Get FPY ratio
~~~~~~~~~~~~~

.. code-block:: solidity

    function getFPY(uint256 amountIn) external view returns (uint256);

Get Mint Amount
~~~~~~~~~~~~~~~

.. code-block:: solidity

    function getMintAmount(uint256 amountIn, uint256 expiry) external view returns (uint256);

Get Stake By ID
~~~~~~~~~~~~~~~

.. code-block:: solidity

    function stakes(bytes32 id) external view returns (uint256 amountIn, uint256 expiry, uint256 expireAfter, uint256 mintedAmount, address staker, address receiver);
