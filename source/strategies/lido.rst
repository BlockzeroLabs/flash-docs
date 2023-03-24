Lido Strategy
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
| Ethereum | 0xB8C60a5C9d73C0406FF279C65E31496a40F0dc5a  | fstETH-B8C6  | 0xe2237a34246eEdCEb43283073Ba9AdeF0450351E  |
+----------+---------------------------------------------+--------------+---------------------------------------------+

Please note: The code for this Strategy can be found via block explorers such as Etherscan.

Strategy Information
------------------------------
This is the very first liquid ETH staking strategy developed for the Flashstake Protocol.

This strategy is built on top of Lido's stETH token which as of Dec 2022 has over 4.5 million ETH staked. This consists
of over 100,000 depositors.

Lido's stETH token is one that represents all the staked ETH within Lido combining both initial deposits and staking
rewards. stETH tokens are minted whenever ETH is deposited and burned when redeemed.

stETH balances automatically rebase (update) every day around 12PM UTC. This means yield increases within this strategy
whenever the rebase occurs.

.. |location_link_lido_1| raw:: html

   <a href="https://help.lido.fi/en/articles/5230610-what-is-steth" target="_blank">https://help.lido.fi/en/articles/5230610-what-is-steth</a>


Learn more: |location_link_lido_1|

Please note this strategy does not allow the Controller to manage deposited funds in any way. The strategy controller
does not have any permission to withdraw stETH (user funds) on a contract level.

Risks
------------------------------
- In the event a smart contract bug is found in this strategy the Owner/Controller has no ability to "Rescue" funds.
- In the event the underlying protocol (Lido) is compromised, staked tokens may be at risk.
- Lido is a centralised system so there is trust involved.
- stETH rebases are performed by the Lido Oracle which is trust based.

Controller Powers
------------------------------

This Strategy implements Ownable and is controlled by the Flashstake DAO. There are limited powers available over
this contract as explained below:

- Ability to withdraw any ERC20 token that is not the stETH token. This is to ensure users can be refunded if ERC20 tokens are accidentally sent to this address. Please note, principal tokens cannot be withdrawn by the Controller.
- Ability to update the UserIncentive address at will. This only impacts the number of User Incentive tokens a user receives moving forward.
- Ability to set the maximum staking duration (only impacts new stakes)
- Ability to permanently lock the maximum staking duration (only impacts new stakes)
- Ability to permanently lock the user incentive address (only impacts new stakes)

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
