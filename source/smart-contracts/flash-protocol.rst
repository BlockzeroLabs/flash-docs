Flash Protocol
===============

The Flash Protocol smart contract allows you to create Flashstakes or stakes with specific Flash strategies.


Methods
--------

Register Strategy
^^^^^^^^^^^^^^^^

.. code-block:: solidity

    function registerStrategy(
        address _strategyAddress,
        address _principalTokenAddress,
        string calldata _fTokenName,
        string calldata _fTokenSymbol
    ) external

With the registerStrategy method, you can register a custom strategy for Flashstaking. It takes as parameters:

* **_strategyAddress**: your strategy's smart contract address (see `Flashstake strategy </smart-contract/flash-strategy>`)
* **_principalTokenAddress**: your strategy's principal token (staked and received). For example, if your strategy is used to stake DAI, _principalTokenAddress would be the DAI stablecoin's smart contract address.
* **_fTokenName**: what the fToken minted when Flashstaking/staking shall be called.
* **_fTokenSymbol**: which symbol should be given to the fToken minted when Flashstaking/staking.

Stake
^^^^^^

.. code-block:: solidity

    function stake(
        address _strategyAddress,
        uint256 _tokenAmount,
        uint256 _stakeDuration,
        address _fTokensTo,
        bool _issueNFT
    ) public returns (StakeStruct memory _stake)

The stake method creates a new stake with a registered strategy of your choosing. Its parameters are:

* **_strategyAddress**: address of a registered strategy. You have to register the strategy with the above-described registerStrategy method first before passing its address here.
* **_tokenAmount**: amount (in Wei) of staked tokens.
* **_stakeDuration**: total duration (in seconds) of the stake.
* **_fTokensTo**: the address the minted fTokens shall be sent to.
* **_issueNFT**: mint stake as NFT upfront.

Flashstake
^^^^^^^^^^

.. code-block:: solidity

    function flashStake(
        address _strategyAddress,
        uint256 _tokenAmount,
        uint256 _stakeDuration,
        address _yieldTo,
        bool _mintNFT
    ) external nonReentrant

The **flashStake** method is similar to *stake*, which it calls before burning the minted fTokens for principal.
The **_yieldTo** parameter has the same function as the *_fTokensTo* parameter in *stake*.

Unstake
^^^^^^^

.. code-block:: solidity

    function unstake(
        uint256 _id,
        bool _isNFT,
        uint256 _fTokenToBurn
    ) external nonReentrant returns (uint256 _principalReturned, uint256 _fTokensBurned)

The *unstake* method unstakes your Flashstake/stake, either partially or completely. Parameters:

* **_id**: your stake's ID.
* **_isNFT**: true if your stake has been minted as an NFT; false otherwise.
* **_fTokenToBurn**: amount of fTokens to be burnt to unstake your desired amount of principal for your stake.

Issue NFT
^^^^^^^^^

.. code-block:: solidity

    function issueNFT(uint256 _stakeId) public returns (uint256 _nftId)

This methods issues an NFT from your stake. It can be called at anytime after your stake's creation,
if an NFT wasn't initially minted in the flashStake/stake methdod.

It returns the NFT's ID, which is different from the stake's ID passed as parameter.

Get stake info
^^^^^^^^^^^^^^

.. code-block:: solidity

    function getStakeInfo(uint256 _id, bool _isNFT) external view returns (StakeStruct memory _stake)

Events
--------

Strategy Registered
^^^^^^^^^^^^^^^^^^^

.. code-block:: solidity

    event StrategyRegistered(
        address indexed _strategyAddress,
        address indexed _principalTokenAddress,
        address indexed _fTokenAddress
    );

* **_strategyAddress**: address of the newly registered strategy.
* **_principalTokenAddress**: address of the newly registered strategy's principal token.
* **_fTokenAddress**: address of the newly registered strategy's principal token.



Staked
^^^^^^^^^^^^^^^^^^^

.. code-block:: solidity

    event Staked(uint256 _stakeId);

* **_stakeId**: ID of the newly created stake.


Unstaked
^^^^^^^^^^^^^^^^^^^

.. code-block:: solidity

    event Unstaked(uint256 _stakeId, uint256 _tokensReturned, uint256 _fTokensBurned, bool _stakeFinished);

* **_stakeId**: ID of the stake from which funds were unstaked.
* **_tokensReturned**: amount of principal tokens withdrawn from stake.
* **_fTokensBurned**: amount of fTokens burned to perform the unstaking.
* **_stakeFinished**: true if the stake duration is over and/or if all funds were unstaked; false otherwise.

NFT Issued
^^^^^^^^^^^^^^^^^^^

.. code-block:: solidity

    event NFTIssued(uint256 _stakeId, uint256 nftId);

* **_stakeId**: ID of the stake.
* **nftId**: ID of the newly minted NFT.

NFT Redeemed
^^^^^^^^^^^^^^^^^^^

.. code-block:: solidity

    event NFTRedeemed(uint256 _stakeId, uint256 nftId);

* **_stakeId**: ID of the stake.
* **nftId**: ID of the newly minted NFT.
