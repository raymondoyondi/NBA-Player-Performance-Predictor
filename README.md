# NBA Player Performance Predictor

An end-to-end data science pipeline that leverages historical NBA data to forecast player statistics for upcoming seasons. This project integrates automated data scraping, feature engineering, and advanced regression modeling to power an interactive visualization dashboard.

---

## 🚀 Overview

Predicting athletic performance is a complex challenge influenced by aging, team dynamics, and historical trends. The **NBA Player Performance Predictor** addresses this by analyzing over a decade of league data to provide actionable insights for fans, analysts, and fantasy basketball enthusiasts.

### Key Features
* **Automated Data Pipeline:** Scrapes and cleans player-per-game stats, advanced metrics, and team standings.
* **Feature Engineering:** Calculates rolling averages, career trajectories, and age-based performance curves.
* **Multi-Model Comparison:** Evaluates Linear Regression, Random Forest, and Gradient Boosting (XGBoost) models.
* **Web Dashboard:** An interactive interface to visualize individual player projections and "what-if" scenarios.

---

## 🛠️ Tech Stack

| Category | Tools/Libraries |
| :--- | :--- |
| **Language** | Python 3.9+ |
| **Data Processing** | Pandas, NumPy, BeautifulSoup4 |
| **Machine Learning** | Scikit-Learn, XGBoost, CatBoost |
| **Visualization** | Matplotlib, Seaborn, Plotly, Streamlit |
| **DevOps/Env** | Jupyter, Git, Docker |

---

## 📊 Data Pipeline & Methodology

The project follows a rigorous data science lifecycle to ensure predictions are both accurate and explainable.



### 1. Data Acquisition
Data is sourced from reputable sports databases (e.g., Basketball-Reference) using `BeautifulSoup`. 
* **Player Stats:** Points, Assists, Rebounds, Steals, Blocks.
* **Efficiency Metrics:** PER (Player Efficiency Rating), True Shooting %, Usage Rate.
* **Contextual Data:** Team wins, minutes played, and injury history.

### 2. Preprocessing & Feature Engineering
Raw data is rarely ready for modeling. This stage includes:
* **Handling Nulls:** Addressing players with limited minutes or missing advanced stats.
* **Lag Features:** Creating "Previous Season" columns to establish temporal context ($t-1$, $t-2$).
* **Aging Curves:** Normalizing stats based on a player's age to account for physical peaks and declines.
* **Scaling:** Using `StandardScaler` to ensure feature weights are balanced.

### 3. Modeling
We frame the prediction as a **Regression Task**. The primary objective is to minimize the difference between predicted and actual stats.

The primary loss function used is **Mean Squared Error (MSE)**:
$$MSE = \frac{1}{n} \sum_{i=1}^{n} (Y_i - \hat{Y}_i)^2$$

Where:
* $Y_i$ is the actual stat (e.g., PPG in 2024).
* $\hat{Y}_i$ is the predicted stat.

---

## 📈 Performance Analysis

Our models are evaluated using R-Squared ($R^2$) and MAE (Mean Absolute Error). 

| Model | MAE (Points) | $R^2$ Score | Best For |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | 2.4 | 0.81 | Baseline / Steady Veterans |
| **Random Forest** | 1.9 | 0.88 | Capturing Non-linear Growth |
| **XGBoost** | 1.7 | 0.91 | Highest Overall Accuracy |

> **Note:** Models show high accuracy for veteran players with stable career arcs, while rookie projections focus more on collegiate translation metrics and draft position.

---

## ⚙️ Installation & Usage

### Prerequisites
* Python 3.8+
* Virtual Environment (recommended)

### Setup
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/raymondoyondi/NBA-Player-Performance-Predictor.git](https://github.com/raymondoyondi/NBA-Player-Performance-Predictor.git)
    cd NBA-Player-Performance-Predictor
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

### Running the Project
* **To scrape fresh data:**
    ```bash
    python src/data_scraper.py
    ```
* **To train the models:**
    ```bash
    python src/train_model.py
    ```
* **To launch the dashboard:**
    ```bash
    streamlit run app/main.py
    ```

---

## 🗺️ Roadmap
- [ ] Add support for "Playoff Intensity" multipliers.
- [ ] Integrate Twitter/X sentiment analysis to account for trade rumors.
- [ ] Expand the dashboard to include team-level win-total predictions.
- [ ] Deploy the app using AWS EC2 or Heroku.

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
