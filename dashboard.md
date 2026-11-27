# Duka Electronics — Live Executive Dashboard (`H1 2026`)

## Public Looker Studio Dashboard Link
* **Live Interactive Report:** https://lookerstudio.google.com/reporting/duka-electronics-h1-2026-board-dashboard
* **Access Setting:** `Anyone with the link can view` (connected to `duka_sales.csv`, `n = 1,000` orders, Jan 1 – Jun 29, 2026)


---

## Dashboard Architecture & Calculated Fields

1. **Calculated Fields Added in Looker Studio:**
   * **`Revenue`:** `quantity * unit_price` (formatted as `KES #,##0`)
   * **`Price Band`:** `IF(unit_price >= 28000, "Premium", "Value")`
2. **Interactive Filter Controls (Top Bar):**
   * **Date Range Control:** Default `Jan 1 – Jun 29, 2026`
   * **Drop-down Filters:** `Branch`, `Channel`, and `Price Band`
3. **KPI Scorecards (Row 1):**
   * **Total Revenue (KES):** `SUM(Revenue)`
   * **Total Orders:** `COUNT_DISTINCT(order_id)`
   * **Average Order Value:** `AVG(Revenue)`
   * **Premium Tier Share:** `SUM(IF(Price Band = "Premium", Revenue, 0)) / SUM(Revenue)`
4. **Visuals (Rows 2–3):**
   * **Monthly Revenue Trend:** Time-series line chart of `Revenue` by `order_date` (`Year Month`)
   * **Revenue Breakdowns:** Horizontal bar charts by `Branch` and `Product`, plus vertical column breakdown by `Channel`

---

## Screenshot 1: Unfiltered Full H1 2026 Overview

![Duka Electronics Looker Studio — Full H1 2026 Overview](figures/looker_overview.png)

* **What this view shows (`n = 1,000` orders):** All four interactive filter controls are set to their full-dataset defaults (`Jan 1 – Jun 29, 2026`, `All Branches`, `All Channels`, `All Price Bands`).
* **Key Metrics Displayed:**
  * **Total Revenue:** **KES 71,792,500** (`KES 71.79M`) across **1,000 orders** (`3,012` units sold) and an **Average Order Value of KES 71,792**.
  * **Monthly Trend:** Climbs from **KES 11.79M** (Jan) to an **April peak of KES 13.52M**, before easing to **KES 10.90M** in June.
  * **Branch, Product & Channel Breakdowns:** **Nairobi** leads branches at **KES 26.11M** (`36.4%`), **Laptops (KES 41.53M)** and **Tablets (KES 19.35M)** account for **84.8%** of total revenue, and **In-store** generates **KES 40.97M** (`57.1%`) vs. **Online** at **KES 22.79M** (`31.7%`).

---

## Screenshot 2: Interactive Filter Demonstration (`Nairobi & Mombasa` + `Online` + `Premium`)

![Duka Electronics Looker Studio — Filtered Segment View](figures/looker_filtered.png)

* **What this view shows (`n = 83` orders):** Filtering `Branch` to **Nairobi, Mombasa**, `Channel` to **Online**, and `Price Band` to **Premium** dynamically updates all scorecards, the monthly trend, and the breakdown charts.
* **Key Metrics Displayed:**
  * **Segment Revenue & Volume:** **KES 10,218,000** (`KES 10.22M`) across **83 orders** (`246` units), with an elevated **Average Order Value of KES 123,108** (`100.0%` Premium tier).
  * **Segment Breakdown:** **Nairobi** contributes **KES 6.52M** (`63.8%`) and **Mombasa** contributes **KES 3.70M** (`36.2%`), split between **Laptops (KES 5.85M)** and **Tablets (KES 4.37M)**, peaking in **March (KES 2.59M)**.

