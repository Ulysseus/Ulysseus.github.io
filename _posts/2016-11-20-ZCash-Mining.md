ZCash Mining

ZCash officially launched on the 28 October: trading was weird to say the least.

State of mining right now? It’s still profitable. So as of now the best option is to buy a AsRock BTC Pro 2 Mobo, six risers and six AMD RX 480 GPUs. Then load Ubuntu 16.04 and the latest drivers from AMD. Install <a href="https://github.com/Optiminer/OptiminerZcash">Optiminer</a> and also keep an eye on <a href="https://github.com/mbevand/silentarmy">SilentArmy</a>. You should be able to get away with one big PSU say 1300W: I suggest you get a Platinum efficiency one. Also, the Mobo has one or two molex connectors: connect them. You should get about 800 sol/s. Of course everyone’s cost of electricity is different. You can try and mine solo, but unfortunately the difficulty is so high, you have to mine to a farm. I use <a href="https://zcash.flypool.org/">flypool.org</a>. But there are others, just check the Zcash forum.

Having given an idea how easy it is to start mining, its really no suprise that the price of ZEC has dropped so significantly. In my experience it’s generally better to just buy the coin instead of spending the money on equipment. So the question is this: what’s the long term prognosis for ZEC?

Firstly, who knows: how long is a piece of string?

Secondly at $64 it’s looking cheap. Here are my concerns: Are z_addresses going to work properly? And, when will I log into flypool.org and not see the big red banner saying “Because of another bug in Zcash version 1.0.2 we are still unable to send transactions to z addresses! Therefore DO NOT use z addresses to mine on the pool for now.”

Ok, so I am not too worried. This is precisely what Zcash was invented for, so I must assume they will get it right.

My main worry is mining, at the time of writing, the top miner was “anonymous” at this pool <a href="https://www2.coinmine.pl/zec/index.php?page=statistics&action=pool">link</a>, with over 10% of the entire network hash rate. Now that’s just weird: if you have 10% of the entire network why mine to a farm? This person’s sol rate fluctuates widely from 2m sol/s down to 1m sol/s. In my view it’s a botnet. So because a botnet does not pay for equipment or electricity, whatever they mine is free money. At the moment that’s about $20K a day.

My next concern as regards mining is the PoW algorithm, it’s called <a href="https://www.internetsociety.org/sites/default/files/blogs-media/equihash-asymmetric-proof-of-work-based-generalized-birthday-problem.pdf">equihash</a>. Basically the idea is to create an asymmetric memory hard non-parallelizable PoW. This is to discourage ASICs. Unfortunately the algorithm is not sequential, so it is parallelizable. Hence the dramatic increases in the sol/s of the network as new mining software is released with significant optimizations for GPUs. So far so good, the faster GPUs become, the less of a threat botnets present.

My concern comes from the design of the algorithm. To work, the authors introduce algorithm binding. This is extremely important, because they are forcing miners to solve the problem in one particular way. In this case, something called Wagner’s algorithm. This means it’s much harder to recast the problem in another way, that may be easier to solve. The algorithm binding is one of the tests a successful solution needs to have. In my opinion this is a weakness.

Then I read this by <a href="http://www.openwall.com/articles/Zcash-Equihash-Analysis#bandwidth">Solar Designer</a>, “Equihash solution verification
As I have mentioned above, it is important to enforce Equihash’s algorithm binding constraint. It is even more important to validate solutions in other aspects, including for lack of duplicate indices.

In Zcash source tree, all of this appears to be enforced in  <a href="https://github.com/zcash/zcash/blob/996fccf267eedbd512619acc45e6d3c1aeabf3ab/src/crypto/equihash.cpp#L738">
zcash/src/crypto/equihash.cpp: IsValidSolution()</a>, but I have not audited it thoroughly. With the abstraction layers in place, I wouldn’t be confident of its correct rejection of subtly invalid solutions without having stress-tested it on many inputs falling into the different categories. There are a few<a href="https://github.com/zcash/zcash/blob/996fccf267eedbd512619acc45e6d3c1aeabf3ab/src/test/equihash_tests.cpp#L151">test vectors</a> for lack of algorithm binding and duplicate indices, but they cover some easy to generate special cases only and <a href="https://github.com/zcash/zcash/issues/1825">should be improved</a>.

Another concern is third-party Zcash software. Unfortunately, lack of or buggy verification of the algorithm binding constraint is likely to go unnoticed until such solutions are attempted to be submitted to the network. When that happens, the network may go out of sync, effectively having a fork of Zcash that already includes some and allows future non-algorithm-bound, amortization friendly solutions. It’s similar for potential lack of or bugs in the duplicate indices check, although the effect on properties of such inadvertent Zcash fork would be different and, for complete lack of the check, so devastating that no one sane would want to continue with it.”

So it may be that people are running mining software that is generating solutions that are not completely satisfying the algoritm binding condition. That would give them a huge advantage in the mining space.

So my conclusion is as follows: Don’t buy mining hardware unless you plan to use it for something else. It’s probably not time to buy ZEC now, I plan to wait till the end of slow start and until the mining and z-addresses issues are clearer.

