The P2P revolution.

I am not an expert on Bitcoin so take what follows with a pinch of salt.

When I was child I remember my father turning a cheque over and signing on the back. When I queried this, he explained that the cheque was a payment from someone else and he was signing it over to another third party.

Of course for someone to actually get paid, they would have to physically present the cheque to the issuing bank who would then debit the drawer’s account. (An aside: The difference between a savings/deposit account and a current account is that a current account is a chequeing transactional account and generally paid no interest). Of course the bank had to have a way to verify the cheque and to check that the account owner had actually signed.

With the advent of the internet, we have a communication system that allows anyone, anywhere in the world to communicate with any other person anywhere else in the world. It is futile to try and use such a system to connect centralised entities like banks together. They should be using secure dedicated non-public networks. What they are doing is trying to cannibilise a public resource, the Internet, so that they can lower their costs. This won't work, because it’s insecure. The Internet was not designed to be secure! Think about it: They have no certain way of knowing if they have been hacked and the attack surface is enormous: Employees sticking USB drives into computers; email phishing; security cams; insecure Wifi and bluetooth, to mention but a few. In case you think “air gapped” is a solution, it’s even possible to hack a computer by listening to the CPU fan, not to mention insecure ISPs. A last question: When did you last check your routers firmware or make sure your firewall was on? Even formatting your hard drive doesn’t mean you will not immediately be reinfected from the router or ISP. Security is so bad they are not even sure if they have been hacked. Its not like coming home and seeing you have been burglered. Hacking, if done right, is the perfect crime, as no-one knows it was done!

Then along comes Bitcoin. Basically it’s just like a checking system. You own 10 BTC to pay someone: To sign them over, you literally cryptographically sign “I have access to these 10 BTC and I am assiging them to the person whose signature is represented by this public address”. Now what’s to stop you signing them over to a hundred other peole and letting them fight it out, without a central authority to verify anything. The problem is solved with Proof of Work (“PoW”) mining in Bitcoin. PoW was developed to prevent spam email, the idea being that before you send an email you solve a hard maths puzzle, one we know can only be done by brute force. This takes say 3 seconds, and you the send the solution together with the email. Now, and this is the important bit, the puzzle is easily verified as being solved, so takes microseconds to verify. If the email does not contain a valid solution the recipient just deletes it. So consider from the spammer’s point of view: They want to send 100m emails, that’s 300m seconds or 3472 days or over ten years!

Bitcoin uses the same idea. All signed transactions are broadcast to the Bitcoin network and are put in a pool. A bunch of special nodes, called miners, choose from this pool to build a block. They then solve a hard mathematical puzzle that is directly dependent on the transactions they have selected. As soon as one of them succeeds; and this extremely important: the miner that finds a solution is random; they shout “Bingo I got it to the network” at the moment they find it. The other nodes verify that the miner has a valid solution and add that block to the chain of previous found blocks. Each block depends on the previous blocks, so if anyone wants to counterfeit a transaction they have to create an entirely new ficticious blockchain (easy to do). Here’s the rub: They must also recreate all the maths solutions for each block. Remember, as the chain gets longer, it gets harder and harder for the email spammer to do this.

Why is this useful? Because it prevents double spend. There is nothing stopping someone from signing two transactions, saying pay A and then pay B the same 10 BTC. But, once one transaction is included in a block, the miner creating a new block with the double spend will reject the second double transaction as invalid, because the Bitcoin at that address have already been spent. This also tells you why you should not reuse BTC addresses. They are not bank account numbers, rather they are like the serial number on a bank note. By always using new addresses you create pseudo anonymity.

Yesterday, my favourite new project Zcash (“ZEC”), launched successfully. I have already mined a tiny amount. Price per ZEC =$10 000. This seems ridiculous to me. In total something like 100 ZEC will be mined over the 24 hrs from launch, then the amount mined will go up steadily over the next 34 days. So don’t buy! I think its unreasonable to pay anything above 1 BTC per ZEC. Think about it: Bitcoin is battle tested, ZEC is not. Yes, ZEC has greater utility because its truly private, but we need to be sure there are no problems. On that front i’ts the first true privacy enhancing non-permissioned public blockchain: A truly impressive achievement.

I am very excited for the future, the Internet is finally starting to deliver on its promise of a free world, a world free from coercion.

Privacy is a fundamental human right, people cannot express themselves morally and ethically without privacy.
