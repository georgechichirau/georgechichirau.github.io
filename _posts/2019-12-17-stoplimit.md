---
layout: post
title: The issue with stop limit orders on option spreads
published: true
tags: trading options
---
I have a very silly problem related to the huge volatility of option premium on open.

For the third time in two days, I've had option spreads bought back at 9:31 AM because my stop limit was reached. When you place a stop loss order, the broker fills it at that price *or better*. No problem, right, if it gets a price that's better for you?

Well, it is an issue. Look at the example below. I sold a put spread at .35 on 12/10, and also placed a stop loss order at 1.12; the limit got triggered at market open and my spread was bought back at... .55. Nowhere near 1.12. My spread was near the defined danger zone for just a few seconds, but got bought back anyway.  

<p class="full-width">
href="https://www.georgechichirau.com/public/image/2019121701.png"> src="/public/image/2019121701.png" width="100%" align="center"/>
</p>

This happens more often than you'd think. I don't see what I can do about it, since I can't place any orders on thinkorswim apart from limit, stop and stoplimit. I suppose the only way to fix this would be to move to algorithmic trading and write an exception ("don't execute orders between 9:30 - 9:35 AM").  
