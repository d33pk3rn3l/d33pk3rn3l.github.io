---
layout: post
title: "Swiss Public Transport Cost Calculator"
date: 2025-05-06 15:45:19
category: posts
---

## The Problem: Navigating Switzerland's Complex Subscription Options

Switzerland has one of the world's most extensive and efficient public transportation systems. However, this comes with a bewildering array of subscription options ("Abonnemente") that can make choosing the right travel card surprisingly difficult.

As a frequent traveler within Switzerland, I faced this challenge myself:

- Should I purchase the expensive GA (General Abonnement) that covers all public transport in Switzerland?
- Is the Half-Fare card combined with individual tickets more economical?
- Would a regional travel card like ZVV (for the Zurich area) combined with occasional long-distance tickets be the optimal solution?

The answer depends entirely on your personal travel patterns, but calculating this manually is tedious and error-prone. Different travel cards include different zones and routes, and the pricing structure isn't always straightforward.

## The Solution: Data-Driven Decision Making

To solve this problem, I created the [Swiss Public Transport Calculator](https://github.com/d33pk3rn3l/SwissPublicTransportCalculator) - a Python-based Jupyter notebook that calculates and visualizes the cost-effectiveness of various travel card options based on your specific travel habits:

The calculator:

1. Takes your personal travel patterns as input
2. Calculates the annual cost for each available travel card option
3. Breaks down costs by route to show exactly where your money is going
4. Visualizes the results to help you make an informed decision

![Example calculation](https://github.com/d33pk3rn3l/SwissPublicTransportCalculator/blob/main/annual_costs_breakdown.png?raw=true)

## The How: From Travel Data to Cost Analysis

The calculator uses two simple CSV files as input:

### 1. Travel Cards (Travel_Cards.csv)

```csv
Travel Card,Cost (CHF)
Half-Fare, 152
GA, 2900
ZVV 9-Pass Zürich, 827.00
ZVV 1-2 Zone, 809.00
ZVV 3 Zonen, 1189.00
ZVV 4 Zonen, 1596.00
ZVV 9-Pass (alle Zonen), 1282.00
```

This file contains all available travel card options and their annual costs. You can customize it to include any travel cards available in your region.

### 2. Travel Routes (Travel_routes.csv)

```csv
Destination,Included in Travel Card,Costs,How many times per month
Home,[GA; bla],[Half-Fare: 38.00; ZVV 9-Pass (alle Zonen): 23.80],1
Ferienhaus Süd,[GA],[Half-Fare: 70.80],0.25
Ferienhaus West,[GA],[Half-Fare: 72.20],0.25
Westschweiz,[GA],[Half-Fare: 74.00],0.5
Hangar,[GA; ZVV 9-Pass Zürich; ZVV 3 Zonen; ZVV 4 Zonen; ZVV 9-Pass (alle Zonen)],[Half-Fare: 6.80],6
In Zürich,[GA; ZVV 9-Pass Zürich; ZVV 3 Zonen; ZVV 4 Zonen; ZVV 9-Pass (alle Zonen); ZVV 1-2 Zone],[Half-Fare: 6.20],20
```

This file contains:
- Your travel destinations
- Which travel cards include these destinations
- The cost of tickets for destinations not included in a travel card
- How frequently you travel to each destination per month

> This part is tedious, as you need to manually input the prices of each route and the frequency of your travels. But it's worth it for the savings! And you can usually reuse most of the data for future calculations.

### The Calculation Process

The Jupyter notebook performs these calculations:

1. **Data Loading**: Imports the CSV files and processes the data
2. **Cost Conversion**: Converts cost strings to numerical values
3. **Monthly Cost Calculation**: For each travel card, calculates:
   - Base cost of the card
   - Additional ticket costs for routes not covered by the card
   - Frequency-adjusted costs based on your travel patterns
4. **Annual Projection**: Projects costs over a full year
5. **Visualization**: Creates charts showing the cost breakdown and comparison between different travel cards

The result is a clear visualization showing which travel card offers the best value based on your specific travel patterns.

## Conclusion

By using data analysis to tackle this everyday problem, I've created a tool that can potentially save hundreds or even thousands of francs annually. The Swiss Public Transport Calculator makes it easy to make an informed decision about which travel card to purchase, removing the guesswork from what was previously a complex financial decision.

The project is open-source and available on [GitHub](https://github.com/d33pk3rn3l/SwissPublicTransportCalculator). Feel free to clone it, customize it for your own travel patterns, and find out which travel card is truly the most cost-effective option for you.

## Further Work

I'm currently exploring the possibility of deploying this calculator as a web application, which would allow everyone to easily input their travel data and get instant results. If you're interested in contributing to this project or have suggestions for improvements, please reach out!
