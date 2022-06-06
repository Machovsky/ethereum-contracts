# ethereum-contracts
Disclaimer: You are using this contract on your own responsibility. I can help, but I don't take any responsibility if anything won't work during the mint.

Hello everyone welcomy to my github. I created low gas optimized ERC721 contract for Ethereum network. Here you can find little tutorial how to use it.

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

Set compiler to newest one, click on checkboxes and click on compile. You should see green icon on the left panel.

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

Your contract is ready! :) 
