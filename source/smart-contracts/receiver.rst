Building Flash Receiver
=======================


In the example below you can find a simple example for a flash receiver that can be used by the Flash Protocol.

We'll define a function required by the Flash Protocol called ``receiveFlash`` and we'll simply collect the yield and reward the staker with half of the yield amount in DAI.
So if the user stakes **1000 $FLASH** with **10% FPY**, we'll receive **100 $FLASH** and we'll send him **50 DAI**.

.. note::
    The code below is used **only** for example and testing. Do not use on production.

.. code-block:: solidity

    // SPDX-License-Identifier: GPL-3.0
    pragma solidity ^0.6.0;

    import '@openzeppelin/contracts/math/SafeMath.sol';
    import './interfaces/ERC20.sol';

    contract FlashReceiver {
        using SafeMath for uint256;

        address public constant FLASH_PROTOCOL = 0x2Fec418941c8E710372625Df48F32b69Cf4431A9;
        address public constant DAI_ADDRESS = 0x6b175474e89094c44da98b954eedeac495271d0f;

        modifier onlyFlashProtocol() {
            require(msg.sender == FLASH_PROTOCOL, 'Only FlashProtocol can call this');
            _;
        }

        function receiveFlash(
            uint256 amountIn,
            uint256 expireAfter,
            uint256 mintedAmount,
            address staker
        ) public override onlyFlashProtocol returns (uint256) {
            uint256 daiReward = mintedAmount.div(2);
            IERC20(DAI_ADDRESS).transfer(staker, daiReward);
            return daiReward;
        }
    }


Now, if we deploy the contract we can use the contract address in the ``receiver`` field when calling ``stake`` and we'll redirect the user's yield to that contract.
The result would be that the user will stake **$FLASH** and receive **$DAI**.