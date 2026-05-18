# 🍽️ Zomato Restaurant Analysis

> **Exploratory Data Analysis (EDA) of Zomato restaurant data to uncover patterns in ratings, costs, ordering behaviour, and popularity using structured analysis and clear visualisations.**

---

## 📑 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Installation & Setup](#installation--setup)
- [Analysis Walkthrough](#analysis-walkthrough)
- [Key Findings](#key-findings)
- [Visualisations](#visualisations)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This project performs a comprehensive exploratory data analysis on the **Zomato restaurant dataset** to answer questions like:

- Do restaurants that accept online orders get better ratings?
- Does price correlate with quality?
- Which restaurant types attract the most votes?
- How does table booking affect customer perception?
- What does the distribution of restaurant ratings look like across Bangalore?

The notebook is structured in **13 clearly labelled sections** — from raw data ingestion through cleaning, feature engineering, visual analysis, and a final insights summary.

---

## Dataset

| Property | Detail |
|---|---|
| **File** | `Zomato-data.csv` |
| **Source** | Zomato restaurant listings |
| **Rows** | ~148 restaurant records |
| **Key Columns** | `name`, `rate`, `votes`, `online_order`, `book_table`, `rest_type`, `approx_cost(for two people)`, `listed_in(type)` |

> ⚠️ **Note:** Place `Zomato-data.csv` in the same directory as the notebook before running.

### Raw Data Challenges Addressed

- `rate` stored as strings (e.g., `"4.1/5"`, `"NEW"`, `"-"`) — parsed and null-filled with the median
- `approx_cost` contained comma-formatted numbers (e.g., `"1,200"`) — cleaned to numeric
- Column names with special characters renamed for convenience

---

## Project Structure

```
zomato-analysis/
│
├── Zomato_Project_Enhanced.ipynb   # Main analysis notebook
├── Zomato-data.csv                 # Raw dataset (download separately)
└── README.md                       # This file
```

---

## Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, aggregation |
| `numpy` | Numerical operations & missing value handling |
| `matplotlib` | Core plotting (histograms, bar charts, scatter) |
| `seaborn` | Statistical visualisations (violin, box, heatmap) |
| `GridSpec` | Complex multi-panel figure layouts |

**Python version:** 3.8+

---

## Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/zomato-analysis.git
cd zomato-analysis
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Or use the requirements file if provided:

```bash
pip install -r requirements.txt
```

### 4. Launch the notebook

```bash
jupyter notebook Zomato_Project_Enhanced.ipynb
```

---

## Analysis Walkthrough

The notebook is divided into **13 sequential sections**:

| # | Section | Description |
|---|---|---|
| 1 | **Imports & Global Style** | Library setup, custom colour palette, Seaborn theme |
| 2 | **Load Data** | Read CSV, inspect shape and first rows |
| 3 | **Initial Exploration** | Data types, missing values, duplicate detection |
| 4 | **Data Cleaning** | Parse messy `rate` strings (`"4.1/5"`, `"NEW"`), clean comma-formatted costs, create boolean flags |
| 5 | **Statistical Summary** | Descriptive stats for `rate`, `votes`, and `cost_for_two` |
| 6 | **Distribution Overview** | Restaurant type counts, rating histogram, cost KDE |
| 7 | **Online Order Analysis** | Availability pie chart, rating violin plot, type × order heatmap |
| 8 | **Rating Bands & Cost Segments** | Segmented bar charts using derived categorical features |
| 9 | **Popularity (Votes) Analysis** | Top 10 restaurants, total votes by restaurant type |
| 10 | **Correlation & Scatter Analysis** | Cost vs Rating scatter coloured by delivery, correlation heatmap |
| 11 | **Aggregated Summary** | Group-by table: count, avg rating, avg cost, total votes, % online |
| 12 | **Table Booking Impact** | Box plot (rating) and bar chart (avg votes) split by booking status |
| 13 | **Final Insights** | Formatted key findings summary printed to console |

---

## Key Findings

```
╔══════════════════════════════════════════════════════════════════╗
║                    KEY FINDINGS SUMMARY                         ║
╠══════════════════════════════════════════════════════════════════╣
║  📊 Most Common Type  : Delivery (highest restaurant count)     ║
║  📱 Online Orders     : ~58% of restaurants offer online order  ║
║  ⭐ Avg Rating        : Online ≈ 3.93  |  Offline ≈ 3.69       ║
║  💰 Cost–Rating Corr  : Slight positive (+0.09)                 ║
║  🗳️  Votes–Rating Corr : Slight positive (+0.12)                ║
║  🏆 Table Booking     : Restaurants with booking → higher medians║
╚══════════════════════════════════════════════════════════════════╝
```

**Highlighted insights:**

- 🛵 **Online ordering restaurants** receive slightly higher average ratings (~3.93) compared to offline-only restaurants (~3.69), possibly driven by broader customer reach and review volume.
- 💸 **Cost and rating show a weak positive correlation** — price is not a reliable predictor of quality alone.
- 📚 **Table booking availability** is associated with higher median ratings and significantly higher average vote counts, suggesting table-booking venues attract more engaged diners.
- 🍽️ **Dining restaurants** dominate vote counts despite being outnumbered by delivery-type restaurants, indicating higher per-customer engagement.
- 📈 The majority of restaurants fall in the **"Good (3.5–4.0)"** rating band — very few restaurants score below 3 or above 4.5.

---

## Visualisations

The notebook generates **6 multi-panel figures** (18 individual charts):

| Figure | Charts Included |
|---|---|
| Distribution Overview | Restaurant types bar chart, Rating histogram, Cost KDE |
| Online Order Insights | Availability pie, Rating violin (online vs offline), Type × Order heatmap |
| Segmented Analysis | Rating band horizontal bar, Avg rating by cost segment |
| Votes & Popularity | Top 10 restaurants, Total votes by type (area line) |
| Relationships | Cost vs Rating scatter, Correlation heatmap |
| Table Booking Impact | Rating box plot, Avg votes bar chart |

All figures use a consistent theme:
- Background: `#F9F9F9`
- Accent colour: `#E63946`
- Palette: `viridis` / `RdYlGn` / `coolwarm` depending on context
- Spines off for a clean, modern look

---

## Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

Please follow PEP 8 style and add comments to any new analysis cells.

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

Made with ❤️ and lots of 🍛

</div>
