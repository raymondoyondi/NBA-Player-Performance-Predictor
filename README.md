# NBA Player Performance Predictor

An end-to-end data science pipeline that leverages historical NBA data to forecast player statistics for upcoming seasons. This project integrates automated data scraping, feature engineering, and advanced regression modeling to power an interactive visualization dashboard.

---

## 🚀 Overview

Predicting athletic performance is a complex challenge influenced by aging, team dynamics, and historical trends. The **NBA Player Performance Predictor** addresses this by analyzing over a decade of league data to provide actionable insights for fans, analysts, and fantasy basketball enthusiasts.

### Key Features
* **Automated Data Pipeline:** Scrapes and cleans player-per-game stats, advanced metrics, and team standings.
* **Feature Engineering:** Calculates rolling averages, career trajectories, and age-based performance curves.
* **Multi-Model Comparison:** Evaluates Linear Regression, Random Forest, and Gradient Boosting (XGBoost) models.
* **Web Dashboard:** An interactive interface (built with Streamlit/Flask) to visualize individual player projections.

---

## 🛠️ Tech Stack

| Category | Tools/Libraries |
| :--- | :--- |
| **Language** | Python 3.9+ |
| **Data Processing** | Pandas, NumPy, BeautifulSoup4 |
| **Machine Learning** | Scikit-Learn, XGBoost |
| **Visualization** | Matplotlib, Seaborn, Plotly |
| **Environment** | Jupyter Notebooks, Git |

---

## 📊 Data Pipeline & Methodology

The project follows a rigorous data science lifecycle:

### 1. Data Acquisition
Data is sourced from reputable sports databases (e.g., Basketball-Reference) using `BeautifulSoup`. 
* **Player Stats:** Points, Assists, Rebounds, Steals, Blocks.
* **Efficiency Metrics:** PER, True Shooting %, Usage Rate.

### 2. Preprocessing & Engineering
Raw data is rarely ready for modeling. This stage includes:
* **Handling Nulls:** Addressing players with limited minutes or missing advanced stats.
* **Lag Features:** Creating "Previous Season" columns to establish temporal context.
* **Normalizing:** Scaling features to ensure model convergence.

### 3. Modeling
We frame the problem as a **Regression Task**.


The primary objective is to minimize **Mean Squared Error (MSE)** across core stats:
$$MSE = \frac{1}{n} \sum_{i=1}^{n} (Y_i - \hat{Y}_i)^2$$

---

## 📈 Performance Analysis

Current models show high accuracy for veteran players with stable career arcs, while rookie projections focus more on collegiate translation metrics.

* **Random Forest Regressor:** Best for capturing non-linear growth spurts.
* **Linear Regression:** Serves as a baseline for "steady-state" performance.

---

## ⚙️ Installation & Usage

### Prerequisites
* Python 3.8+
* Virtual Environment (recommended)

### Setup
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/raymondoyondi/NBA-Player-Performance-Predictor.git](https://github.com/raymondoyondi/NBA-Player-Performance-Predictor.git)
   cd NBA-Player-Performance-Predictor
