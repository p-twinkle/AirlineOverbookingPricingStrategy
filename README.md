# Airline Overbooking Optimization using Dynamic Programming

This project applies dynamic programming and forward simulation to optimize airline overbooking and pricing strategies. The goal is to maximize expected discounted profit while managing customer disruptions and operational constraints.

## Overview

We model an airline’s ticket sales over a 365-day period, allowing decisions on coach and first-class pricing. The model incorporates:
- Probabilistic ticket demand and show-ups
- Overbooking penalties (bump to first class or deny boarding)
- Seasonal variation in demand
- A no-sale option for coach tickets

Dynamic programming is used to find optimal daily pricing strategies, and forward simulation evaluates real-world performance.

## Methods

- **Dynamic Programming (DP):** Computes optimal pricing decisions based on current day, tickets sold, and availability.
- **Forward Simulation:** Tests DP policies under uncertainty in sales and attendance.
- **Seasonality:** Adjusts demand probabilities to reflect increasing booking rates closer to departure.

## Results Summary

| Metric                           | Naive       | OB - 5     | OB - 9     | No Sale    | Seasonality |
|----------------------------------|-------------|------------|------------|------------|--------------|
| Expected Profit                  | $37,346.34  | $38,148.03 | $38,381.68 | $41,759.37 | **$41,833.27** |
| Profit Volatility                | $905.69     | $527.83    | $833.59    | $937.98    | $932.13       |
| % Overbooked                     | 100.00%     | 39.27%     | 90.26%     | 87.43%     | 82.34%        |
| % Passengers Kicked Off          | 100.00%     | 28.54%     | 80.85%     | 79.26%     | 70.99%        |
| Avg Overbooking Cost             | $4,809.66   | $194.28    | $1,051.71  | $1,020.36  | $852.63       |
| Avg Coach Tickets Sold           | 120.00      | 105.00     | 109.00     | 108.78     | 108.34        |
| Avg First-Class Tickets Sold     | 19.94       | 19.87      | 19.67      | 19.75      | 19.55         |

## Recommendation

The Seasonality DP Policy is the most effective overall. It delivers the highest expected profit, reduces overbooking risk significantly, and reflects real-world booking behavior. This policy is recommended for implementation due to its balance of revenue optimization and customer satisfaction.

## Structure

```
.
├── FinalCode/     # Jupyter notebooks
├── report/       # Final report and results
└── README.md
```

## Authors

Biagio Alessandrello, Jenna Ferguson, Kimble Horsak, Twinkle Panda
