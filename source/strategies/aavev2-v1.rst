AAVEv2-V1 Strategies
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
| Ethereum | 0x89988FB43890C857205Cee04413EF173c93f55fc  | fDAI-8998    | 0x5028c667D1C9DA0A9090f16E1607F60B7717FC6a  |
+----------+---------------------------------------------+--------------+---------------------------------------------+
| Ethereum | 0x15c32F81Df9B00b97B68148B6BdeB72D57f24845  | fUSDC-15c2   | 0xe221bBf1D5960FC420D451206cF2ee0539398aAC  |
+----------+---------------------------------------------+--------------+---------------------------------------------+

Please note: The code for this Strategy can be found via block explorers such as Etherscan/Snowtrace.

Strategy Information
------------------------------
AAVEv2-V1 strategies are the first generation of strategies build on top of the AAVE protocol (AAVE version 2).

This strategy is built on top of AAVEv2 which as of Oct 2022 has a market size of over 5 billion USD.

This Flashstake strategy accepts tokens from depositors and pays upfront yield in kind.

Users can early unstake their principal deposit at any time if in possession of the required amount of fTokens.
The full amount of accumulating yield is available for redeeming fTokens or direct flashstaking.
The deposited stake tokens is redirected to the AAVE-V2 lending pool to generate interest.

This strategy has been tested via testnet competitions which attracted over 10,000 interactions.

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
