# 🚲 Urban Mobility SQL Analysis
### NYC Citi Bike Trip Data · Snowflake SQL · Emina Toric

---

## Overview

This project analyzes **NYC Citi Bike trip data** to uncover patterns in urban mobility — 
who's riding, when, where, and what that tells us about how cities move. 

The analysis is structured as a consulting deliverable: starting with data exploration, 
moving through behavioral segmentation, and ending with infrastructure recommendations 
grounded in the data.

**Tools:** Snowflake SQL · CSV exports · Markdown documentation  
**Dataset:** [NYC Citi Bike System Data](https://citibikenyc.com/system-data) (public)  
**Analyst:** [Emina Toric, MSc](https://linkedin.com/in/emina-toric-msc)

---

## Business Questions Answered

| # | Question | SQL Script |
|---|----------|------------|
| 1 | What are the busiest stations and when do they peak? | `01_station_demand.sql` |
| 2 | How do weekday vs weekend trip patterns differ? | `02_temporal_patterns.sql` |
| 3 | Which routes (station pairs) are most frequently traveled? | `03_popular_routes.sql` |
| 4 | How does trip duration vary by user type and time of day? | `04_trip_duration.sql` |
| 5 | Where are the infrastructure gaps — high demand, low supply? | `05_infrastructure_gaps.sql` |
| 6 | What does seasonal ridership look like across the year? | `06_seasonal_trends.sql` |

---

## Key Findings

### 🔵 Peak Demand is Hyper-Concentrated
The top 10 stations account for a disproportionate share of total trip starts. 
Grand Central Terminal, Central Park South, and W 21 St & 6 Ave consistently 
rank highest — with morning peaks between 7–9am and evening peaks between 5–7pm 
confirming commuter-driven usage patterns.

### 🟢 Weekend Riders Behave Differently
Weekday trips average shorter durations with tight temporal clustering (commute windows). 
Weekend trips are longer, more evenly distributed across the day, and skew toward 
tourist-adjacent stations — suggesting leisure and exploration rather than utility.

### 🟡 Subscriber vs Casual Rider Gap
Annual subscribers take shorter, more frequent trips. Casual (pay-per-ride) users 
take fewer but significantly longer trips. This behavioral segmentation has direct 
implications for pricing strategy and station placement.

### 🔴 Infrastructure Gaps Identified
Several high-traffic neighborhoods show imbalanced dock capacity relative to trip 
demand — meaning bikes are frequently unavailable during peak hours. The analysis 
flags 8 specific station clusters where capacity expansion would have the highest 
ridership impact.

---

## Project Structure

```
urban-mobility-sql/
│
├── README.md                    ← You are here
│
├── sql/
│   ├── 00_setup.sql             ← Database setup and data loading
│   ├── 01_station_demand.sql    ← Station-level demand analysis
│   ├── 02_temporal_patterns.sql ← Time-of-day and day-of-week patterns
│   ├── 03_popular_routes.sql    ← Most-traveled origin-destination pairs
│   ├── 04_trip_duration.sql     ← Duration analysis by segment
│   ├── 05_infrastructure_gaps.sql ← Supply vs demand gap identification
│   └── 06_seasonal_trends.sql  ← Monthly and seasonal ridership trends
│
├── results/
│   ├── top_stations.csv         ← Top 20 stations by trip volume
│   ├── hourly_patterns.csv      ← Avg trips per hour by day type
│   ├── popular_routes.csv       ← Top 50 station-to-station routes
│   └── seasonal_summary.csv    ← Monthly ridership summary
│
└── docs/
    └── methodology.md           ← Data notes and analytical decisions
```

---

## How to Run

1. Sign up for a [Snowflake free trial](https://signup.snowflake.com/) (30 days free)
2. Download the Citi Bike trip data from [citibikenyc.com/system-data](https://citibikenyc.com/system-data)
3. Run `sql/00_setup.sql` to create your database schema and load data
4. Run scripts `01` through `06` in order — each builds on the previous
5. Export results using Snowflake's UI or `COPY INTO` commands

---

## Skills Demonstrated

- Complex `JOIN` operations across multiple tables
- Window functions (`ROW_NUMBER`, `RANK`, `LAG`, `LEAD`, `PARTITION BY`)
- Aggregations with `GROUP BY`, `HAVING`, and `ROLLUP`
- CTEs (Common Table Expressions) for readable, layered logic
- Date/time manipulation and temporal bucketing
- Subqueries and correlated subqueries
- Data quality checks and NULL handling
- Snowflake-specific features: `QUALIFY`, `SAMPLE`, `FLATTEN`

---

*Part of my data analytics portfolio. See more at [eminatoric.github.io](https://eminatoric.github.io)*
