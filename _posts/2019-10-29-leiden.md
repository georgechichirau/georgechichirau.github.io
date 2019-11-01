---
layout: post
title: Project Leiden - impulse trading on a random day
published: true
tags: trading earnings
---
I've been meaning for a while to develop an earnings-based trading plan (= Project Leiden), but I haven't had time to figure out a way to backtest it. I wish I had access to [institutional tools](http://solutions.refinitiv.com/qa-point-quantitative-investment-management/), but I don't, and backtesting in thinkorswim was thought out for different things. (I'm also beginning to think the TOS interface is considerably different on Mac vs Windows - and not in a good way.)

If I'll never get to actually backtest, at least I can get data points by trading live. This morning I see this e-mail from Market Chameleon and I decide to go ahead and buy iron butterflies on whichever of these are both overestimated and liquid enough. AR overestimated by almost 20%? Let's see how much it will move.

<p class="full-width">
<img src="/public/image/2019102901.png" width="80%" align="center"/>
</p>

I managed to place trades on 8 of these; total max profit $3600, max loss $2100 (at expiration). I'm offloading them all tomorrow though.

**Update 2 days later (2019/10/31)**

I bought another 6 yesterday, and now I have a small farm of 14 iron butterflies:

<p class="full-width">
<img src="/public/image/2019103101.png" width="80%" align="center"/>
</p>

As you can see, it's pretty much even. Two things are bothering me right now (and I don't really know how to figure them out).

One: if I were to do these trades on a real portfolio, what liquidity threshold would I use? I suspect a good number of my butterfly positions are not liquid enough, and I'd run into trouble if I were to try and adjust them.

Two: if I'm even 1-2 days in, what would happen, generally, if I let the positions run closer to expiration? Looking at the risk profile for long iron butterflies in the [Holy Scriptures](https://www.amazon.com/Bible-Options-Strategies-Definitive-Practical/dp/0133964027/), it would seem that both volatility and time decay are helpful/unhelpful according to whether the stock is in the money/out of the money. But are they *equally* so? Is volatility hitting positions equally at delta +30 or -30, 15 days out or 5 days out?

<p class="full-width">
<img src="/public/image/2019103102.png" width="100%" align="center"/>
</p>

_Option Greek variation for Long Iron Butterflies_

Of course not. There's an interesting (and separate) relationship between delta and theta and between delta and vega for each stock in the butterfly farm. Which means I'd need to figure out how to compute [second order options greeks](https://medium.com/hypervolatility/options-greeks-vanna-charm-vomma-dvegadtime-77d35c4db85c) for the portfolio. Not just compute, but figure out how to use them productively, as well.

I [understand the theory](http://www.volcube.com/resources/options-articles/the-hidden-uses-of-vanna/) when I spend some time on it, but the greater challenge is how to implement it on a butterfly farm without institutional tools. I'll try to see how much I can get done in thinkorswim.
