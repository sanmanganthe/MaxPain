#### Algorithm Overview
1. Get historical options data (underlying, expiration, strikes, open interest) for all tickers in SP500, and underlying data
2. Clean Bloomberg data 
3. Compute cumulative open interest sum for OTM call options at each strike 
4. Compute cumulative open interest sum for OTM put options at each strike 
5. Find strike with maximum cumulative options OTM. Log target in window.
6. Create CI for n-day window as price target range
    + Window width 
    + CI MOE
7. Trade
    + If underlying trades below lower bound, BUY 
    + If underlying trades above upper bound, SELL/SHORT
    + If underlying trades within bounds 
        + Do nothing if not holding
        + SELL if holding 

#### Remaining Work:
+ Decide action upon approaching expiration while holding
+ Scrape options data from Bloomberg
+ Reduce data pull to a tractable set 
+ Write test cases for helper functions in backtest.py