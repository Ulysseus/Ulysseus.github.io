Tezos Baking: You loaf/We bake

![Test](/Ulysseus.github.io/_images/1*hy6pwy5Afo8qAajzANF0oA.jpeg?raw=true)


[Delegation Service](https://youloafwebake.io/)

The Tezos network is finally live, albeit in Beta version. So far my experiences; this thing is fast; it’s easy to use once you figure a few things out.

The documentation is poor, not many examples of commands etc etc, but some persistence and you get used to the way they do things, and find your way around. Initially I struggled to get my Tezos out of the funding wallet. It’s amazing what little things like put your password in at one point and then put your passphrase at another will do to you!

I tried baking on the Zeronet so that I was ready for the Betanet, I missed baking on cycle 7 because I was so afraid of stuffing up the claiming of the Tezzies. I did make cycle 8 though.

Tezos has a interesting PoS mechanism. I will not go into details but you can only bake/mine a block assuming you have a roll. A roll is 10 000 Tezzies. If you have less you cannot bake, but you can delegate your Tezzies to someone else; who when they have a round 10 000 can bake. There is literally no risk in delegating, the Baker never gets to see the delegator’s private keys. The Baker posts the bond for the staking to be able to bake. In the event that the Baker is slashed, the person delegating to them loses nothing. The only risk to the person delegating; is that the Baker does not pay out the rewards. Here’s where a transparent immutabule blockchain comes into its own. You can check on a blockchain explorer like [tzscan.io](http://tzscan.io/tz1eZwq8b5cvE2bPKokatLkVMzkxz24z3Don?default=baking), you can see exactly how much the Baker you delegated to has earned. There are three levels of rewards:

Baking rewards 16tz per block

Endorsing rewards 2tz per slot

Fees

Presently transactions will go through with zero fees, but I assume that will change as time goes on.

To run a Baker you need to run a full node, the biggest obstacle here seems to be the hard disk space as the blockchain seems to be growing at a fast pace. You’ll also need a reliable internet connection and power. The only danger is that you miss your turn to bake/endorse. If your internet goes down and you end up running two baking daemons you could get your security deposit slashed.

My experience with mining Ethereum from before Frontier was that people with massive mining farms, most left over from Bitcoin, could not be bothered to figure out how to run an Ethereum node. They waited until there where farms avaible and then pointed all their GPUs at the farm. I calculated that it cost them between 5%–15% of their returns. The main argument was that they did not like the volatility of not mining consistently. I remember one guy saying: “I have not mined a block in 4hrs! I am pointing at a farm.”

In the case of Tezos running a node is dead simple. If you have a roll you should definitely bake, it’s irrelevant if you miss out on a few bakes because your 10 000tz represents such a small percentage of the total, over a year you are nearly guaranteed to earn the inflation rate of Tezos.

The cost of the node: a machine that is always on; a bit of work to get it setup so that if it restarts it starts the node up automatically; and a decent internet connection with a backup internet connect like 4G. A smallish machine with a big hdd drive like 4T should be fine. Electricity cost should be below 100W.

Now if you have less than a roll you should delegate it to earn a reward till you get to 10 000tz.

Now here is the plug I am running a delegation service, [youloafwebake.io](http://youloafwebake.io/).

Join us at [Telegram](https://t.me/joinchat/HSfKDw3ldwbCVihlzmZR_g).

Check it out it’s had 100% uptime, presently it’s got a 0% fee.
