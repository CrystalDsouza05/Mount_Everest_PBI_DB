# Mount Everest Exploration Dashboard

### 📊 Dashboard Link Coming Soon...

## 📌 Problem Statement

This Power BI dashboard analyzes historical data of Mount Everest expeditions, climbers, and peaks to uncover patterns in summits, deaths, seasonal trends, and geographic risks. It helps researchers, mountaineers, and enthusiasts understand the evolution of Everest expeditions and key risk-reward dynamics over decades.

---

Snap of Dashboard Pages (3):

![Image](https://github.com/user-attachments/assets/cc2b889e-6d62-472e-b175-c4fe072b5e47)

![Image](https://github.com/user-attachments/assets/248c15bf-2b35-4d04-b51b-656eb3557a17)

![Image](https://github.com/user-attachments/assets/6ce38995-d893-4d90-8a31-defcc8fd4152)

---

## 📄 Pages Included

| Page No. | Page Name          |
|----------|--------------------|
| 1        | The Everest Legacy |
| 2        | The Climbers       |
| 3        | Risks and Rewards  |

---

## 🧩 Key Visuals and Features

### ✅ The Everest Legacy
- KPI cards for total expeditions, summits, and deaths
- Area chart of expedition trends over time and season
- Column chart for Total Summits and Deaths
- Slicers for filtering by season and time period

### ✅ The Climbers
- Donut charts showing climber gender and successful solo climbs
- Bar charts showing summits by season
- Top 10 climbers table
- Line chart for summit rate (%) by year
- Slicers for filtering by 25-year period

### ✅ Risks and Rewards
- Funnel chart of Total Summits and Deaths
- Bar charts of deaths by region, occupation and season.
- Line chart showing death rate (%) vs. number of climbers
- Peaks climbed by month line chart
- Slicers for filtering by time period (Interval 25 years )
---
Added Page Navigators and Refresh Button on all Pages.
---

## ⚙️ DAX Measures & Expressions

Key Measures created include:

```DAX
Summit Rate (%) = DIVIDE([Total Summits], [Total Members])
Death Rate (%) = DIVIDE([Total Deaths], [Total Members])
Deaths by Season = CALCULATE([Total Deaths], ALLEXCEPT(exped, exped[season]))
Summits with Oxygen = CALCULATE([Total Summits], 'members'[mo2used] = TRUE())
Total Attempts = COUNT('members'[expid])
Total Deaths = CALCULATE(COUNTROWS('members'), 'members'[death] = TRUE)
Total Expeditions = DISTINCTCOUNT(exped[expid])
Total Members = COUNTROWS('members')
Total Peaks = COUNT(peaks[peakid])
Total Solo Climbs = CALCULATE(COUNTROWS('members'), 'members'[msolo] = TRUE())
Total Summits = CALCULATE(COUNTROWS('members'), 'members'[msuccess] = TRUE)
Yearly Summits = CALCULATE([Total Summits], ALLEXCEPT('members', 'members'[myear]))
```
## 📊 Tables & Relationships

- **Used Tables:**
  - `exped` – – Expedition data including season, routes, and members
  - `Members` – Detailed climber profiles and achievements
  - `peaks` – Peak metadata including location and region
  

- **Relationships:**
  - `exped` linked with `members` via expedition ID
  - `members` and `exped` linked to `peaks` by peak ID

  ---
- **Data Model:**
- ![Image](https://github.com/user-attachments/assets/68f8304a-1373-414f-afbf-8dddec769f13)

## 🔍 Insights Uncovered

- Total expeditions peak during the Autumn and Spring seasons, indicating these as the most preferred climbing windows.
- There has been a steady growth in the number of expeditions over the past decade, reflecting increased interest and accessibility.
- 2018 recorded the highest number of deaths, even as total summits reached a peak of 1,862, suggesting a year of both high achievement and significant risk.
- Out of 133 solo climbers, 84 were successful, highlighting the extreme difficulty and risk involved in solo ascents.
- The death rate has shown a gradual decline over the last 10 years, pointing to improved safety practices and better expedition planning.

---

## 🚀 Tech Stack

- Power BI Desktop & Power BI Service
- MS Excel for Data Source 
- DAX  
- Power Query  
- ZoomCharts Visuals
- PowerPoint and Figma for Design
- PBI Helper for documentation

---
