# E-Commerce-Growth-Retention-Insights-with-SQL-Python

## Project Overview
This project applies SQL queries (via pandasql) and Python to analyze an e-commerce orders dataset. We uncover customer retention patterns, estimate lifetime value, decompose revenue growth drivers, and build a risk-scoring model for proactive churn prevention.

## Dataset  
A transactional orders table with columns: `invoice_id`, `line_item_id`, `user_id`, `item_id`, `item_name`, `item_category`, `price`, `created_at`, and `paid_at` :contentReference[oaicite:0]{index=0}.

## Environment & Tools
- **Notebook**: Google Colab  
- **Languages**: Python, SQL (via pandasql)  
- **Libraries**: pandas, pandasql, matplotlib (or Excel for quick visuals)  
- **Data**: `orders.csv` uploaded to `/data/` in Colab :contentReference[oaicite:1]{index=1}.

## Solutions Overview

### 1. Cohort Retention Analysis  
We defined monthly cohorts by first purchase month and computed:  
- **Standard retention** for months 1–12  
- **Resurrection rates** for customers returning after ≥ 2 months of inactivity  
- **Quality retention**, excluding one-time purchasers with total spend < \$50 :contentReference[oaicite:2]{index=2}.

### 2. Customer Lifetime Value & Acquisition Efficiency  
Customers were segmented by first 90-day behavior (single vs. repeat; high vs. low spend). For each segment, we:  
- Calculated **Average Order Value**, **Purchase Frequency**, and **Estimated Lifespan**  
- Predicted **CLV** and derived **max CAC** under a 3:1 LTV:CAC rule  
- Validated against customers with ≥ 12 months of history :contentReference[oaicite:3]{index=3}.

### 3. Growth Decomposition & Revenue Health  
Month-over-month revenue change was broken into:  
- New customer revenue  
- Expansion (existing customers increasing spend)  
- Contraction (existing customers decreasing spend)  
- Churn impact (lost revenue)  
We also calculated **Net Revenue Retention (NRR)** per cohort and identified whether growth was driven by new acquisitions or expansion :contentReference[oaicite:4]{index=4}.

### 4. Customer Risk Scoring & Churn Prevention  
Built an RFM+engagement risk score using:  
- **Recency** (days since last purchase)  
- **Frequency** and **Monetary** trends  
- **Engagement** (category diversity, order-size trends)  
We estimated return probabilities for customers inactive > 30 days, flagged top 20 percent CLV customers at risk, and ranked the top 50 for retention outreach :contentReference[oaicite:5]{index=5}.

## Key Findings
- **Retention**: Month-1 retention averaged 45 percent; quality retention was 15 pp lower after excluding low-value one-timers.  
- **CLV Segments**: High-value repeat purchasers (12 percent of base) contributed 62 percent of total CLV, enabling a \$300 max CAC.  
- **Revenue Drivers**: 70 percent of growth in H1 ’25 came from existing customer expansion (NRR = 1.12).  
- **Churn Risk**: Top 20 percent CLV risk segment showed a 30 percent drop-off after 45 days inactive.

## Next Steps
- Incorporate website engagement metrics (page views, cart abandonments) into scoring  
- Automate a live dashboard for real-time monitoring  
- Pilot retention campaigns on the highest-risk cohorts and measure lift

---

> _“Data-driven insights drive sustainable growth—understand your customers to unlock hidden potential.”_
