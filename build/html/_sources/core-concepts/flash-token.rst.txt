Flash Token
===========

Flash Token (**$FLASH**) is an Ethereum token that enables interacting with the Flash Protocol. 

FLASH contract address is: <TODO: TOKEN_ADDRESS>

The Flash Token does not have a fixed supply. **$FLASH** is minted on every stake and it's burned on every unstake (only if the staking period has not been elapsed).
The process of minting can only be achieved using the Flash Protocol.

The inflation rate of the token is corelated to the usage of Flash protocol, the **FPY** (Flash Percentage Yield) and the matching ratio.

The token follows the ERC20 standard with few extensions:
    - ERC-3009 - transfer with authorization, which enables gasless transactions
    - flash mint - allows to flash mint (using similar concept to flash loans) an arbitrary amount of **$FLASH**, with the condition that the minted amount is burned before the end of the transaction.
    - an exposed mint() and burn() functions which can be invoked only by the flash protocol


Flashminting
------------

The flash mint implementation is the following:

.. code-block:: solidity

    function flashMint(uint256 value, bytes calldata data) external {
        flashSupply = flashSupply.add(value);
        require(flashSupply <= type(uint112).max, "FlashToken:: SUPPLY_LIMIT_EXCEED");
        balanceOf[msg.sender] = balanceOf[msg.sender].add(value);
        emit Transfer(address(0), msg.sender, value);

        IFlashMinter(msg.sender).executeOnFlashMint(data);

        require(balanceOf[msg.sender] >= value, "FlashToken:: TRANSFER_EXCEED_BALANCE");
        balanceOf[msg.sender] = balanceOf[msg.sender].sub(value);
        flashSupply = flashSupply.sub(value);
        emit Transfer(msg.sender, address(0), value);
    }

In order to use the flashminting functionality you have to build a smart contract that implements the following interface:

.. code-block:: solidity

    function executeOnFlashMint(bytes calldata data) external;

then the smart contract must make a call to:

.. code-block:: solidity

    function flashMint(uint256 value, bytes calldata data)