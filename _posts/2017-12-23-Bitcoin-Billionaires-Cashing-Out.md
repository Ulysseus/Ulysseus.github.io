Bitcoin Billionaires Cashing Out?

I just ran the numbers and my crypto portfolio had a 45% swing in value over the last day. Its only down 18% from the highs now.

An interesting trade was done by [Block Tower Capital](https://www.bloomberg.com/view/articles/2017-12-21/bitcoin-billionaires-may-have-found-a-way-to-cash-out). Basically they bought an option on Bitcoin for $1m; the option gives the right to buy 275 BTC at $50 000 each in one year’s time. The trade is fully collateralized by the 275 BTC.

It’s an interesting trade for a few reasons, firstly it took place on [LedgerX](https://ledgerx.com/) , this is an exchange for very high networth indivuals > $10m or institutions. It’s a pity its only US based at the moment. [(be U.S.-based and U.S.-banked)](https://ledgerx.com/trade-on-ledgerx/

A trade like this is called a covered call, basically the seller of the call option owns the underlying asset in this case BTC. In reality the seller of a covered call has sold a put option on BTC. That is, the seller is betting that BTC will be below $50 000 in one year’s time.

The trade is interesting because for large holders of BTC, 275 coins is a pretty big amount and they will have trouble monetizing it. In the long term it almost certainly will have been a mistake to have sold (BTC will go higher than $50 000), but consider it from their perspective. It would be nice to spend some of it now. If you bought at a round $1 and BTC is at $14 000, that is a massive gain, but there is not much you can buy directly with BTC (expect that to change). So what are your options? Centralized exchanges, where you can trade your BTC for fiat, but the last few days, [have shown us](https://www.cnbc.com/2017/12/22/coinbase-one-of-the-biggest-bitcoin-marketplaces-says-buying-and-selling-temporarily-disabled-amid-price-rout.html), just how woefully under resourced the exchanges are. The only one I can recommend is [BitMex](https://www.bitmex.com/register/ZgfHjW) and that is a futures only, profit into BTC exchange.

All others, I have accounts at any that would have me, it either take ages to verify you, or they have continual timeouts. The other problem is that trading 275 BTC would take literally ages, the order books are just not that deep. So what is a poor whale to do? Well, sell a put option, the whale gets an immediate $1m to go spend. If in one year’s time BTC is below $50 000, no harm no foul: the whale still has his 275 BTC. If in one year’s time it’s above $50 000 the whale is forced to sell for $50 000 a coin. The whale’s total selling price is $53 636 per coin. So the whale is basically saying, you know what I am gonna hold these coins but if the price gets to $50 000 I will sell. If it doesn't I am happy to keep HODL. It’s a great trade.

Now let’s delve a bit more into the pricing, options have value largely because of the time they are valid for: the longer, the more value and the volatility of the asset they are written on, the more volatile the more valuable.

I will use Black Scholes because everyone has heard of it, although I think it’s completely inappropriate for such a volatile asset as BTC. I will also use an infinite variance model to price it.

I am going to assume interest rates of zero and a dividend yield of zero. If there are hard forks in the next year, pretty sure the seller will get the benefit of them. Strike $50 000, time to expiration exactly 365 days. A slight wrinkle: options come in two varieties European and American. European is only exercisable at expiration, American at any time up to expiration. American are always worth more than European. I am assuming this option is European, so only exercisable at expiration

Here it gets very interesting, here are the Black Scholes prices, unfortunately Medium won’t let me do a Table, the deal was done at $1 000 000/275 per BTC or $3 636.36 per BTC
```
Spot->10 000 Volatility->50% Price->$1.87
Spot->15 000 Volatility->50% Price->$35.44
Spot->18 000 Volatility->50% Price->$110.56
Spot->50 000 Volatility->50% Price->$9 870
Spot->10 000 Volatility->100% Price->$463.54
Spot->18 000 Volatility->100% Price->$2 214.81
Spot->50 000 Volatility->100% Price->$19 146
```
So if Spot was $18 000 the implied volatility of the trade was in excess of 100%.

Now let’s use a more realistic model: this is an option pricing model I like to use it assumes infinite Kurtosis. Simply put infinite Kurtosis assumes that the error in your measurement of volatility is infinite, that is you literally have no idea what the volatility will be.
```
Spot->10 000 Volatility->50% Price->$14.59
Spot->15 000 Volatility->50% Price->$62.69
Spot->18 000 Volatility->50% Price->$126.12
Spot->50 000 Volatility->50% Price->$9 652.86
Spot->10 000 Volatility->100% Price->$112.23
Spot->18 000 Volatility->100% Price->$851.12
Spot->50 000 Volatility->100% Price->$19 305.7
```
The implied volatility of the deal is in excess of 175%.

The results are very interesting: it looks like the option was hugely overvalued, the seller seems to have done a very good deal. I must admit I was surprised by this, but one thing trading for over twenty years has taught me is, some people have developed a keen intuition for profit. The early adopters of Bitcoin were not just some lucky bosons, they saw a massively mispriced opportunity and they hit it and they hit it hard. Now the cards have turned in their favour they will make you pay and pay heavily, don't expect them to give up their position easily.

All this tells me Bitcoin is not a bubble, the HODL of Bitcoin and other cryptos are the new masters of the universe. We are watching a quiet revolution, the establishment has shown its hand with negative interest rates, bail outs and bail ins. They have no solutions, they are about to be owned, don't be on the wrong side of history. This is nothing short of a revolution. HODL at least a small position in crypto.

“ No one would have believed, in the last years of the 19th century, that human affairs were being watched from the timeless worlds of space. No one could have dreamed that we were being scrutinized as someone with a microscope studies creatures that swarm and multiply in a drop of water. Few men even considered the possibility of life on other planets. And yet, across the gulf of space, minds immeasurably superior to ours regarded this Earth with envious eyes, and slowly, and surely, they drew their plans against us…”

~ [**H. G. Wells**](http://uncyclopedia.wikia.com/wiki/H._G._Wells) **on The War of the Worlds**

[Previous to the commencement (tactically speaking) of the battle of Austerlitz, the allies attempted a flank march in column to turn the right flank of Napoleon. He restrained his marshals, who were eager to attack, saying, “the enemy is making a false move, why should we interrupt him?](https://books.google.im/books?id=LFgBAAAAQAAJ&q=false&redir_esc=y&hl=en#v=snippet&q=false%20move&f=false)

