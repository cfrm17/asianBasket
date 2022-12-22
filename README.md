# Asian Basket Options with Individually Capped Returns

A model is presented for pricing Asian basket options with individually capped returns. Crude Monte Carlo method is employed to value the derivatives. Each asset return is capped with a rate.  Volatility smile is utilized in the calculation.

Let   be a price process of a given underlying asset i, and suppose we have a basket of n assets.  Let   be a set of reset dates and   be a payoff settlement date.  The price of each asset is recorded on the set of reset dates to obtain the price arithmetic average of  .  The payoff of this European type call option at the settlement date is given by

	 

where N is the notional principal,   is the weight of asset i in the basket,   is the strike for asset i, and   is the cap on return for asset i.

Let t be the current value date, then the current value of this derivative security can be written as

	 

where   is the discount factor at the value date.  The above formulae are in a world that is forward risk-neutral with respect to a specific currency  .  If an underlying asset i is measured in another currency  , the governing price dynamics of this underlying asset in the risk-neutral world of   should be written as

	    

where   is the short rate of  ,   is the dividend yield of the asset,   is the correlation coefficient between the asset price and the cross-currency exchange rate,   is the volatility of the asset price,   is the volatility of the exchange price, and   is the Wiener process.  Asset prices in the basket are correlated with   where  ’s are constant correlation coefficients between the logarithmic asset prices.  All these parameters are assumed deterministic.

To compute this expectation we use a Monte Carlo approach. First we will describe the multi-asset path generation. Let Wi(t) be a 1-dimensional Brownian motion under currency Ci risk-neutral world, for all i = 2, ..., n. Let (WC1 (t), ...,WCn (t)) be a n-dimensional Brownian motion under currency C risk-neutral world having (instantaneous) correlation matrix (_ij)i,j=1,...,n, that is:

 

We have, for each i = 2, ..., n:

 

Repeating this procedure for all k = 1, ..., p (new standard Gaussian random vector for each date, but the same seed), we produce the averages Ai, i = 1, ..., n necessary in the payoff.

We compute the payoff M times and then take the average. If M is large enough, then these average approaches the expectation we are looking for (an application of the Strong Law of Large Numbers). Alongside we also compute the statistical standard error. Note that if the valuation date is later than an averaging date, then on that date the realized price must be used in the computation of the payoffs. The sensitivities are computed using finite differencing with path recycling. For example, delta is computed using:

 

References:
https://finpricing.com/lib/IrBasisCurve.html


