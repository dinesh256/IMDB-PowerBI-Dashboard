# 🎬 IMDB Movie Data — Power BI Dashboard
---

## 📌 Project Overview

This project is an interactive **Power BI Dashboard** built on **IMDB Movie Data** to explore and analyze the film industry through data. The dashboard provides actionable insights into movie trends, genre performance, top-rated films, and advanced analytics — all in a visually compelling and easy-to-navigate interface.

The goal is to help users understand:
- How the movie industry has evolved over the decades
- Which genres consistently perform best
- Who the top directors and actors are
- What factors correlate with high ratings and box office success

---

## 🗂️ Dataset

- **Source:** IMDB Movie Dataset (5,000+ movies)
- **Fields Used:** Title, Genre, Release Year, Rating, Votes, Director, Cast, Budget, Box Office Revenue, Runtime, Language

---

## 📊 Dashboard Sections

### 1. 🌍 Overview & Trends
- Total movies, average rating, total votes, and average runtime — displayed as KPI cards
- Release trends over the years shown via a line chart
- Revenue growth across decades using a bar chart
- Average ratings over time to track quality shifts in the industry

### 2. 🎭 Genre & Rating Analysis
- Average ratings and vote counts broken down by genre using DAX measures
- Clustered bar chart comparing genres side by side
- Donut chart for genre distribution across the dataset
- Identifies top-performing genres and least popular categories

### 3. 🏆 Top Performers
- Top 10 highest-rated movies with vote count validation
- Top 10 highest-grossing films at the box office
- Most prolific directors by number of movies and average rating
- Most featured actors ranked by appearances and audience ratings
- Dynamic slicers for Year, Genre, Language, and Rating filters

### 4. 📈 Advanced Analytics
- **Budget vs. Box Office Revenue** correlation scatter plot
- **Rating Distribution** histogram to understand audience scoring patterns
- Drill-through pages for deep-diving into individual movie details
- Calculated columns for profit margin and ROI per film
- Trend lines and forecasting on revenue and rating metrics

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard design and visualization |
| **DAX (Data Analysis Expressions)** | Custom measures and calculated columns |
| **SQL** | Data extraction and preprocessing |
| **Excel** | Initial data cleaning and formatting |

---

## 🔑 Key DAX Measures Used

```dax
-- Average Rating by Genre
Avg Rating by Genre = CALCULATE(AVERAGE(Movies[Rating]), ALLEXCEPT(Movies, Movies[Genre]))

-- Total Box Office Revenue
Total Revenue = SUM(Movies[BoxOfficeRevenue])

-- Profit Margin %
Profit Margin = DIVIDE([Total Revenue] - SUM(Movies[Budget]), SUM(Movies[Budget]), 0) * 100

-- Top Rated Movies (Rating > 8)
Top Rated Count = CALCULATE(COUNTROWS(Movies), Movies[Rating] >= 8)
```

---

## 💡 Key Insights Discovered

- **Drama** and **Documentary** genres consistently achieve the highest average ratings
- Movies released between **1990–2010** show the strongest box office revenue growth
- Higher production budgets show a **moderate positive correlation** with box office revenue but not with ratings
- **Christopher Nolan** and **Steven Spielberg** appear among the top directors by both rating and revenue
- Most movies fall within the **6.5–7.5 rating range**, showing audience scoring tendencies

---

## 📁 Project Structure

```
imdb-powerbi-dashboard/
│
├── data/
│   └── imdb_movies_cleaned.xlsx       # Cleaned dataset used in the dashboard
│
├── dashboard/
│   └── IMDB_Dashboard.pbix            # Power BI dashboard file
│
├── screenshots/
│   ├── overview_trends.png            # Overview & Trends page
│   ├── genre_rating_analysis.png      # Genre & Rating Analysis page
│   ├── top_performers.png             # Top Performers page
│   └── advanced_analytics.png        # Advanced Analytics page
│
└── README.md
```

---

## 🚀 How to Open the Dashboard

1. Download and install **[Power BI Desktop](https://powerbi.microsoft.com/desktop/)** (free)
2. Clone this repository:
   ```bash
   git clone https://github.com/dineshkumar2512/imdb-powerbi-dashboard.git
   ```
3. Open the `IMDB_Dashboard.pbix` file in Power BI Desktop
4. Refresh the data source if prompted
5. Explore the dashboard using the slicers and filters!

---
