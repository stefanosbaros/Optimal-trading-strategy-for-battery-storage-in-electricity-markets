# Optimal-trading-strategy-for-battery-storage-in-electricity-markets

Model predictive Control Approach to Computing Battery Bids and Offers
We assume that at time t we have forecasts (features) for the next look-ahead period. In the analysis, I considered look-ahead periods ranging from 12 to 120 hours. Using the price forecasters, I predict energy prices for the look-ahead period in all three grid nodes. Then, the bidding strategy is as follows:

For each node, I solve a look-ahead optimization problem for the look-ahead period, using the forecasted prices and incorporate all constraints associated with the battery storage devices and come up with Psd and Psc, the discharging and charging commands for each hour of the look-ahead horizon corresponding to that node.
Then our order for t+1 will be the commands for the first hour that correspond to the node with maximum profit over the look-ahead horizon specifically to sell Psd[0] (if Psd[0]>0) or buy if Psc[0] (if Psc[0]>0) i.e., our bid will be the output of the optimization problem for hour 1 of the look-ahead horizon of the most profitable grid node and will be to sell if the discharge variable is greater than zero or to buy if the charge variable is greater than zero.
At t+1, we repeat this process.
