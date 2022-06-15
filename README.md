# Read me first!!!
Disclaimer: You are using this contract on your own responsibility. I can help, but I don't take any responsibility if anything won't work during the mint.
Hello everyone welcomy to my github. I created low gas optimized ERC721 contract for Ethereum network. Here you can find little tutorial how to use it.
If any help will be needed, feel free to ask me on discord **arczi.eth#7777**

# What are this contracts about?
ContractNFTLowGasERC721A.sol - ERC721A optimized contract with lower gas fees. This contract will let you create mint which has:
2 stages - first for example free mint, second with paid mints

To give you better example - you have 5000 NFT collection. With this contract you can make free mint for first 2000 NFTs and then 3000 paid mints. 

**Costs of mint in both phases, amount of mints per tx for both phases, amount of mints per wallet, total supply, mint pause and reveal after mint are fully configurable!** 

Tutorial of how to configure everything you can find below in next README chapters.

# How to prepare contract for your project?


First thing - go to Remix https://remix.ethereum.org/ and create a new workspace

![image](https://user-images.githubusercontent.com/32854636/172213493-d3e2003f-7800-480b-a14c-744da0c2fd77.png)

Then delete all files inside folders in your workspace:

![image](https://user-images.githubusercontent.com/32854636/172213653-dab7f39e-dca2-4e04-a71a-bd9d0342ca7b.png)

It should look like this and be empty:

![image](https://user-images.githubusercontent.com/32854636/172213696-f6919be5-f51d-4df9-b74b-2fd8bf28cba8.png)

Then, add downloaded NFT contract - for this case we will use SampleNFTLowGas.sol contract. Open it and copy whole code from inside, then go back to remix and paste your code there as new file into "contracts" folder. After you paste file content, press ctrl+s to run compiler. You will see that compiler will process everything and create a bunch of new files. Don't worry about them. It should look like this:

![image](https://user-images.githubusercontent.com/32854636/172214810-68b84814-65c1-43ba-9531-45fd4d87d6fc.png)

If you have done everything correctly and you have same result as me, go to the code you pasted, starting from line 12. That will be only changes that you want to change in the contract.
![image](https://user-images.githubusercontent.com/32854636/172215134-7738c584-c74a-466f-9ec4-98f4c204e09a.png)

To summary a little - this is just example. I will create a bunch of contracts - separated for phases with different prices and others which have always the same price. Limited for amount of mints per wallet per phase etc. Don't bother about it now. If you want some other behavior and you don't know how to do that, just write straight to me on discord - https://discord.com/users/arczi.eth#7777

For this example
**cost1** - cost of phase 1

**cost2** - cost of phase 2

**supplyPhase1** - supply for phase 1 (amount of mints you wan't to sell using cost1)

**totalSupply** - whole supply of NFT collection

**maxMintAmountPerTxPhase1** - mint amount per transaction with phase 1 cost

**maxMintAmountPerTxPhase2** - mint amount per transaction with regular cost

**maxLimitPerWallet** - mint amount per wallet (for example if maxAmountPerTx is 10 and maxLimitPerWallet is 20, then you can mint 2 times 10 NFT's per transaction)

**sale** - if sale is set to false it means, that contract is paused automatically. Let it like it is. We will change that when we will start mint.

**revealed** - if revealed is set to false it means that you want to leave nft hidden using separate image.

Next part that you have to change is constructor part - that strings (the orange color). Leave " as they are, but change what is inside. First one is full name of your NFT collection. Second one is short name - best practice is to use 3 big letters for it. For example when we have something like AI Goblins, as short name use AIG letters.

![image](https://user-images.githubusercontent.com/32854636/172217911-f698a37d-063f-4f0f-842d-858a929f90ac.png)

If everything is done and saved by clicking ctrl+s, go to the left menu and choose this icon.

![image](https://user-images.githubusercontent.com/32854636/172219094-7d6af44a-ddbc-4563-8af4-13d064f9cc0a.png)

Set compiler to newest one. Check "Auto compile" checkbox, then expand advanced options and check "Enable optimization" checkbox with value set to 200.

![image](https://user-images.githubusercontent.com/32854636/172219454-f08b7f5e-033c-4b37-8292-f6b89d436417.png)

If all works fine, go to left panel document view, find again your file and right click, choosing "Flatten" option.

![image](https://user-images.githubusercontent.com/32854636/172219629-76f8256a-27d5-4d6e-ac4a-921913e992dd.png)

After few second you will find flattener pop-up window. Click on "Accept"

![image](https://user-images.githubusercontent.com/32854636/172219746-b9acec9f-453b-46e5-b1cc-5c5da536120d.png)

After you accept that, you will see that a lot of new items were created. At the bottom of your files you will find new .sol file, called as your previous file but with added _flat in name.

![image](https://user-images.githubusercontent.com/32854636/172220561-1bf14256-573f-4abf-a364-67657d83521b.png)

Click on that file - you will see red exclamation mark in first line.

![image](https://user-images.githubusercontent.com/32854636/172221135-e8c40c2a-e21f-40ff-a124-40b3426594b7.png)

Add there code:
// SPDX-License-Identifier: MIT

copy it with "//" sign.

Now error is gone and we don't have any additional errors to fix.

![image](https://user-images.githubusercontent.com/32854636/172220877-e5c52de0-99dc-40af-afb3-394fd8c955db.png)

Your contract is ready to deploy! :) 

# How to approve contract?

After you have done all of above steps, it's time for contract deploy and getting an approval from etherscan!
First thing to do now - go to "Deploy & Run transaction" and then choose "Injected Web3" from environment dropdown - remember to have the correct wallet chosen. The wallet which is connected to the site will be owner of the contract and after mint all money will be transferred back to wallet which is the contract owner.
Just for this tutorial I will use rinkeby testnet just to show you how to proceed all the stuff on your ethereum mainnet. All will look the same! :)

![image](https://user-images.githubusercontent.com/32854636/172670105-1f24d4fc-c64a-4a7e-ac96-6c69e49a1730.png)

Remember to pick correct contract by choosing "ContractName - FileName.sol" like the one on screen below.

![image](https://user-images.githubusercontent.com/32854636/172670772-442a97c7-f779-4956-88a0-4e7646d47c0f.png)

As a next step click on expand button next to orange "Deploy" button.

![image](https://user-images.githubusercontent.com/32854636/172672438-8136d0aa-3084-49a3-a788-f2b3a0e93b9d.png)

As you can see there are 2 empty fields that we have to fill up. I assume that you have already your NFT collection created and you have ipfs CID's to folder with collection and to separate hidden NFT if you want to make a reveal after some time. That empty fields that we have to fill should look like that.

![image](https://user-images.githubusercontent.com/32854636/172673005-55db90fd-3ce3-4a2a-938e-2418993ce47f.png)

First field is called _URI_. We need to add there ipfs address to our folder with whole collection metadata (.json files). It should be in this format:
**ipfs://HerePasteYourCIDAddressToFolderWithWholeCollectionMetadata/**  - remember about / at the end of uri. Metadata folder means whole folder with .json files.

Next field is _HiddenMetadataUri_ is field where you add ipfs address to folder with hidden metadata files. Probably it will be only 1 picture but it have to be pasted separately. Format should look the same way:
**ipfs://HerePasteYourCIDAddressToFolderWithHiddenImageMetadata/**

If you are not going to make a reveal, just leave this field empty and verify if you changed variable "revealed" to "true".

![image](https://user-images.githubusercontent.com/32854636/172684741-083fd1c8-a9c2-4b79-a796-f0906863bbd2.png)

If you have done this, don't click "Transact" yet. First click on copy button next to transact:

![image](https://user-images.githubusercontent.com/32854636/172674674-ca8ec8fb-ae5f-456e-a7e9-1e99b1263ca1.png)

Open notepad or some document editor and paste what you have copied. It will look similar to this:

![image](https://user-images.githubusercontent.com/32854636/172674934-910f40d8-3005-4792-b5c3-06d6b1c5888b.png)

After you done this, save it somewhere not to lose it and now you can click "Transact"

![image](https://user-images.githubusercontent.com/32854636/172675257-b76a5f0e-d4ca-4327-bdaf-8738f97c379b.png)

After you click it, you will see metamask notification to create a contract. After you approve this, your contract will be created and wallet that you used will be the owner of the contract.

![image](https://user-images.githubusercontent.com/32854636/172675433-cca4e721-1654-479e-85d4-d702596c79fa.png)

At the bottom of remix ide, you will see that contract was deployed. Just click on button to expand and then click on copy button next to contract again:

![image](https://user-images.githubusercontent.com/32854636/172680220-925218ae-d347-4691-a420-67c5c5e10074.png)

Do the same as before - paste it to some file. This is your contract address which you can find already on etherscan.
If you have your address copied, go now to etherscan and search for the contract.

![image](https://user-images.githubusercontent.com/32854636/172681028-c025e5f9-6bf4-43a7-ba5d-b8b3ebd81482.png)

You will see there whole information about the contract and also the only transaction which was creation of contract.

![image](https://user-images.githubusercontent.com/32854636/172681164-2b48f4a4-4628-4f50-8c8f-9f5f962795af.png)

Go now to "Contract" page:

![image](https://user-images.githubusercontent.com/32854636/172681328-4aab028c-cc65-45d4-a2c0-a7a8f8aa7fc0.png)

Then click "Verify and Publish" to verify your contract.

![image](https://user-images.githubusercontent.com/32854636/172681491-1d399462-d967-4d2b-9d04-da2f5a05cb87.png)

On the next page we need to pick some options about our contract. 

  1. Compiler type - we are using flattened version of the contract. That means all libraries are "packed" into one file. In that case we pick here "Solidity (Single file)" option

  2. Compiler version - should be the same as in compiler tab in Remix IDE - automatically probably newest one. If you used different version, just change it to the one you have used.
  3. License - we pick MIT license.

![image](https://user-images.githubusercontent.com/32854636/172682139-5c9d8826-fc9e-4ca7-bbc6-a84c6a73ebc3.png)

After all is done, click on "Continue".

On the next page we will see window with "Contract Source Code". It should be configured like that:
  1. On the top right corner you will see "Optimization" - change it to "Yes" as you had "Enable optimization" checkbox in remix checked.
  2. In field "Enter the Solidity Contract Code below" you have to paste whole code from remix. It will have more or less about 2k lines, so just click **ctrl+a** to select all and then **ctrl+c** to copy whole contract. 
  3. Next field is "Constructor Arguments ABI-encoded". My contract will be using constructors so this field needs to be filled automatically. If it is not, I will show you how to get it. In next step. 

Finally all should look like this:

![image](https://user-images.githubusercontent.com/32854636/172685528-80f952e2-6109-488a-b162-a0b2ff125ab0.png)

If you don't have ABI filled up automatically, go back to remix to your opened contract, change tab back to "Compiler", change contract to correct one and copy the "ABI" by clicking button visible on the screen:

![image](https://user-images.githubusercontent.com/32854636/172686628-69863ac9-497b-405a-bb76-30c03bd40f0e.png)

Then go to page https://abi.hashex.org/
Paste whole contract ABI there and click on "Parse".

![image](https://user-images.githubusercontent.com/32854636/172686797-eca3e852-a60f-4691-9008-79332875a937.png)

Pick function as "constructor". Then you will see 2 fields - URI and hiddenMetadataUri. You have to paste them your code in the same format as you did previously in remix:

![image](https://user-images.githubusercontent.com/32854636/172687112-2169faec-a258-43e6-9ffb-05da2eeb3f27.png)

^ it should be the same as this:

![image](https://user-images.githubusercontent.com/32854636/172687174-00084f92-ae55-4199-b4ae-778c04c8d7e9.png)

After you do it, you will see your constructor ABI encoded. Just copy it and paste on etherscan :)

One more thing - the same you can find just in your copied encoded number that we pasted to notepad. At the end of the string you will see that it have a lot of 0's. Just try to copy it starting from the first zero if you have any problems using ABI encoder.

![image](https://user-images.githubusercontent.com/32854636/172688037-2fefe934-20e8-485f-9705-28bacad5ab94.png)


Let's continue with etherscan. If you have your ABI there, just click on "Verify and Publish".

![image](https://user-images.githubusercontent.com/32854636/172688202-56625d09-ec46-4146-83df-e0ce9881e120.png)

If everything is okay, you will see such screen with message:
"Successfully generated ByteCode and ABI for Contract Address"

![image](https://user-images.githubusercontent.com/32854636/172688361-6913b10a-c25c-48b6-846a-379c347b6f0b.png)

Congratulations! You have verified your contract! :)

If you go back to your contract, now you will see that it has green check.

![image](https://user-images.githubusercontent.com/32854636/172688638-50fbc721-2f12-470f-abf3-397566e930a8.png)


# How to start minting or change anything on the contract?

So now let's focus on mint management. Contract is paused by default. If you want to unlock your mint just go to etherscan, then pick "Contract" tab and then "Write contract". Below you will see "Connect to web3" button. Click it and connect to your wallet which is owner of the contract.

![image](https://user-images.githubusercontent.com/32854636/172689085-090e75f8-10cd-46a5-b4f6-f80d8171b1d4.png)

Connected wallet should look like that:

![image](https://user-images.githubusercontent.com/32854636/172689147-882f090b-1135-49f7-8e30-427002217a01.png)

Now you have bunch of options there where you can manage your whole contract. 

![image](https://user-images.githubusercontent.com/32854636/172689253-e2b8308c-0f7e-41ed-8856-68324030525c.png)

**1. Airdrop of NFT's.**
If you want to airdrop NFT's to some wallet, just use "Airdrop" function.
In mintAmount type amounts of NFT's you want to drop, and in receiver just write address that should be airdropped.
After that click on "Write" and confirm transaction on Metamask.

![image](https://user-images.githubusercontent.com/32854636/172689565-8c90da72-57ee-4912-b93d-73a7a28495d8.png)

**2. Unlock minting option.**
If you have mint paused, you can unlock it by searching for "SetSaleStatus" function. Expand it and write "true" if you want to unlock minting. Then click on "Write" and confirm your action on MetaMask.

![image](https://user-images.githubusercontent.com/32854636/172689945-d60a574f-a84f-4c4d-986e-6b6f9c5acca0.png)

**3. Changing the price.** 
If you want to change the price during mint just find option "setcost1" or "setcost2" (in this case. some contracts will have only one cost). Again expand that function and set cost as you wish. **Remember that price is not in ethers!!! It uses wei instead!!!** For example if price is set to 0.003 ethers it is saved as 3000000000000000 wei. If you want to change your price, just go to https://eth-converter.com/ and there you can convert your price from ethers to wei.

![image](https://user-images.githubusercontent.com/32854636/172690564-b0261e77-e231-486b-9c22-187fd6d57cff.png)

# How to withdraw money?

That's the most important part for every NFT creator :D In contract you will find function "Withdraw"
If you want to withdraw your money, just expand the function, click on write and confirm transaction on metamask.

![image](https://user-images.githubusercontent.com/32854636/172694816-690fbaad-62ad-4237-8597-60e26627cf3b.png)

You will have to use owner wallet to do all that transactions. If you try to use other wallet you will get error:

![image](https://user-images.githubusercontent.com/32854636/172694954-6e3b0c51-fc89-439e-82bb-51f6758fd392.png)

So after transaction is approved, money will be automatically transferred to the adress you are using.

Good luck with your projects! :)
