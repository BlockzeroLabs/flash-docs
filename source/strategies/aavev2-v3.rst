AAVEv2-V3 Strategies
===============
You can read more about overall security and risks of using the Flashstake Protocol by heading over to :doc:`Security </security>`.

.. important::
    Flashstake Strategies are used by the Flashstake Protocol to facilitate where the staked tokens are directed towards
    as well as how up-front yield is generated when burning fTokens.

    Flashstake Strategies can be developed and registered with the Flashstake Protocol by anyone but the Flashstake
    DAO chooses which Strategies are listed on the frontend located at app.flashstake.io

Contract Addresses
------------------------------

+----------+---------------------------------------------+--------------+---------------------------------------------+
| Network  | Contract Address                            | fToken Name  | fToken Address                              |
+==========+=============================================+==============+=============================================+
| Ethereum | 0xA3F8115F38356a78898D0D3d50faE356A83AC13d  | fCRV-A3F8    | 0x93eE9a13daEC3AAA3C18bFdAC9581a3B92e3530C  |
+----------+---------------------------------------------+--------------+---------------------------------------------+
| Ethereum | 0xE165d4278f4a629b8Ec906015C95CCEbEC56621a  | fBAL-E165    | 0x5FF6D4E7C30EC99F55fD33bD2447c1644fA73C1b  |
+----------+---------------------------------------------+--------------+---------------------------------------------+

Please note: The code for this Strategy can be found via block explorers such as Etherscan/Snowtrace.

Strategy Information
------------------------------
AAVEv2-V3 strategies are the second generation of strategies build on top of the AAVE protocol (AAVE version 2).

This strategy is exactly the same as the :doc:`AAVEv2-V1 strategy </strategies/aavev2-v1>` but introduces
additional Controller Powers such as the ability to set the maximum staking duration, permanently lock the
maximum staking duration, permanently lock the UserIncentive address and the ability to update the UserIncentive
address.

Please note this strategy does not allow the Controller to manage deposited funds in any way. The strategy Controller
cannot withdraw principal tokens or yield tokens (aTokens in this case).

Risks
------------------------------
- In the event a smart contract bug is found in this strategy the Owner/Controller has no ability to "Rescue" funds.
- In the event the underlying protocol is compromised, staked tokens may be at risk.
- In the event the underlying protocol has lent out all Staked tokens, you will be unable to unstake until there is sufficient liquidity.

Controller Powers
------------------------------

This Strategy implements Ownable and is controlled by the Flashstake DAO. There are limited powers available over
this contract as explained below:

- Ability to withdraw any ERC20 token that is not the AAVE interest bearing token. This is to ensure users can be refunded if ERC20 tokens are accidentally sent to this address. Please note, principal tokens cannot be withdrawn by the Controller.
- Ability to claim AAVE rewards from the AAVE rewards pool. These rewards will be deposited directly into the contract.
- Ability to update the UserIncentive address at will. This only impacts the number of User Incentive tokens a user receives moving forward.
- Ability to set the maximum staking duration (only effects new stakes)
- Ability to permanently lock the maximum staking duration (only effects new stakes)
- Ability to permanently lock the user incentive address (only effects new stakes)

"Flashstake DAO" consists of a multisig located at the following addresses:

+------------+---------------------------------------------+
| Network    | Multisig Address                            |
+============+=============================================+
| Ethereum   | 0x8603FfE7B00CCd759f28aBfE448454A24cFba581  |
+------------+---------------------------------------------+
| Optimism   | 0x3144F26fBc2421e5E69f87Ff8c54799e60a4fBB9  |
+------------+---------------------------------------------+
