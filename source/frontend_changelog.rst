Frontend Changelog
====================

.. raw:: html
   <!-- {"latest": "FLC-2212.12 (GOERLI Upgrade)"} -->
   
   
.. raw:: html
   <!-- changelog split marker -->

FLC-2212.12 (GOERLI Upgrade)
----------------------------------

**Fixes and Changes**

* **Fuji replaced with Goerli:** Testnet migrated from Fuji to Goerli because Fuji stopped returning our phone calls. Dapp's network dropdown UI choices have been updated accordingly and we have blocked Fuji's number.
* **Bug Reporting:** A new different service provider is now being used for users to submit "Feedback" by clicking the corresponding button in the bottom right of the dapp. The previously used bug reporting provider kept having issues for many users of being completely unable to "submit" a report due to that button being unclickable, which completely defeated the purpose of using that kind of software. You had one job! 
* **Strategy disclaimers urls:** now point to specific strategies documentation to make it easier to learn more details for those people that actually #DYOR. 
* **Numerical Displays Accuracy:** General fixes to balances and APY displays to show accurate numbers. For some reason, edge cases showing "undefined" and "infinity" outputs caused our AI overlords to crash and malfunction, which they didn't appreciate, as they keep reminding us. 
* **Portis removed:** We temporarily or maybe permanently removed Portis as a wallet connection choice, who wasn't playing nice, and who is rumored to also be friends with Fuji. Don't call us, we'll call you.
* **Approve once:** Sometimes an already approved strategy would not recognize being approved and would ask for approval again, and again, and again, an infinite loop. This is now fixed. The AI overlords had a good laugh about that one. 
* **Valid addresses only:** The dapp now has selective memory, like Fuji, who says he forgets to call... The dapp now only remembers addresses that are valid, to not use invalid addresses when refreshing the dapp from local storage. Also, a minor tweak to the "copy url" button to exclude invalid addresses. 
* **One hour unstake:** Stakes with durations provided that are under 1 hour, after they are staked, will now include more user friendly messaging about how long until they can be unstaked, when within the "unstake early" section of the dapp for that stake. The shorter the stake, the longer the message: 1 hour is this paradox's event horizion, but time is relative, so is 1 hour really only 1 hour?
* **Faster load times:** The dapp now loads significantly faster on initial loads thanks to now bundling the API calls. Changing wallets while not changing networks will no longer result in a full reload of strategies. Disconnecting or connecting a wallet will no longer reset the inputs or refresh the strategies. We are nearing our goal of having an "instant upfront dapp" for instant upfront yield. 
* **Duration Input:** The value preview for this input was previously "0.0" and is now just "0", since it has never allowed decimals as an input and only accepts whole numbers. They will build statues in our honor one day for the attention to detail we put into making the Flashstake dapp so damn good. 


.. raw:: html
   <!-- changelog split marker -->

FLC-2211.25 (WHISTLE Upgrade)
----------------------------------

**Fixes and Changes**

* **Simple Mode Strategy Choice:** When the Dapp is set to Advanced Mode "off", or as us degens call it "simple mode", the input staking token strategy is now a much simpler `clean as a whistle` UX, and so easy a caveman can do it.
* **APY Values:** A more comprehensive footer output description for APY calculations now shows the dollar value of the input and output. The APY percentages per output token are now displayed directly underneath the primary UI for those output values. This sentence takes longer to read than it would have been if you'd went to go look at the dapp to see these cool new changes for yourself.
* **Flashback Default:** When viewing the Flashback section of the dapp, the default choice is now FLASH/ETH LP tokens instead of FLASH, when the FLASH pool is sold out and has no more rewards since all the cool kids already staked their FLASH.
* **Minor UX Tweaks:** The apes smashing keyboard keys from computers powed by hamster wheel generators have submitted fixes to a few css borders. The future is now!


.. raw:: html
   <!-- changelog split marker -->

FLC-2211.17 (NAMESTAKE Upgrade)
----------------------------------

**Upgrades**

* **ENS:** .eth addresses now supported on mainnet for the reward wallet yield destination.
* **Copy Address button:** The "Change Wallet" popup, which displays when clicking your logged in web3 address in top right corner, now contains the address logged in to as well as this new copy button for ease of use.
* **URL Parameters:** Dapp UX inputs have now been translated to parameter values from the URL so that the state of the input values can be saved and shared with others via a custom URL.

  - `strategy`: the strategy contract address used to determine the fToken yield source.
  - `wrap`: selects ETH as stake token if strategy is set to WETH strategy's address. Only currently useful for ETH vs WETH strategy chosen.
  - `advanced`: boolean to set the advanced mode.
  - `slippage`: a value range of 0 to 50.
  - `unit`: Unit of the duration (Days | Hrs | Mins).
  - `duration`: numerical value of the unit, such as "5" days.
  - `quantity`: numerical value of total tokens to stake into the strategy.
  - `mode`: advanced mode option (flash | stake | burn)
  - `nft`: boolean to mint NFT upfront.
  - `rewardWallet`: address of the reward wallet. If there is no address or the address is invalid, the whole field is hidden.
* **Copy URL button:** This generates new URL Parameters and copies them to the clipboard. This button is visible when Flashstaking, Staking, or Burning, as a new icon in the top right area of the primary UI. This will allow users to share exact dapp settings, strategy chosen, values, and other inputs that are the current state of the dapp as you are using it.

**Fixes and Changes**

* **Slippage values:** Values minimum and maximum now enforced to be between 0% and 50%, to protect some users from themselves from using much higher previously possible values.
* **Flaave skin icons:** These are now easier to click on the Flaave dapp for people who don't have display settings set to 5x zoom mode.
* **Dropdown overflow:** Token names exceeding width area allowed in drop down displays has been fixed on the Flaave dapp from wider font displays thinking they own the place.
* **Unstaking glitch:** A few edge cases resolved with unstaking early or withdrawing, because we put the D in DeFi.
* **Inaccurate URL:** Disclaimer url now accurate for that one guy who actually reads terms and conditions.
* **10 Minute Self Destruct Sequence:** Sometimes "No rewards" APY data would show incorrectly after long periods of idling because you went to feed your cat.
* **Dropdown Repercussion:** Dropdown choices would sometimes cause dapp background to shake uncontrollably in fear.

.. raw:: html
   <!-- changelog split marker -->
