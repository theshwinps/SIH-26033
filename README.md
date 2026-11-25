# Smart India Hackathon Workshop
# Date:25/11/2026
## Reference Number:26005632
## Name:THESHWIN P S

## Problem Title
SIH 26033: Multiple intermediaries reduce farmers earnings and increase consumer prices.

## Problem Creater's Organization
Ministry of Consumer Affairs, Food & Public Distribution

## Theme
Agriculture, FoodTech & Rural Development

## Problem Description
Expected Solution: Create a digital marketplace that:

• Connects farmers/FPOs directly with consumers and bulk buyers.
• Provides logistics support.
• Uses AI for demand forecasting and route optimization.

Benefits:

• Better prices for farmers.
• Lower prices for consumers.
• Reduced supply chain inefficiencies.

## Proposed Solution
Kathir is an order-first supply platform for Farmer Producer Organizations (FPOs). Instead of farmers harvesting and then hunting for a buyer, buyers commit first and farmers harvest against those orders.

It runs on a weekly cycle. Apartment communities, hostels and small restaurants place orders before a cutoff, say Tuesday night, for delivery later in the week. The FPO coordinator opens the app and sees confirmed demand per crop before anyone has cut a single vegetable.

A planning model then looks at the confirmed orders, recent mandi prices and the season. It estimates how much extra demand and what price range to expect, and it splits the harvest across the FPO's member farmers so they don't all pick the same crop on the same day.

Delivery goes to one fixed drop point per community instead of every doorstep, so a handful of vehicle trips can serve a whole area. Every order receipt shows what share of the price reached the farmer.
Farmers know what is sold before they harvest, so there is less distress selling and less rot. Buyers get fresher produce at a lower price because a layer of middlemen and a lot of wasted transport disappear. Pickup-point delivery makes logistics cheap enough to work for small orders, which is where most agri-logistics ideas break down.
. Innovation and uniqueness

Order-before-harvest instead of list-and-hope
The AI coordinates farmers within an FPO to avoid gluts, instead of only predicting prices
Pickup-point delivery shrinks the routing problem and the cost per kg
A visible farmer-share receipt builds buyer trust and generates impact data automatically
A built-in fallback: any produce not covered by orders goes to the regular mandi, so no farmer is ever worse off than today
## Technical Approach
Frontend: React web app for buyers and FPO coordinators; simple WhatsApp-based flow for farmers
Backend: Python (FastAPI) with PostgreSQL
Planning and forecasting: gradient-boosted model (XGBoost) with a seasonal baseline, trained on Agmarknet mandi price data for 3 to 4 crops. Since real order history won't exist yet, early training uses mandi data and simulated orders, which we say openly.
Routing: Google OR-Tools capacitated vehicle routing, from the FPO collection point to about 10 to 15 community drop points
Maps: OpenStreetMap
Payments: UPI (test mode for the prototype), held until delivery is confirmed
Language: Tamil text templates for WhatsApp; voice via Bhashini APIs as a stretch goal

## Feasibility and Viability
1. Feasibility

Everything in the stack is free or open source, and the data we need is public. FPOs already aggregate produce and have a coordinator, so we are adding a planning layer on top of something that exists. A one-FPO, three-community, four-week pilot is realistic.

2. Challenges and risks

Buyers over-ordering or cancelling
Early forecasts being weak with so little local data
Quality disputes on delivery
Farmers hesitating to trust a new system
Dependence on a single transport provider

3. Strategies

A small advance token and a firm weekly cutoff keep orders reliable
The mandi fallback means joining carries no downside for the farmer, which helps with trust
Quality is checked at collection and at the drop point, with photo proof
We begin with simple, explainable models and show the FPO why each suggestion is made
Two or three local transport partners instead of one
The pilot has clear success measures: farmer price vs mandi price, percentage of produce wasted, and delivery cost per kg

## Impact and Benefits
1. Impact on the target audience

Farmers and FPO members get more predictable income and fewer forced low-price sales. Communities and small businesses get dependable fresh supply and can see exactly where their money goes. Transporters get fuller, planned trips instead of scattered small runs.

2. Benefits

Economic: a higher share of the final price for farmers, lower cost per kg for buyers
Social: stronger FPOs and real market access for small farmers
Environmental: less food wasted, fewer half-empty trips and so lower fuel use

## Research and References
Agmarknet, mandi price data (agmarknet.gov.in)
e-NAM platform (enam.gov.in)
Google OR-Tools vehicle routing documentation
ICAR-CIPHET studies on post-harvest losses in fruits and vegetables
Government and SFAC material on FPOs
