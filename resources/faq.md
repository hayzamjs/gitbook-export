---
description: Frequently Asked Questions About Scala.
---

# FAQ

## My balance is incorrect or shows 0

If you open your wallet and your balance is not showing the proper value, chances are your wallet is out of sync. Check to see if your wallet is syncronized by comparing your wallet blockheight with the network blockheight found on the Scala [Block Explorer](https://explorer.scalaproject.io/). If your wallet is out of sync, follow these simple steps:

**For Scala Electron GUI Wallet:**

1. Visit the "settings page" located within the tab bar at the top left hand corner of your Scala wallet.
2. Once in settings, navigate to the two bars at the top, and make sure that you are on a working node. To find working nodes you can visit our Scala Discord channel.
3. Save your changes, the wallet will ask you to restart in order to apply. Restart wallet, and log in to your wallet account.
4. Allow the Scala wallet to fully synchronize, this may take several minutes to complete.

**Scala CLI Wallet Local Node:**

1. Within the scala Daemon command prompt type, "status." Record the blockhight of your local daemon and compare it with the network blockheight on the [Scala Block Explorer](https://explorer.scalaproject.io/).
2. If your blockheight is incorrect, type in to the command line: Pop\_blocks 5000
3. Allow the Scala daemon to fully synchronize with the blockchain. After it is finished synchronizing, again type, "status." The blockheight should return the correct value.
4. Open up the CLI wallet and sign in to your wallet account. Let the wallet verify with your newly synced ledger

## Restore your Scala wallet from seed

Always save your Mnemonic seed words in a safe, private location anytime you create a new wallet. To access your wallet on a new device, or restore your wallet,  you can enter your Mnemonic seed words into the wallet system.

**For Scala Electron GUI Wallet:**

1. Open your Scala Electron GUI wallet.&#x20;
2. At the top right of your wallet main page screen you will see a "+" symbol tab. Within that tab select, "restore wallet from seed."
3. Choose a name, and password for your new wallet.
4. Copy and paste your Mnemonic seed into the correct bar.
5. Select, "restore wallet."

**Scala CLI Wallet:**

1. Locate the Scala directory on your computer.
2. Within the Scala directory, create a new text file.
3. Open the text file and within it add: scala-wallet-cli.exe --restore-deterministic-wallet
4. Save the text file to your Scala folder as a .bat file.
5. Run the .bat file, follow the onscreen instructions in the command line interface.
6. After you restore your wallet in the .bat-cli, open your CLI wallet and select your new wallet.

## How do I install and use the Scala CPU Miner?

The XLArig miner is an application developped to mine XLA with CPU. Always be conscious of your processor temperatures and utilization, running equipment at high usage for long periods of time can result in malfunctions. Mine responsibly.

**XLArig :**

1. Install the XLArig miner, located [here.](https://github.com/scala-network/XLArig/releases)
2. Extract the download to a location of your choice.
3. Open the XLArig folder, and create a new .text document within the folder location.
4. Within the .text document, paste the following text: xlarig.exe -o \<Your Mining Pool> -u \<Your Scala wallet address> -p x --algo panthera
5. Save the .text document as a .bat, and run the new .bat file that you have now created in your XLArig folder.

## How do I install and use the Scala Android Mobile Miner?

Scala Mobile Miner:

1. Download and install the Scala Mobile Miner from the Scala Github found [here.](https://github.com/scala-network/MobileMiner/releases)
2. After Installation, open the app and open settings within the options tab located on the top left hand corner of the app.
3. Once in settings,  paste your pool info: \<Scala pool:port> and paste your Scala wallet address.
4. Choose the number of CPU cores that you wish to use in your _armv_ processor. Save. (more cores = more hashes). Note: The more cores you use, the hotter the device will be, and the slower that it will operate.
5. Go back to the "Miner" page, and tap start on the bottom right hand corner of the screen.
6. View your mobile device hashrate located at the top left-hand side of the miner's page screen. Total = all miners hashrate connected to that pool combined.
7. Visit the "Statistics" page to view network and pool information.

