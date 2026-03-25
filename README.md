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

- Geographic performance is concentrated in a few regions, with **Sub-Saharan Africa** and **Europe** contributing approximately **$74.4B each**, compared to **North America at $6.1B**. Despite this, margins remain consistent at around **34%**, reflecting standardized pricing and cost control.

- Channel performance is balanced, with Online and Offline sales showing similar volume distribution across categories. The primary strategic opportunity lies in optimizing product mix and improving margin efficiency rather than expanding geography or channels.
