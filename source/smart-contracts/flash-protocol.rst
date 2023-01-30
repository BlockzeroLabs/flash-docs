Flash Protocol
===============

The Flash Protocol smart contract allows users to Stake principal tokens into a specified strategy.

The associated code for this smart contract can be found at 0x78b2d65dd1d3d9Fb2972d7Ef467261Ca101EC2B9 (ethereum
mainnet).


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

* **_strategyAddress**: your strategy's smart contract address (see :doc:`../smart-contracts/flash-strategy`)
* **_principalTokenAddress**: your strategy's principal token (staked and received). For example, if your strategy is used to stake DAI, _principalTokenAddress would be the DAI stablecoin's smart contract address.
* **_fTokenName**: what the fToken minted when Flashstaking/staking shall be called.
* **_fTokenSymbol**: which symbol should be given to the fToken minted when Flashstaking/staking.

.. important::
    Naming convention must be followed to be added to the official frontend.

The naming convention for _fTokenSymbol is a function of the principal token symbol and the first four letters of your
strategy - eg fDAI-0123


Stake
^^^^^^

.. code-block:: solidity

    function stake(
        address _strategyAddress,
        uint256 _tokenAmount,
        uint256 _stakeDuration,
        address _fTokensTo,
        bool _issueNFT
    ) public nonReentrant returns (StakeStruct memory _stake) {

The stake method creates a new stake with a registered strategy of your choosing. Its parameters are:

* **_strategyAddress**: address of a registered strategy. You have to register the strategy with the above-described registerStrategy method first before passing its address here.
* **_tokenAmount**: amount (in Wei) of staked tokens.
* **_stakeDuration**: total duration (in seconds) of the stake.
* **_fTokensTo**: the address the minted fTokens shall be sent to.
* **_issueNFT**: mint stake as NFT upfront.


.. note::
    Redirecting fTokens by providing a different address in the _fTokensTo address will result in only the resulting
    fTokens to be redirected. The Stake ownership will be retained by the caller. This also means when minting a FlashNFT,
    this will be retained by the caller (Staker).

Flashstake
^^^^^^^^^^

.. code-block:: solidity

    function flashStake(
        address _strategyAddress,
        uint256 _tokenAmount,
        uint256 _stakeDuration,
        uint256 _minimumReceived,
        address _yieldTo,
        bool _mintNFT
    ) external {

The **flashStake** method is similar to *stake*, which it calls before burning the minted fTokens for yield. Upon
staking, the fTokens minted will be held by the Flash Protocol and then immediately burned with the resulting yield
being redirected to _yieldTo.

.. note::
    Redirecting yield by providing a different address in the _yieldTo address will result in only the resulting
    yield to be redirected. The Stake ownership will be retained by the caller. This also means when minting a FlashNFT,
    this will be retained by the caller (Staker).

Unstake
^^^^^^^

.. code-block:: solidity

    function unstake(
        uint256 _id,
        bool _isNFT,
        uint256 _fTokenToBurn
    ) external nonReentrant returns (uint256 _principalReturned, uint256 _fTokensBurned) {

The *unstake* method unstakes your Flashstake/stake, either partially or completely. Parameters:

* **_id**: your stake's ID.
* **_isNFT**: true if your stake has been minted as an NFT; false otherwise.
* **_fTokenToBurn**: amount of fTokens to be burnt to unstake your desired amount of principal for your stake.

.. note::
    Stakes that have ended should pass 0 in the _fTokenToBurn parameter.

.. note::
    NFTs are not burned when unstaking - that means the NFTs live forever.

Issue NFT
^^^^^^^^^

.. code-block:: solidity

    function issueNFT(uint256 _stakeId) public returns (uint256 _nftId) {

This methods issues an NFT from a given stake. It can be called at anytime after the stake's creation,
if an NFT wasn't initially minted.

It returns the NFT's ID, which is different from the stake's ID passed as parameter.

Get stake info
^^^^^^^^^^^^^^

.. code-block:: solidity

    function getStakeInfo(uint256 _id, bool _isNFT) external view returns (StakeStruct memory _stake) {

This method will return all the information for a given stake. The information returned is as follows:

.. code-block:: solidity

    struct StakeStruct {
        address stakerAddress; // Address of staker
        address strategyAddress; // Address of strategy being used
        uint256 stakeStartTs; // Unix timestamp of when stake started
        uint256 stakeDuration; // Time in seconds from start time until stake ends
        uint256 stakedAmount; // The amount of tokens staked
        bool active; // Stake has been removed/unstaked
        uint256 nftId; // NFT id if set
        uint256 fTokensToUser; // How many fERC20 tokens were minted
        uint256 fTokensFee; // How many fERC20 tokens were taken as fee
        uint256 totalFTokenBurned; // The total fTokens burned against this Stake (early unstaking related)
        uint256 totalStakedWithdrawn; // The total staked tokens withdrawn from this Stake (early unstaking related)
    }


Set Mint Fee Info
^^^^^^^^^^^^^^

.. code-block:: solidity

    function setMintFeeInfo(address _feeRecipient, uint96 _feePercentageBasis) external onlyOwner {


* **_feeRecipient**: the address the fees will go to
* **_feePercentageBasis**: the percentage of fees to take upon fToken minting

It allows the Owner to set a global fToken mint fee up to a
hardcoded maximum of 20%. This means if 1,000 fTokens are minted during the Stake process and the fee is
set to 20%, the user will receive 800 fTokens.

.. note::
    This function can only be called by the Owner.

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
* **_fTokenAddress**: address of the newly registered strategy's fToken.



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
* **_fTokensBurned**: amount of fTokens burned to perform the unstake.
* **_stakeFinished**: true if all staked tokens were removed from stake, false otherwise.

NFT Issued
^^^^^^^^^^^^^^^^^^^

.. code-block:: solidity

    event NFTIssued(uint256 _stakeId, uint256 nftId);

* **_stakeId**: ID of the stake.
* **nftId**: ID of the newly minted NFT.


Error Messages
---------------

SNE: Stake Not Exists
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The provided stake reference points to a Stake that is not active.

NSO: Not Stake Owner
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The caller does not own the referenced Stake.

NNO: Not NFT Owner
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The caller is not the owner of the supplied NFT id

SNM: Stake NFT Missing
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The required NFT is missing from the callers wallet.

NTR: NFT Token Required
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The user may either; not have the associated NFT to the specified Stake or there is no Stake associated to the referenced NFT id.

MIN DUR 1HR
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The Flash Protocol enforces a waiting time of 1 hour before callers can unstake early.

ISD: Invalid Stake Duration
^^^^^^^^^^^^^^^^^^^

Function: Unstake

Reason: The supplied _stakeDuration is either not greater 60 seconds or is greater than the max Stake duration as
specified by the Flash Strategy.


EMD: Exceeds Max Duration
^^^^^^^^^^^^^^^^^^^

Function: Stake

Reason: The user may either; not have the associated NFT to the specified Stake or there is no Stake associated to the
provided NFT Id.
