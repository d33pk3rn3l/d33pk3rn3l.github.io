---
layout: post
title: "Swiss Public Transport Cost Calculator"
date: 2025-05-06 15:45:19
category: posts
---

# Finding Your Best Travel Card

Ever stood at a Swiss train station kiosk, staring at all those subscription options and wondering which one would actually save you money? I've been there too.

## The Challenge

Switzerland's public transport is amazing, but choosing between a GA (General Abonnement), Half-Fare card, or regional passes like ZVV can be overwhelming. The right choice depends entirely on your personal travel patterns, and calculating this manually is a headache.

After wasting too much money on the wrong subscriptions, I decided to solve this with code.

## My Simple Solution

I created a [Swiss Public Transport Calculator](https://github.com/d33pk3rn3l/SwissPublicTransportCalculator) using Python that:

1. Takes your regular travel routes as input
2. Calculates the annual cost for each subscription option
3. Shows you exactly which card saves you the most money

The tool uses two basic CSV files:
- One listing available travel cards and their costs
- Another detailing your regular routes, their prices, and how often you travel them

The calculator then does the math and creates a visual breakdown of your annual costs with each option.

![Cost comparison chart showing different travel card options](https://github.com/d33pk3rn3l/SwissPublicTransportCalculator/blob/main/annual_costs_breakdown.png)

## Try It Yourself

The project is open-source on [GitHub](https://github.com/d33pk3rn3l/SwissPublicTransportCalculator). The setup takes about 30 minutes (mostly looking up ticket prices), but could save you hundreds or even thousands of francs.

I'm working on making this into a simple web app so everyone can use it without needing to code. In the meantime, if you're comfortable with Jupyter notebooks, give it a try and let me know how much you saved!
