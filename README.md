## Project Background & Overview
NovaRetail Inc. is a globally distributed omnichannel retailer managing a diversified product portfolio across multiple regions.

### Project Scope
To support upcoming planning and budgeting cycles, leadership commissioned a structured performance evaluation focused on revenue composition, 
margin sustainability, and financial exposure across products, geographies, and distribution channels. 

**Key Focus Areas:**
* **Identifying Margin Dilution:** Pinpointing specific products or regions where profitability is underperforming.
* **Performance Resilience:** Validating the stability of historical sales data to ensure reliable future forecasting.
* **Growth Identification:** Uncovering scalable levers within the existing portfolio to drive expansion.

### Core Objectives
The primary goals of this analysis are to assess **revenue durability**, **profitability efficiency**, and **capital productivity**. 
These insights are designed to guide:
* Strategic resource allocation decisions.
* Targeted margin enhancement initiatives.
* Sustainable, long-term value creation.

[Download Transformed Excel File](https://github.com/ruchi-010/global-sales-performance-analysis/blob/main/data/Sales%20Records%20transformed.xlsx)

[Excel Dashboard](https://github.com/ruchi-010/global-sales-performance-analysis/blob/main/Sales%20Records%20(excel).pdf)

[Download Sales Analysis Presentation](https://github.com/ruchi-010/global-sales-performance-analysis/blob/main/Sales%20Analysis%20Presentation.pdf)

## Data Structure and Data Engineering

This project follows a structured data lifecycle, moving from raw transactional logs to a validated analytical model. The following section details the schema structure and the engineering steps taken to ensure the data was "analysis-ready."

### **Initial Data Schema**
The source data provided 14 core attributes including Geographic markers (Region, Country), Product identifiers (Item Type), Sales Channels (Online, Offline), and five key financial metrics.

![Screenshot 2026-03-03 160858](https://github.com/user-attachments/assets/ba453cf0-15ec-461c-a3c4-c033d7b8175c)

### **Data Transformation & Engineering**
Before visualization, the following engineering tasks were completed to enhance the dataset's utility:
1. **Data Type Standardization:** Converted all financial fields to currency and all date fields to a standardized date format to enable accurate time-based calculations.
2. **Attribute Engineering:**
    * Created a **Time Hierarchy** (Year, Quarter, Month) for granular trend analysis.
    * Calculated **Shipping Days** to serve as a primary KPI for fulfillment efficiency.
    * Developed **Profit Margin %** to identify high-value categories that outperform their revenue weight.

### **Rigorous Data Quality Audit (DQA)**
To prevent "Garbage In, Garbage Out," a strict DQA was performed on the 500,000 raw records:
* **Removal of Chronological Inconsistencies:** Purged **365,306 records** where `Ship Date < Order Date`. These represented data entry errors or system bugs that would have invalidated lead-time metrics.
* **Lead-Time Normalization:** Excluded **1,960 records** with extreme lead times (over 1 year). These outliers were deemed non-representative of standard operating procedures at NovaRetail Inc.
* **Uniqueness Validation:** Confirmed 100% uniqueness of `Order ID` across the final set.

**Outcome:** The final validated dataset contains **233,472 records**, ensuring that every insight in this report is backed by logically consistent and operationally realistic data.

## **Executive Summary**

- The analysis covers **$287.0B in revenue**, **$84.8B in profit**, and a **34.37% average margin** across **1.08B units sold**. Revenue and profit remained structurally stable from 2010 to 2016, with annual revenue ranging between **$40.67B and $41.61B**.

- Product performance shows clear concentration. **Household** is the top revenue category, while **Clothes** leads in margin at **67.2%**, and **Cosmetics** contributes the most profit. The top three categories account for **55% of total revenue**, indicating a gap between scale and profitability.

![Screenshot 2026-03-25 131440](https://github.com/user-attachments/assets/f01d46e0-47d6-424f-8bb1-f272a6cf8c23)

- Geographic performance is concentrated in a few regions, with **Sub-Saharan Africa** and **Europe** contributing approximately **$74.4B each**, compared to **North America at $6.1B**. Despite this, margins remain consistent at around **34%**, reflecting standardized pricing and cost control.

![Screenshot 2026-03-25 131733](https://github.com/user-attachments/assets/44a51011-7ead-415a-bf5a-c0f24bf7b1ad)

- Channel performance is balanced, with Online and Offline sales showing similar volume distribution across categories. The primary strategic opportunity lies in optimizing product mix and improving margin efficiency rather than expanding geography or channels.

# Detailed Insights & Strategic Analysis: Global Sales Performance

This section provides a technical deep-dive into the performance metrics of the NovaRetail dataset, focusing on **Revenue Durability**, **Profitability Efficiency**, and **Capital Productivity**.

## 1. Time Intelligence Analysis (Revenue Durability)

* **The Growth Plateau & Stagnation Phase:** While the cumulative revenue of **$287.02B** is substantial, a longitudinal analysis reveals a distinct growth plateau. Year-over-Year (YoY) growth peaked at **1.97% in 2013** before entering a period of marginal contraction with **-1.07% in 2014** and **-1.18% in 2015**. This suggests that the enterprise has transitioned from an expansionary phase to a "mature stability" phase, where protecting the existing base is as critical as seeking new volume.

![Screenshot 2026-03-25 132106](https://github.com/user-attachments/assets/b1d035d8-529f-43f8-b16f-5ef4b245a48e)


* **Volume/Price Decoupling Trends:** Analysis of the **1.07B total units sold** across the period shows that sales volume remains remarkably static, averaging approximately **153.5M units per year**. Since volume is nearly constant, the observed revenue fluctuations are not a result of market share expansion but are driven by internal shifts in "basket composition", specifically the ratio of high-unit-price items (like Household goods at **$668.27**) versus low-unit-price staples.
* **Exceptional Quarterly Run-Rate Resilience:** The data exhibits extreme operational consistency at the quarterly level, with a mean Quarter-over-Quarter (QoQ) variance of just **0.069%**. This level of stability is rare in global retail and indicates a supply chain and demand forecasting system that has effectively "de-risked" the business from seasonal shocks or inventory-driven revenue volatility.
* **Margin Preservation During Revenue Dips:** A pivotal indicator of durability was observed in **2015**; despite a top-line revenue decline of **$488M** compared to the previous year, total profit remained essentially flat at **$12.02B**. This proves the existence of a flexible cost structure capable of maintaining "bottom-line integrity" even when the high-revenue engines experience temporary softening.

## 2. Product Performance Analysis (Profitability Efficiency)

* **The High-Efficiency Profit Engine (Clothes):** The **Clothes** category is the primary driver of profitability efficiency for the entire organization. While it accounts for a relatively modest **$32.1B (11.2%) of total revenue**, it generates a disproportionate **$21.5B (25.4%) of total profit**. Its **67.2% profit margin** is nearly double the corporate average, making it the most capital-productive asset in the portfolio.
* **The Capital Intensity Trap (Meat & Office Supplies):** The analysis pinpoints a significant "efficiency leak" in the **Meat** and **Office Supplies** categories. **Meat** requires high capital exposure with a unit price of **$421.89** yet yields a portfolio-low margin of **13.5%**. Similarly, **Office Supplies** drive **20.2% of total revenue ($58B)** but only **13.3% of profit**, indicating that these categories consume significant operational resources for a comparatively low net return.

![Screenshot 2026-03-25 132141](https://github.com/user-attachments/assets/282a65f2-3503-4475-bb84-a3478f168f3f)

* **Cosmetics as the Unit Productivity Benchmark:** On a "per-transaction" basis, **Cosmetics** outperforms all other categories. Every single unit of Cosmetics sold contributes **$173.87 in net profit**, contrasted sharply against the **$57.20** generated per unit of Meat. Prioritizing the "per-unit" productivity of Cosmetics offers a scalable lever for value creation that does not require the massive logistics overhead of the lower-margin, high-volume segments.
* **Dilution from Low-Value Staple Verticals:** A "low-value anchor" segment exists within the portfolio, consisting of **Fruits, Beverages, and Personal Care**. **Fruits**, for example, contribute a negligible **$2.41 in profit per unit**. While these items may drive customer frequency, they structurally dilute the corporate margin. Strategic intervention is required to determine if these categories are effectively serving as "loss leaders" or if they are misallocated capital that should be pivoted toward mid-tier efficiency leaders like **Cereal (43.1% margin)**.

![Screenshot 2026-03-25 132217](https://github.com/user-attachments/assets/b9f8da89-b449-4e04-8a97-e67293efe3c7)


## 3. Regional Performance Analysis (Capital Productivity)

* **Strategic "Hub-Market" Dependency:** A deep-dive into geographic revenue distribution reveals that the $287B base is anchored by strategic logistics and trade hubs rather than broad consumer populations. The **Maldives ($1.68B)** and **Singapore ($1.67B)** are the top two revenue-contributing countries. This suggests that NovaRetail's revenue durability is currently optimized around high-efficiency, high-traffic trade nodes.
* **The North American Scalability Gap:** Despite its status as a premier global market, **North America** represents a mere **$5.97B (2.1%) of total revenue**. Given that the region operates at the same **34.4% margin** as the rest of the world, it represents the single largest "growth lever" in the portfolio. Scaling this region to even 10% of total revenue would add over **$20B** to the top line without introducing margin risk.

![Screenshot 2026-03-25 132257](https://github.com/user-attachments/assets/53d0f9b7-220e-4751-9116-ab7c68ad79de)

* **Geographic Diversification as a Risk Hedge:** The portfolio is shielded from country-specific economic shocks through extreme diversification. The **Top 5 Countries** combined contribute only **2.91% of total revenue**. This granular distribution ensures that no single geopolitical event or local market downturn can materially threaten the stability of the **$84.7B total profit** base.
* **Global Model Portability & Operational Parity:** The data confirms "Operational Parity" across all seven global regions, with **Revenue per Unit** holding steady at **~$266** and **Profit per Unit** at **~$78** globally. This consistency is a powerful indicator of capital productivity; it proves that the business model is perfectly portable and that leadership can reallocate capital to any region with a high degree of confidence in the resulting margin and return.

## Key Recommendations & Tradeoffs

### 1. Focus on High-Margin Products
Prioritize capital toward the most efficient products by making Clothes and Cosmetics the portfolio leaders for investment and expansion.  
**Tradeoff:** This can increase profits, but it may reduce focus on products that bring in more customers overall.

---

### 2. Reassess Low-Return Staples
Reassess low-return staples like Fruits, Beverages, and Personal Care to decide whether they should be kept as traffic drivers or restructured for better margin.  
**Tradeoff:** Improving margins here may help profits, but it could reduce how often customers come to shop.

---

### 3. Improve Product Mix
Reduce dependency on low-efficiency volume in categories like Meat and Office Supplies by improving assortment mix and pushing higher-margin substitutes.  
**Tradeoff:** Focusing on fewer, better products can improve returns, but customers may feel there are fewer choices.

---

### 4. Expand in North America
Put more effort into growing in North America, where the business is still small but has strong potential.  
**Tradeoff:** This can unlock growth, but returns may be slower and less predictable in new markets.
