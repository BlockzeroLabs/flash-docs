AAVEv3 Strategies
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
| Optimism | 0x28b413F9f09fBA829A4C0B43783541373Ee3F6C3  | fsUSD-28b4   | 0x5028c667D1C9DA0A9090f16E1607F60B7717FC6a  |
+----------+---------------------------------------------+--------------+---------------------------------------------+

Please note: The code for this Strategy can be found via block explorers such as Etherscan/Snowtrace.

Strategy Information
------------------------------
This is the first generation of strategies build on top of the AAVE V3 protocol.

This strategy is built on top of AAVEv3 which as of Oct 2022 has a market size of over 1 billion USD.

This strategy is very similar to the :doc:`AAVEv2-V1 strategy </strategies/aavev2-v1>` but has been adapted to interact
with the third version of AAVE protocol (v3). This strategy has been specifically tailored for layer 2 use.

Please note this strategy does not allow the Controller to manage deposited funds in any way. The strategy Controller
cannot withdraw principal tokens or yield tokens (aTokens in this case).

Risks
------------------------------
- In the event a smart contract bug is found in this strategy the Owner/Controller has no ability to "Rescue" funds.
- In the event the underlying protocol is compromised, staked tokens may be at risk.
- In the event the underlying protocol has lent out all Staked tokens, you will be unable to unstake until there is sufficient liquidity.

Controller Powers
------------------------------
.. |location_link_aave_ref_code| raw:: html

   <a href="https://docs.aave.com/developers/v/1.0/integrating-aave/referral-program" target="_blank">refCode</a>

This Strategy implements Ownable and is controlled by the Flashstake DAO. There are limited powers available over
this contract as explained below:

- Ability to withdraw any ERC20 token that is not the AAVE interest bearing token. This is to ensure users can be refunded if ERC20 tokens are accidentally sent to this address. Please note, principal tokens cannot be withdrawn by the Controller.
- Ability to claim AAVE rewards from the AAVE rewards pool. These rewards will be deposited directly to the configured address
- Ability to update the UserIncentive address at will. This only impacts the number of User Incentive tokens a user receives moving forward.
- Ability to set the maximum staking duration (only impacts new stakes)
- Ability to permanently lock the maximum staking duration (only impacts new stakes)
- Ability to permanently lock the user incentive address (only impacts new stakes)
- Ability to set the AAVE |location_link_aave_ref_code| and address where AAVE incentive rewards are redirected to (only impacts new stakes)

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
