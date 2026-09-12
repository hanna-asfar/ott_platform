# OTT Streaming Intelligence

## Power BI Project

OTT Streaming Intelligence is an interactive Power BI solution for
analyzing OTT subscription sales, customers, churn, platforms, plans,
content, and geographic revenue.

**Workflow:** Raw Data → Power Query → Star Schema → DAX → Dashboard →
Validation → Insights

## Objectives

-   Monitor revenue and transaction performance
-   Understand customer activity, churn, and renewals
-   Compare OTT platforms and subscription plans
-   Analyze content, genres, and content types
-   Compare country and regional revenue
-   Provide interactive business analysis

## Dataset

The Excel source contains:

  Table                   Purpose
  ----------------------- -------------------------------------------
  FactSubscriptionSales   Subscription transaction and revenue data
  DimCustomer             Customer attributes and status
  DimPlatform             OTT platform information
  DimPlan                 Subscription plan and billing information
  DimContent              Content, genre, language, and type
  DimLocation             Country, state, city, and region
  DimDate                 Calendar and time analysis

## Data Preparation

Power Query was used for:

-   Data type correction
-   Header promotion
-   Text trimming and standardization
-   Identifier standardization
-   Duplicate removal
-   Invalid date and value handling
-   Missing-value review
-   Location data validation

Missing descriptive values were retained when the correct value could
not be determined reliably.

## Data Model

The project uses a **Star Schema**.

**Fact:** `FactSubscriptionSales`

**Dimensions:** `DimDate`, `DimCustomer`, `DimPlatform`, `DimPlan`,
`DimContent`, `DimLocation`

All dimension-to-fact relationships use **1:\*** cardinality and
**single-direction** filtering.

**Fact grain:** one subscription transaction per `Sale_ID`.

## DAX

Key measures include:

-   Total Revenue
-   Total Transactions
-   Total Customers
-   Active Customers
-   Churned Customers
-   Churn Rate
-   Renewal Rate
-   Revenue per Customer
-   Average Transaction Value
-   Previous Year Revenue
-   YoY Revenue Growth %
-   Revenue YTD
-   Revenue MTD
-   Previous Month Revenue
-   MoM Revenue Growth %

Example:

``` dax
Total Revenue =
SUM(FactSubscriptionSales[Net_Revenue])
```

## Dashboard Pages

### 1. Executive Overview

KPIs: - Total Revenue --- 9.38M - Total Customers --- 299 - Active
Customers --- 126 - Churn Rate --- 37.5% - Renewal Rate --- 40.0%

Visuals: - Revenue Trend - Revenue by Region - Revenue by Platform -
Revenue by Plan

### 2. Sales & Platform Analysis

KPIs: - Total Revenue --- 9.38M - Total Transactions --- 2K - Average
Transaction Value --- 4.42K - Revenue per Customer --- 31.38K

Visuals: - Revenue by Platform - Transactions by Platform - Revenue by
Plan - Revenue by Billing Cycle - Monthly Revenue Performance

### 3. Customer & Subscription Analysis

KPIs: - Total Customers --- 299 - Active Customers --- 126 - Churned
Customers --- 112 - Churn Rate --- 37.5% - Renewal Rate --- 40.0%

Visuals: - Customer Status - New vs Renewal Subscriptions - Churn by
Segment - Customers by Segment - Subscription Trend

### 4. Content & Geographic Analysis

KPIs: - Total Revenue --- 9.38M - Total Transactions --- 2K - Total
Content --- 173 - Total Regions --- 5

Visuals: - Revenue by Genre - Revenue by Content Type - Revenue by
Country - Revenue by Region - Top 10 Content by Revenue

## Interactivity

Slicers include:

-   Year
-   Platform
-   Plan
-   Region
-   Customer Segment
-   Subscription Type
-   Content Type

Page navigation connects the four dashboard pages.

## Key Insights

-   Total validated revenue is **9.38M**.
-   The model contains **299 distinct customers**.
-   **126 customers** are active and **112** are classified as churned.
-   The validated churn rate is **37.5%**.
-   The renewal rate is **40.0%**.
-   Platform, plan, content, and geography provide multiple
    revenue-analysis perspectives.
-   APAC and North America are the largest displayed regional
    contributors.
-   Customer retention is an important business focus.

## Data Quality

Some source attributes contain missing values, including selected
customer, subscription, payment, quantity, discount, net-revenue,
platform, and plan attributes.

These were reviewed without inventing unsupported values.

A blank category may appear in **Top 10 Content by Revenue** where
revenue exists without a usable content title. It is retained to avoid
silently excluding valid revenue.

## Tools

-   **Excel** --- Source data
-   **Power Query** --- Cleaning and transformation
-   **Power BI** --- Modeling and visualization
-   **DAX** --- Measures and time intelligence

## Project Structure

``` text
POWER-BI-PROJECT/
├── BRD.pdf
├── FRD.pdf
├── CHECKLIST.pdf
├── ANALYSIS_REPORT.pdf
├── README.md
└── OTT Streaming Intelligence.pbix
```

## Documentation

-   **BRD.pdf** --- Business requirements
-   **FRD.pdf** --- Functional requirements and KPI definitions
-   **CHECKLIST.pdf** --- Development and validation checklist
-   **ANALYSIS_REPORT.pdf** --- Analysis, findings, and recommendations
-   **README.md** --- Project and technical overview

## Business Recommendations

-   Prioritize customer retention initiatives.
-   Monitor churn and renewal together.
-   Use platform and plan performance to guide commercial decisions.
-   Promote high-performing content and genres.
-   Use geographic performance for market-specific strategies.
-   Improve source-data completeness for missing attributes.

## Project Status

**Completed**

Business requirements, data preparation, Power Query transformations,
Star Schema, DAX measures, four dashboard pages, formatting, slicers,
navigation, validation, checklist, and analysis report are complete.

## Conclusion

The project demonstrates a complete Power BI workflow from raw OTT data
to a validated, interactive business intelligence solution covering
**revenue, customers, subscriptions, platforms, content, and
geography**.
