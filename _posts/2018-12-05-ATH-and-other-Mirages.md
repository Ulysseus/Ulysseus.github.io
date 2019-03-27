# ATH and other Mirages

It’s no secret that crypto prices are set via exchanges. This is a problem because the price is whatever the exchange says it is. [At the moment there is no regulation or oversight](https://blog.goodaudience.com/the-416-million-usd-liquidation-on-chinese-exchange-okex-super-simplified-8ad656af299a), and as a result things like volume are essentially meaningless indicators. The MtGox saga drove the Bitcoin price to $1200 or did it? In my opinion the price was driven to $1200 by MtGox trading with itself on its own exchange. This is referred to as painting the tape. The problems today are much much bigger: as we have multiple exchanges, it’s possible to exploit the different rules on each exchange to manipulate prices. Many exchanges offer leverage which lowers the risk of some manipulation strategies (you need to deposit smaller amounts). Plus you have the threat of double spend attacks. The easiest way to execute a 51% attack, is to send a coin to an exchange, trade it for another coin and withdraw that other coin. Then reorganize the chain of the original coin via a 51% mining attack.

At the time of writing VERTCOIN is being attacked in this way, [link0](https://medium.com/coinmonks/vertcoin-vtc-is-currently-being-51-attacked-53ab633c08a4), [link1](https://bitcoinist.com/vertcoin-vtc-51-attack-100k-double-spend/, [link2](https://cryptobriefing.com/vertcoin-vtc-51-percent-attack/.

Given the crypto winter we are experiencing, I started thinking about how bad is it actually? Everyone measures the price drop by the fall from the all time high ATH.

In the case of BTC the ATH was on 17 December 2017: just shy of $20K; but thing is on 22 December 2017 it hit a low of $10 700. So within a five-day period it hit it almost halved. On 6 February 2018 it hit a low of $6K. The case of Ether is even worse, it peaked on 13 January 2018 at $1440; the low on that day was $1252. On 16 January 2018 three days after the momentary high, the low was $867. The volume on 16 January 2018 was about 4x the volume on 13 January 2018.

The thing is every Ethereum “founder” I have met says that they sold, moreover, they say it was at the high (LOL). It’s interesting that they are only claiming this now. Other than the [Litecoin founder](https://techcrunch.com/2017/12/20/litecoin-charlie-lee-conflict-of-interest/), I haven’t see any articles of people saying they sold everything at $19K. Also notice how the ATH in BTC was almost a month before the ATH in Ether.

The TL:DR take away is: **the ATH is bullshit.** Measuring your trading performance based on some fictitious number, because some exchange published a number is silly at best, or irrational at worst.

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/ethereumprice.png?raw=true" class="inline"/>

I decided to do some simple analysis: taking daily price data on Ethereum and BTC going back 1444 days, I got the data from cryptocompare.com [excellent api.](https://www.cryptocompare.com/coins/list/USD/1)

This data represents about 4 years worth of data.

A histogram of the BTC price changes

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/BTCHistogram.png?raw=true"  class="inline"/>

Daily PCT Change for BTC

The distribution is skewed to the right as you would expect for an appreciating asset. Looking at the number of occurrences versus price is very revealing.

The following histogram shows the number of days BTC price was within a $1000 range
The key take away is: four days between 19K and 20K, two days between 18K and 19K and six days between 17K and 18K. **Or in percentage terms 0.28% near the ATH.**

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/BTCOccurences vs Price.png?raw=true"  class="inline"/>

BTC occurrences versus price

Now let’s increase the granularity of the price further: the following histogram is in price buckets of $100. Notice the big gaps from 18K to the ATH.

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/BTC Occurences vs Price $100 Buckets.png?raw=true"  class="inline"/>

BTC occurrences, price buckets of $100

Let’s assume that you traded everyday and sold a percentage of your bitcoin. What percentage would you have liquidated at the ATH? 0.28%: representing a negligible impact on your trading profitability. If I could sell everything at 20K and then know that today I could buy back at <$4000: sure I would do it, but I bet you would have bought back at $6300 on 6 February 2018 or at $5900 on 12 November 2018. Measuring the ATH from some reported numbers from totally un-transparent exchanges is just bullshit!

[Given that reported volume is total rubbish](https://medium.com/@sylvainartplayribes/chasing-fake-volume-a-crypto-plague-ea1a3c1e0b5e), and that most exchanges allow you to self trade, some claim that they scrub their data for this type of behavior, but it’s pretty easy to just open two accounts at the same exchange, and still wash trade. Exchanges don't care because they still earn the commission.

So let’s look at the data slightly differently…

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/BTC cumulative Distribution.png?raw=true"  class="inline"/>

Cumulative distribution function versus price

You can see from the graph, that the median price is about $2 000; the 95% percentile is $12 500. That is, for 95% of the time, the Bitcoin price is at or below $12 500. So my argument is that this is a much more realistic indicator of the ATH than some ludicrous spoofed price at $19 940 that the media loves to scream about.

The next piece of analysis I did was to weight the price by the percentage of time BTC spent at that price, a kind of proxy for a probability weighted average price. To take into account the effect of bucket sizing I varied the bucket size between $50 to $1000 in steps of $10 and then averaged the results. This gives a probability weighted price of Bitcoin of $4 400.

Markets have to discount uncertainty: something could be worth either $100 or $0 if you price it at $50, you are implying that the probability it goes to $100 is 50% and the chance it hits zero is 50%. This argument will work for all distributions, so we may disagree on the distribution of price changes, but we can still agree on the price, because the probability of the 50% move is the same.

At the moment it’s impossible to value these networks: they are not companies, they have no cash flows, market cap means nothing, PE ratios are meaningless there are no earnings. So am I saying that $4 400 is the correct price of Bitcoin. **I literally have no idea**, if it trades below $4 400 for an extended period of time then my analysis will show that the price is lower than $4 400.

So now for Ethereum…
<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/Ether Histogram.png?raw=true"  class="inline"/>


Ether number of Occurences versus Pct change

A few observations, it’s skewed to the right. Look at the tails, that small bump above 30% it has a value of 2, meaning that twice Ether traded up in excess of 30%!

Now let’s look at the CDF…

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/Ether CDF.png?raw=true"  class="inline"/>

CDF for ETHER versus Price

The median price is at about $100; the 95% percentile is about $900. So in terms of this analysis the ATH was $900.

A more granular histogram of Ether occurrences versus price shows similar gaps to BTC above $1 200.

<img src="https://github.com/Ulysseus/Ulysseus.github.io/blob/master/_images/Ether Occurences vs Price $10 Buckets.png?raw=true"  class="inline"/>

Ether occurences versus price in buckets of $10

Doing a probability weighted price calculation on Ether gives $287.

Take aways: I think most of the crypto exchanges are a blight on the ecosystem. Fortunately market forces are taking care of them; unfortunately they are generating gigabytes of data, that is being used to “show” that crypto is dead.

So in your mind, consider that the ATH in BTC is $12 500; in Ether $900.

Yes, they have crashed massively. The value of a BTC or an Ether is what you can buy in real world goods and services. Comparing it to the dollar is a proxy for that kind of calculation. You could have sold all your Bitcoin and bought Apple^ stock at a 1 Trillion dollar market cap and promptly lost 25%, or you could have sold BTC and bought a lambo^^; you would now have a depreciating asset, that requires fuel and ongoing maintenance.

Bottom line: what we are witnessing is the growth pangs of a nascent market, don't get sucked into all the nonsense going around.

Be careful out there and stay safe!

^I am big Apple fan.

^^I could care less about cars.

