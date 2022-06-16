Flash Strategy
===============

Any strategy registered and used by the Flashstake Protocol has to match the Flash Strategy interface, described here.


Methods
--------

Deposit principal
^^^^^^^^^^^^^

.. code-block:: solidity

    function depositPrincipal(uint256 _tokenAmount) external returns (uint256);

This is how principal will be deposited into the contract.
The Flash protocol allows the strategy to specify how much should be registered.
This allows the strategy to manipulate (eg take fee) on the principal if the strategy requires.

Withdraw principal
^^^^^^^^^^^^^

.. code-block:: solidity

    function withdrawPrincipal(uint256 _tokenAmount) external;

This is how principal will be returned from the contract.

Burn fToken
^^^^^^^^^^^^^

.. code-block:: solidity

    function burnFToken(
        uint256 _tokenAmount,
        uint256 _minimumReturned,
        address _yieldTo
    ) external returns (uint256);

Responsible for instant upfront yield. Takes fERC20 tokens specific to this strategy.
The strategy is responsible for returning some amount of principal tokens.

Get principal balance
^^^^^^^^^^^^^

.. code-block:: solidity

    function getPrincipalBalance() external view returns (uint256);

This should return the current total of all principal within the contract.

Get yield balance
^^^^^^^^^^^^^

.. code-block:: solidity

    function getYieldBalance() external view returns (uint256);

This should return the current total of all yield generated to date (including bootstrapped tokens).

Get principal address
^^^^^^^^^^^^^

.. code-block:: solidity

    function getPrincipalAddress() external view returns (address);

This should return the principal token address (eg DAI).

Quote mint fToken
^^^^^^^^^^^^^

.. code-block:: solidity

    function quoteMintFToken(uint256 _tokenAmount, uint256 duration) external view returns (uint256);

View function which quotes how many principal tokens would be returned if x fERC20 tokens are burned.

Quote burn fToken
^^^^^^^^^^^^^

.. code-block:: solidity

    function quoteBurnFToken(uint256 _tokenAmount) external view returns (uint256);

View function which quotes how many principal tokens would be returned if x fERC20 tokens are burned.

.. note::
    This should utilise bootstrap tokens if they exist.
    Bootstrapped tokens are any principal tokens that exist within the smart contract.

Set fToken address
^^^^^^^^^^^^^

.. code-block:: solidity

    function setFTokenAddress(address _fTokenAddress) external;

The function to set the fERC20 address within the strategy.

Get max stake duration
^^^^^^^^^^^^^

.. code-block:: solidity

    function getMaxStakeDuration() external view returns (uint256);

This should return what the maximum stake duration is.
