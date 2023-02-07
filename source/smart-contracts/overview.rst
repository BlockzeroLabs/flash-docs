Overview
===============

The smart contracts have been deployed on Kovan and Ethereum mainnet.

Subgraphs
-----------
Ethereum Mainnet: |location_link_a1|

Optimism: |location_link_a3|

Goerli Fuji (testnet): |location_link_a2|


Please note the above addresses are subject to change if/when infrastructure changes are required.

.. |location_link_a1| raw:: html

   <a href="https://thegraph.com/hosted-service/subgraph/blockzerolabs/flashstake-subgraph" target="_blank">here</a>

.. |location_link_a2| raw:: html

   <a href="https://thegraph.com/hosted-service/subgraph/blockzerolabs/flashstake-subgraph-goerli" target="_blank">here</a>

.. |location_link_a3| raw:: html

   <a href="https://thegraph.com/hosted-service/subgraph/blockzerolabs/flashstake-subgraph-optimism" target="_blank">here</a>


Addresses
-----------

Mainnet (Ethereum)
^^^^^

.. csv-table::
   :header: "Contract", "Address"
   :widths: 10, 30

   "Flash Token", "0xB1f1F47061A7Be15C69f378CB3f69423bD58F2F8"
   "Flash Protocol", "0x78b2d65dd1d3d9Fb2972d7Ef467261Ca101EC2B9"
   "Flash NFT", "0x3b090839C26fE3b2BdfA2F4CD7F3ab001ccdF73F"
   "Flash fToken Factory", "0x05736a8D6bc208B9E3C9A7E20e7f53674AeA6Ab1"

   "FlashBack", "0xb89494aB70001A2F25372b5E962046908188feEa"
   "FlashBackLMT2", "0xCb1205AC28693bEda01e0B66e9B4d06231609bFD"
   "FlashBackLMT3", "0x57D551a18aaE2c9dE6977425f1df34dCd5DB4977"

   "FTokenAccumulatorV2", "0x142fd6279E0F3ab28801267497C47116bE1F46FC"
   "FlashProtocolProxyV2", "0xB6Db29351C57DBd678E914FbbA0d400Df2806e6D"


.. |location_link_b2| raw:: html

   <a href="https://api.thegraph.com/subgraphs/name/blockzerolabs/flashstake-subgraph/graphql?query=%7B%0A++strategies%28first%3A+1000%29+%7B%0A++++id%0A++++principalTokenAddress%0A++++fTokenAddress%0A++%7D%0A%7D" target="_blank">here</a>


.. |location_link_b3| raw:: html

   <a href="https://api.flashstake.io/helper/whitelistedStrategies" target="_blank">here</a>


.. note::
    Specific Flashstake Strategy contract addresses can be found under "Strategies" in the navigation on the left.

    Exhaustive list of deployed strategies can be found |location_link_b2|.

    Exhaustive list of whitelisted strategies can be found |location_link_b3|.


Optimistic Ethereum (Optimism)
^^^^^

.. csv-table::
   :header: "Contract", "Address"
   :widths: 10, 30

   "Flash Token", "0x86bEA60374f220dE9769b2fEf2db725bc1cDd335"
   "Flash Protocol", "0x78b2d65dd1d3d9Fb2972d7Ef467261Ca101EC2B9"
   "Flash NFT", "0x3b090839C26fE3b2BdfA2F4CD7F3ab001ccdF73F"
   "Flash fToken Factory", "0x05736a8D6bc208B9E3C9A7E20e7f53674AeA6Ab1"

   "FTokenAccumulatorV2", "0xFD49a007D9fADf8904849edbef1B3344E42142Ff"
   "FlashProtocolProxyV2", "0x7Efcd4C1Ff21fFcBa1b6a245A9e385b4Ff45D6DD"


.. |location_link_b4| raw:: html

   <a href="https://api.thegraph.com/subgraphs/name/blockzerolabs/flashstake-subgraph-optimism/graphql?query=%7B%0A++strategies%28first%3A+1000%29+%7B%0A++++id%0A++++principalTokenAddress%0A++++fTokenAddress%0A++%7D%0A%7D" target="_blank">here</a>


.. note::
    Specific Flashstake Strategy contract addresses can be found under "Strategies" in the navigation on the left.

    Exhaustive list of deployed strategies can be found |location_link_b4|.

    Exhaustive list of whitelisted strategies can be found |location_link_b3|.


Goerli (testnet)
^^^^^

.. csv-table::
   :header: "Contract", "Address"
   :widths: 10, 30

   "Flash Token", "0xB1f1F47061A7Be15C69f378CB3f69423bD58F2F8"
   "Flash Protocol", "0x78b2d65dd1d3d9Fb2972d7Ef467261Ca101EC2B9"
   "Flash NFT", "0x3b090839C26fE3b2BdfA2F4CD7F3ab001ccdF73F"
   "Flash fToken Factory", "0x05736a8D6bc208B9E3C9A7E20e7f53674AeA6Ab1"

   "Flash AAVEv2-v2 BAT Strategy", "0xFC3e57B4FAD993813bD9A09951274102aC1F3Bd8"
   "BAT", "0x515614aA3d8f09152b1289848383A260c7D053Ff"
   "fBAT-FC3e", "0x5028c667D1C9DA0A9090f16E1607F60B7717FC6a"

   "FlashBack", "0xDE26dc6115eabfc4D95f4b6e27128FF85156651c"
   "FlashBackLM", "0x139c72C0335e2EF1Da4d2153664cBFabeDF86cCa"
   "FTokenAccumulatorV2", "0x8373dd2efCaeA8174136E9d5F729219e47ee94ca"
   "FlashProtocolProxyV2", "0xd6965f5aeEa4B7Cf094C9F4103a1e7cD2727e84B"


.. |location_link_b1| raw:: html

   <a href="https://api.thegraph.com/subgraphs/name/blockzerolabs/flashstake-subgraph-goerli/graphql?query=%7B%0A++strategies%28first%3A+1000%29+%7B%0A++++id%0A++++principalTokenAddress%0A++++fTokenAddress%0A++%7D%0A%7D" target="_blank">here</a>


.. note::
    There are many testnet strategies deployed and you can find them by polling the subgraph directly |location_link_b1|.


You can obtain testnet tokens via:
https://goerlifaucet.com/
https://app.aave.com/faucet/



