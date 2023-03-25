AAVEv2-V2 Strategies
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
| Ethereum | 0x6e5eD1A5901E81F6bC008023d766454D831B6617  | fUSDC-6353   | 0x32ea96f6f2985bd38e4dac3bc08156198bc2324d  |
+----------+---------------------------------------------+--------------+---------------------------------------------+
| Ethereum | 0x8373dd2efCaeA8174136E9d5F729219e47ee94ca  | fWETH-8373   | 0x4d1733b4a6b92056f77b42e01ff05f0f1e863a5a  |
+----------+---------------------------------------------+--------------+---------------------------------------------+
| Ethereum | 0x543134eC56eE444403461519C1Ec8590C7475897  | fSNX-5431    | 0xb66f4bd1a4f0b594fd5c7c3513b14025d072e31d  |
+----------+---------------------------------------------+--------------+---------------------------------------------+

Please note: The code for this Strategy can be found via block explorers such as Etherscan/Snowtrace.

Strategy Information
------------------------------
AAVEv2-V2 strategies are the second generation of strategies build on top of the AAVE protocol (AAVE version 2).

This strategy is exactly the same as the :doc:`AAVEv2-V1 strategy </strategies/aavev2-v1>` with the exception:

- This strategy allows the Controller to update the UserIncentive address at will. This only impacts the number of User Incentive tokens a user receives moving forward.

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

"Flashstake DAO" consists of a multisig located at the following addresses:

+------------+---------------------------------------------+
| Network    | Multisig Address                            |
+============+=============================================+
| Ethereum   | 0x8603FfE7B00CCd759f28aBfE448454A24cFba581  |
+------------+---------------------------------------------+
| Optimism   | 0x3144F26fBc2421e5E69f87Ff8c54799e60a4fBB9  |
+------------+---------------------------------------------+
| Arbitrum   | 0xEeB3f4E245aC01792ECd549d03b91541BC800b31  |
+------------+---------------------------------------------+
