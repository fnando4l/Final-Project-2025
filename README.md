# New York City Air Quality Analysis

**STAT 230 — Spring 2025**
Fernand Gbodjo

---

## Overview

This project analyzes fine particulate matter (PM2.5) concentrations across New York City community districts using surveillance data from the [NYC Open Data portal](https://data.cityofnewyork.us/). The analysis investigates whether PM2.5 levels differ by location and whether seasonal patterns exist across months.

---

## Research Questions

1. Does the average PM2.5 concentration differ significantly between **Upper West Side (CD7)** and **Rockaway and Broad Channel (CD14)**?
2. Is there a statistically significant relationship between PM2.5 levels and **month of the year**?

---

## Dataset

**Source:** NYC Environment & Health Data Portal — Air Quality Surveillance
**File:** `Air_Quality.csv`

| Variable | Type | Description |
|---|---|---|
| `PM25` | Numeric | Fine particulate matter concentration (µg/m³) |
| `Location` | Categorical | Community district name |
| `Month` | Categorical | Month of measurement |
| `Time.Period` | Character | Time frame of measurement |

---

## Methods

| Step | Technique |
|---|---|
| Data wrangling | `tidyverse` (filter, select, mutate) |
| Descriptive statistics | Mean, SD, Min, Max by location |
| Visualization | Histogram, boxplot (`ggplot2`) |
| Inferential — Question 1 | Welch two-sample t-test |
| Inferential — Question 2 | One-way ANOVA |

---

## Key Findings

- **Upper West Side (CD7)** had a higher mean PM2.5 (~9 µg/m³) with greater variability than **Rockaway and Broad Channel (CD14)** (~7 µg/m³).
- The PM2.5 distribution showed a slight right skew, with most values falling between 5–12 µg/m³.
- The **t-test** returned p < 0.05, indicating a statistically significant difference in PM2.5 levels between the two districts.
- The **ANOVA** returned p > 0.05, suggesting no significant seasonal variation in PM2.5 across months.

These results highlight **spatial disparities** in NYC air quality and support the case for location-targeted public health policy.

---

## Project Files

| File | Description |
|---|---|
| `final_project2.qmd` | Quarto source document (R code + narrative) |
| `final_project.html` | Rendered HTML report |
| `Air_Quality.csv` | Raw dataset |
| `final STAT 230.mp4` | Presentation video |

---

## Tools & Technologies

- **R** (tidyverse, ggplot2)
- **Quarto** for reproducible reporting
- **RStudio**

---

## How to Reproduce

1. Clone the repository.
2. Open `final_project2.qmd` in RStudio (requires R and Quarto installed).
3. Install dependencies if needed:
   ```r
   install.packages("tidyverse")
   ```
4. Render the document:
   ```r
   quarto::quarto_render("final_project2.qmd")
   ```
   Or use the **Render** button in RStudio.
