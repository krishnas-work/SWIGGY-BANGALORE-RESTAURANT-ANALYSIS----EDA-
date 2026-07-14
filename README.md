# Swiggy Bangalore Restaurant Analysis — Exploratory Data Analysis (EDA)

## 📌 Problem Statement
Restaurant listings scraped from Swiggy for Bangalore are analyzed to understand how pricing, ratings, and cuisine offerings vary across the city's major dining hubs, and to identify the best value-for-money restaurants.

## 🎯 Objectives
- Compare ratings and cost-for-two across Bangalore's key food hubs: BTM, HSR, and Koramangala
- Determine whether cost and rating are related
- Identify the most affordable, highly-rated restaurants (best value)
- Analyze the most popular cuisines, city-wide and per area

## 🗂️ Dataset
- **Source:** `Swiggy Bangalore Outlet Details.csv` (scraped restaurant listings)
- **Size:** 118 restaurants × 5 columns
- **Columns:** `Shop_Name`, `Cuisine`, `Location`, `Rating`, `Cost_for_Two`

## 🧹 Data Cleaning
- No missing values or duplicate rows found in the raw dataset
- `Rating`: `'--'` placeholders (unrated restaurants) replaced with `0`, converted to `float`
- `Cost_for_Two`: currency symbol (`₹`) stripped, converted to `int`
- `Location`: parsed via substring matching to segment restaurants into three key hubs — **Koramangala, HSR, BTM**

## 📊 Key Findings
- **BTM and Koramangala** offer similar value — ratings mostly 4.0-4.3, cost for two around ₹200-350. **HSR** is slightly pricier (₹300-400) with comparably strong ratings.
- **Cost and rating are only weakly related** — some 4.6+ rated restaurants cost as little as ₹150-250, while several ₹600-800 restaurants rate no higher than 4.0-4.3.
- Best value-for-money restaurants: **Khichdi Experiment (4.8, ₹200)**, **Natural Ice Cream (4.6, ₹150)**, **Corner House Ice Cream (4.6, ₹250)**
- **Chinese (35)** and **North Indian (32)** are the most common cuisines city-wide, followed by South Indian, Biryani, and Fast Food — a pattern that holds across all three hubs, with HSR showing more cuisine diversity relative to its size.

*(See the notebook for full area-wise rating/cost distributions and cuisine breakdowns.)*

## 💼 Business Recommendations
- Highlight affordable-but-highly-rated "hidden gem" restaurants in discovery features, since price doesn't reliably signal quality
- Promote under-represented cuisines in each hub to diversify options beyond the dominant Chinese/North Indian/South Indian mix
- Focus restaurant onboarding efforts in HSR, which has a smaller and more evenly spread cuisine base compared to BTM and Koramangala

## ⚠️ Limitations
- Unrated restaurants were encoded as `Rating = 0` rather than left null, which can distort rating-based averages if not filtered out
- Single time-snapshot dataset — does not capture how ratings/pricing change over time
- Location segmentation relied on substring matching, which works for these three hubs but would need generalizing (e.g. a proper location/pincode field) to scale citywide

## 🚀 Future Scope
- Expand to more Bangalore neighborhoods for a full city-wide comparison
- Combine with order volume/delivery time data to analyze popularity beyond ratings alone
- Build a "best value per cuisine and area" recommendation feature

## 🛠️ Tech Stack
`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `plotly` · `Jupyter Notebook`
