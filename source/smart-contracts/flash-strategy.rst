Flash Strategy
===============

Any strategy registered and used by the Flashstake Protocol must match the Flash Strategy interface, described here.


Methods
--------

Deposit principal
^^^^^^^^^^^^^

.. code-block:: solidity

    function depositPrincipal(uint256 _tokenAmount) external returns (uint256);

This function will be called whenever a user stakes via the Flash Protocol. The Strategy owner can choose to implement
a fee but the resulting "locked" principal the user should expect after the stake has ended must be returned.

.. danger::
    This function should be protected such that only the Flash Protocol can execute this. This is to ensure users
    do not accidentally call this function and lose their funds.

Withdraw principal
^^^^^^^^^^^^^

.. code-block:: solidity

    function withdrawPrincipal(uint256 _tokenAmount) external;

This function should withdraw principal from the underlying strategy (eg AAVE).

.. note::
    This function should be protected such that only the Flash Protocol can execute this. Keeping this unprotected
    would of course mean anyone would withdraw principal tokens from your strategy.

Burn fToken
^^^^^^^^^^^^^

.. code-block:: solidity

    function burnFToken(
        uint256 _tokenAmount,
        uint256 _minimumReturned,
        address _yieldTo
    ) external returns (uint256);

This is the function the user will be calling when performing a :doc:`FlashBurn </core-concepts/flashburn>`. It is
responsible for burning the fToken supplied by the user and returning yield to the user.

Get principal balance
^^^^^^^^^^^^^

.. code-block:: solidity

    function getPrincipalBalance() external view returns (uint256);

This must return the current total of all principal accepted by the contract.

Get yield balance
^^^^^^^^^^^^^

.. code-block:: solidity

    function getYieldBalance() external view returns (uint256);

This function must report the total yield balance.

Get principal address
^^^^^^^^^^^^^

.. code-block:: solidity

    function getPrincipalAddress() external view returns (address);

This must return the principal token address (eg DAI).

Quote mint fToken
^^^^^^^^^^^^^

.. code-block:: solidity

    function quoteMintFToken(uint256 _tokenAmount, uint256 duration) external view returns (uint256);

This function will be called by the Flash Protocol (and frontends) to determine how many fTokens should be minted
for a given _tokenAmount and _duration (in seconds).

Quote burn fToken
^^^^^^^^^^^^^

.. code-block:: solidity

    function quoteBurnFToken(uint256 _tokenAmount) external view returns (uint256);

This function must return the yield a user should expect when burning _tokenAmount fTokens.

Set fToken address
^^^^^^^^^^^^^

.. code-block:: solidity

    function setFTokenAddress(address _fTokenAddress) external;

The function to set the fERC20 address within the strategy.

.. note::
    This function should be protected such that only the Flash Protocol can execute this.

Get max stake duration
^^^^^^^^^^^^^

.. code-block:: solidity

    function getMaxStakeDuration() external view returns (uint256);

This function must report the maximum duration a user can stake for. This can either be hardcoded or be a function
of on-chain metrics.


Events
--------

BurnedFToken
^^^^^^^^^^^^^^^^^^^


.. code-block:: solidity

    event BurnedFToken(address indexed _address, uint256 _tokenAmount, uint256 _yieldReturned);

* **_address**: the address of the user who burned fTokens.
* **_tokenAmount**: the number of fTokens burned.
* **_yieldReturned**: the number of yield tokens returned to the user.





