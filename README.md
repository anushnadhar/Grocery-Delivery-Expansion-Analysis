# Grocery Delivery Expansion Analysis (1Q2025)

## 📌 Project Overview

This project simulates a business decision-making data challenge similar to the Capital One Data Challenge, focused on expanding a grocery delivery company’s operations across the United States.

The objective is to identify the most attractive delivery loops (Fulfillment Center ↔ Delivery Zone round trips) to launch first, balancing profitability, demand, and on-time performance, while considering realistic operational costs.

The analysis uses 1Q2025 data and applies Python-based data analysis to recommend five delivery loops worth investing in.

## 🏢 Business Context

The company plans to expand by launching 5 new delivery loops, each operated by a dedicated delivery van.
* Upfront cost per van: $120,000
* Company motto: “Fast, fresh, reliable”
* Success depends not only on profit, but also on reliability and utilization

Each delivery loop is defined as a round trip between:
* A Fulfillment Center (FC) and
* A Delivery Zone (Z)
(Direction does not matter FC03–Z12 is the same as Z12–FC03.)

## 📊 Datasets Used
1. Deliveries Dataset (Deliveries_1Q2025.csv)
  * One row per delivery leg
  * Used for:
      * Distance traveled
      * Delays and on-time performance
      * Cancellations

2. Orders Dataset (Orders_Sample_1Q2025.csv)
* One row per completed round trip
* Used for:
  * Revenue
  * Capacity utilization
  * Sample dataset (mirrors real-world data constraints)

3. Location Codes Dataset (Location_Codes.csv)
* Identifies each Fulfillment Center and Delivery Zone as:
    Medium or Large
* Only medium and large locations are considered

## ⚙️ Cost & Revenue Assumptions
### Costs

* Operating cost: $1.20 per mile
* Location handling fee (Charge location handling fee only at the Delivery Zone, No fee charged at Fulfillment Centers):
  * Medium: $50
  * Large: $80
* Delay cost (outbound only):
  * First 10 minutes free
  * $2 per additional minute
* Cancelled deliveries incur no delay cost

### Revenue

* Revenue per round trip is taken directly from the Orders dataset
* No recalculation of delivery fees or service charges

## 🧠 Analysis Approach

1. Data Cleaning & Preparation
 * Filtered 1Q2025 data
 * Removed cancelled deliveries where required
 * Created standardized delivery loop identifiers

2. Demand Analysis
 * Identified busiest delivery loops by number of completed round trips

3. Profitability Analysis
 * Calculated total revenue and operational costs per loop
 * Derived profit and profit per round trip

4. Scoring & Recommendation
 * Normalized key metrics to a 0–1 scale
 * Applied a weighted scoring model using:
 * Profit per round trip
 * On-time performance
 * Utilization rate

5. Break-Even Analysis
 * Estimated number of round trips required to recover the upfront van investment

## ❓ Business Questions Answered

1. What are the 10 busiest delivery loops in 1Q2025?
2. Which delivery loops are the most profitable (excluding upfront costs)?
3. Which 5 delivery loops should the company launch first and why?
4. How many round trips are needed to break even on the $120,000 van investment?
5. What KPIs should be tracked post-launch to measure success?
