# Paris_Hackhaton

Project Computational data feeds (extending the oracle & feeds)

Alternative aggregation:

A TWAP feed: Use keepers to regularly ping the oracle to get the most recent price and add that to the running sum: https://en.wikipedia.org/wiki/Time-weighted_average_price#:~:text=TWAP orders are a strategy,second half of the day or https://docs.uniswap.org/protocol/V2/concepts/core-concepts/oracles

Exponential decay weighting: Take all the most recent reports and instead of taking the median, weight the most recent submissions more heavily than older submissions

Empiric Network goes beyond price feeds. Advanced computational fields are needed, similarly to what Traditional Finance already has. Thanks to Empiric, these computational fields can be built in a secure and verifiable manner.

Our project for this hackhaton is centered on providing TWAP feed. TWAP is a pricing methodology that calculates the mean price of an asset during a specified period of time. For example, a “one-day TWAP” means taking the average price over a defined day of time. 

One of the most known protocols using TWAP is Uniswap. A common TWAP implementation used in Uniswap involves taking two snapshots at different points in time, tracking both the timestamp and historical sum of prices for each, and using this information to calculate a final TWAP data point.

In our project, we define an array of arbitrary size and then compute the TWAP metric. We also provide the Exponential decay weighting: We allocate weights to price measurements depending on time (older submissions are less weighted than newer ones) and then compute accordingly the TWAP.

The array we defined with prices and timestamps also allow us to derive sentiments (bullish, bearish). In an array of size 60, if the 10 last values are decreasing, then we consider that we are in a bearish phase. On the other hand, having 10 increasing values mean we are bullish.

Last but not least, we compute the volatility based on the array we have.

