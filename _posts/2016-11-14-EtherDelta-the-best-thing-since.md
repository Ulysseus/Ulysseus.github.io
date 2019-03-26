EtherDelta the best thing since …

Okay so here’s the deal EtherDelta is a smart contract, that allows you trade with others for Tokens issued on the Ethereunm network. So its P2P, decentralized needs no ID or sign up. Since you never send your funds to a central party, they cant get frozen or hacked.

So how to use it, you can either download the Chrome extension MetaMask and install it in Chrome, you get nice Fox that follows your mouse around in the top righthand corner of the browser. <a href="https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?utm_source=chrome-app-launcher-info-dialog">Chrome webstore metamask</a>.

Or download and install the Mist browser.

I suggest get VirtualBox VM and create an ubuntu box on your machine.

Then download and install the Mist Browser.

ethereum/mist
mist - Mist browsergithub.com
Startup the Mist Browser let it sync to the Ethereum mainnet. Send one Ether or .5 Ether to your new wallet.

Wait till it shows up, should not be longer than a minute.

Now in Mist navigate to <a href="etherdelta.github.io">etherdelta</a>. This is the GUI for the contract.

At the top right of the screen you should see a little man with connect written next to it. Click on it, it will ask you if you want to share your identity with ETHERDELTA and what account you want to use, you will have only one account, if its a new install. Click on it and provide your password and its off to the races. You should also click pin app to side bar if its not already selected.

In the EtherDelta GUI, near the top right hand side of the page you will a little man click on it and choose your wallet address from the drop down list.

Now if you look at the left of the screen you will see deposit.

So before you can start trading you need to deposit some Ether. Type in amount you want to deposit and click deposit. The GUI will ask for your password type it in and you are done.

Now here comes the hard part. To actually trade you need to unlock the account, its a Mist issue not an EtherDelta issue.

To do this open a terminal in ubuntu type

```
cd ~/.config/Mist/binaries/Geth/unpacked
```
Then type 
`geth attach`

You should get a > prompt. You are now in geth console mode.

Now type 
`personal.unlockAccount(“0xYour Address here”)

It will respond with Passphrase: type it in. It should respond with true.

Then type `exit.

If you go back to Mist you will be able to trade.

Have fun and give MetaMask a try its even easier.

Of course don’t stick a ton of Ether in this just yet, there’s very low liquidity and as you can see Mist is not up to it yet.

I tried to get it working with Parity to no avail.

