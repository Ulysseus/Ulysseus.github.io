Tesos delegation: Now you can have your cake and eat it!!

We launched our delegation service, You loaf / We bake ([youlofwebake.io](http://youlofwebake.io/)) about two weeks ago and along the way our delegators have learnt quite a few lessons — main one being that delegating your tezzies let’s you have your cake and eat it.

But, don’t get too greedy — the returns won’t be in the stratosphere. It also it takes some time being delegated to a service before you to start earning those rewards. Firstly you have to be at the “snapshot date” (roll over between cycles) to be eligible for your share of the returns, and secondly, the rewards take another five cycles to be released and only then can we pay them to our delegators.

**First off, why did we start our delegation service?**

We realised this would not be a huge money spinner for us. We believe Tezos is an exciting new token, and that despite all the shenanigans of the last year, the token holds a lot of promise. Our aim was to support the ecosystem in gaining critical mass. As an aside, when I started mining ethereum back in [2015] is was with the same philosophy. I thought that I would make a 5% return if I was lucky. Of course I am charging a 0% fee on the baking at the moment so bit pointless for me from a cash generation perspective, but I want this ecosystem to grow. We also need to stake our own Tz (staking bond) in order to accept delegates, which locks up our Tz.

A few of the questions we’ve had and our responses:

**How does the baking work?**

The protocol takes 16 snapshots per cycle of 4 096 blocks, so that’s about 2d and 20hrs. The right to publish a block in cycle number “n” is assigned to a roll that is randomly selected from one of the 16 snapshots taken in cycle n-7 that is from 7 cycles ago — or about 21 days. We get 16 Tz plus all of the fees for baking a block.

For each block that can be baked 32 endorsers are also selected from the roll snapshot. The endorsement reward is 2 Tz but it halves if the if the person baking the block is not there to bake it. So sometimes we will get 1 Tz for endorsing rather than 2. We can be selected multiple times to endorse a block.

**How can I see online whether my Tz have arrived?**

[tzscan.io](http://tzscan.io/) on the [link:http://tzscan.io/tz1eZwq8b5cvE2bPKokatLkVMzkxz24z3Don?default=delegation](http://tzscan.io/tz1eZwq8b5cvE2bPKokatLkVMzkxz24z3Don?default=delegation)

You can also email us on [bakerinchief@youloafwebake.io](bakerinchief@youloafwebake.io) and we will check online for you.

**How much is YL:WB going to make for the delegation service?**

It’s not a big money spinner, but does generate a basic return on your Tz. For every 10 000 Tz staked, YL:WB has the right to accept ±120 000 Tz in delegations. Say we charge 10% fee (we have committed to no fee until the end of Cycle 25), we earn 10% of the reward. Tezos is designed so that rewards on baking are 5.5% per annum. On this basis, we would earn 10% of 5.5% of 120 000 Tz or 0.5% of 120 000 Tz per year. This is 600 Tz per year or 50 Tz per month.

Our risk is the 512 Tz bond if which we lose if we double bake, of the 10 000 Tz if we’re hacked. You don’t hand over any private keys so you don’t run the risk your Tz being hacked on our service. We’re incurring website hosting, equipment costs as well as electricity costs, not to mention our time which we’re investing in the Tezos ecosystem. We see this as our investment in getting the project started and ensuring it stays decentralised.

Where delegation is going to get interesting is when we need to vote on protocol changes!

**Will we be baking right away or do you need more folks to get started?**

We take your Tz straight away, but in order for them to start baking rewards, they need to snapshot at the next cycle roll over, which at date of publishing will at the end of Cycle 20. We will also know what we’re going to get at this point, but it will take 7 cycles to bake.

We have justreached the cycles where people have delegated, so on tzscan, where it shows two delegates in the cycles they are both mine. In the “bakings section, [(http://tzscan.io/tz1eZwq8b5cvE2bPKokatLkVMzkxz24z3Don?default=baking)](http://tzscan.io/tz1eZwq8b5cvE2bPKokatLkVMzkxz24z3Don?default=baking), you will notice that there’s a big jump in cycle 19 which correlates to 7 cycles after we launched our delegation service.

**What is your mechanism for paying out rewards?**

Initially we will payout manually but later we are planning to use tzscan’s API to do it automatically, but only once we’re sure it’s working correctly. So, initially we will pay them monthly, but once we am sure it’s working correctly it will be paid out once the lockup is over.

**What is your baking success rate?**

Success rate is 66% at the moment.Its missleading because we have only had a chance to bake 3 blocks and we missed one. We had a bake in Cycle 17 that we missed because of a faulty plug. You can see your projected rewards on tzscan.io, so you’ll be able to check that I have paid out the right rewards to you.

How quickly will you let clients know that you are over-delegated

If you check [http://mytezosbaker.com](http://mytezosbaker.com/) it gives stats on over delegation. It’s an issue at the moment because it’s being calculated wrong. The issue of course is we can only communicate via telegram or twitter etc, we can’t exactly send out an email so it’s wise to check online yourselves.

**So how much do you need before you are over-delegated?**

The amount I can take in delegations is linked to my bond i.e. the bond of Tz gives me capacity to take on delegations. That bond needs to be at least 8.25% of all Tz delegated to me. So say I have one roll of 1 0000 Tz, I can get delegations of (1/.0825)*10 000 =121212.1212 or about 120 000 Tz.

I have about 24 000 Tz so that’s a capacity of (1/.0825)*24 000 =±288 000, or just under 29 rolls. And this excludes what I have made so far — as I earn Tz, I can increase my bond and take on more delegations.

**How do you plan to scale your bond**

We keep the bond in another account controlled by a ledger nano s. If the bond becomes too small we move Tz to the baking account within at least 12hrs. If someone delegates to YL:WB, and we don’t have enough bond to cover it, it should take no longer than 12hrs for us to notice. We will, in due course make it programmatic so it will be instant.

We can also scale our bond by reinvesting of tezzies earned via baking/endorsing. When reasonable exchanges start listing Tz we will buy them. Currently, only Gatecoin lists them.

**Where are we now?**

We’re are in Cycle 19: cycle 13 rewards were released basically at the end of cycle 18, or a five-cycle lag. Our first delegators start earning rewards in Cycle 18, payable in Cycle 23.

We hade our first block to bake in Cycle 15 which will be an interesting test as we’ve only had endorsements to date. We missed the block in cycle 17 faulty plug meant the machine never switched back on.

We have 11 delegators in Cycle 19; minus 3 which are YL:WB. That’s 8 real delegations. We successfully baked the block in Cycle 19. Rewards payable in cycle 24. In Cycle 19 we will earn 16 Tz from baking and a whopping 94 Tz from endorsements.

One thing: If we have a priority of 1 in baking then we may get a steal and get an extra 16 Tz if some stuffs up their baking and we endorse on that block we only get 1 Tz instead of 2 Tz. This seems silly to me but that’s the way the protocol works and this means that until the end of the cycle the rewards could vary from what we have stated.

