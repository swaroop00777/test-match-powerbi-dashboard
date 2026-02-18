# 🏏 ICC Test Match Analytics Dashboard (Power BI)

An interactive multi-page Power BI dashboard built to analyze Test cricket match data after 2000.  
This project demonstrates an end-to-end data analytics workflow including data cleaning, transformation, DAX calculations, and professional dashboard design.

---

# 🎯 Project Objective

The goal of this project is to create an analytical dashboard that provides insights into:

- Team performance analysis
- Batting and bowling performance comparison
- Match trends across years and venues
- Interactive filtering for dynamic insights

---

# 📊 Dashboard Pages

## 1️⃣ Overview Page

Executive summary view including:

- Total Runs
- Total Wickets
- Total Balls
- Run Rate
- Runs by Team
- Wickets by Team
- Venue Analysis
- Year Trends

---

## 2️⃣ Batting Analysis

- Top run scorers
- Strike rate vs runs comparison
- Runs distribution by over
- Team batting comparison

---

## 3️⃣ Bowling Analysis

- Top wicket takers
- Bowling performance comparison
- Opposition analysis
- Tactical performance visuals

---

# 🧹 Data Cleaning & Transformation

The dataset contained ball-by-ball records and required preprocessing before analysis.

---

## Step 1 — Load Data

- Imported dataset into Power BI Desktop.
- Verified and adjusted column data types.

---

## Step 2 — Data Cleaning

- Removed blank/null values where necessary.
- Corrected data types:

  - Date → Date format  
  - Runs and Extras → Whole numbers  

- Standardized column naming for consistency.

---

## Step 3 — Created Calculated Columns

New calculated columns were created to enable analysis.

### Total Runs Column

```
Total Runs = runs + extras
```

Purpose:

- Combine runs scored with extras into one metric.

---

### Ball Count Column

```
Ball_Count = 1
```

Purpose:

- Used to calculate total balls faced/bowled.

---

### Is Wicket Column

```
Is_Wicket =
IF(player_dismissed <> BLANK(), 1, 0)
```

Purpose:

- Identify wicket events for aggregation.

---

### Over Number Column

```
Over = INT(ball)
```

Purpose:

- Extract over number from ball value for over-wise analysis.

---

# 📐 DAX Measures Created

## Total Runs

```
Total Runs =
SUM(Test[Total Runs])
```

---

## Total Balls

```
Total Balls =
SUM(Test[Ball_Count])
```

---

## Total Wickets

```
Total Wickets =
SUM(Test[Is_Wicket])
```

---

## Run Rate

```
Run Rate =
DIVIDE([Total Runs], [Total Balls]) * 6
```

---

## Strike Rate

```
Strike Rate =
DIVIDE([Total Runs], [Total Balls]) * 100
```

---

# 🎛 Slicer Implementation

- Added slicers for:

  - Year
  - Venue
  - Batting Team
  - Bowling Team

- Enabled multi-selection for flexible analysis.
- Synced slicers across all dashboard pages.

Purpose:

- Allow dynamic filtering and comparison across different match scenarios.

---

# 🎨 Dashboard Design Approach

- Multi-page analytical layout.
- Different theme styling per page:

  - Overview → Executive style
  - Batting → Aggressive visual theme
  - Bowling → Tactical strategic theme

- Consistent spacing and alignment.
- Interactive filtering enabled across visuals.

---

# 📸 Dashboard Screenshots

## Overview Page

![Overview](Screenshots/Overview.png)

## Batting Analysis

![Batting](Screenshots/Batting.png)

## Bowling Analysis

![Bowling](Screenshots/Bowling.png)

---

# 🛠 Tools & Technologies

- Power BI Desktop
- DAX
- Data Modeling
- Data Visualization
- Git & GitHub

---

# 📂 Dataset

Dataset excluded due to GitHub file size limits.  
Available upon request.

---

# 🚀 Future Improvements

- Player-level analytics
- Advanced performance metrics
- Predictive trend analysis

---

# 👨‍💻 Author

Swaroop  
MCA Student | Data Analytics Enthusiast
