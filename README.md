# Driver-Based Revenue Forecasting with Statistical & Machine Learning Models

**Business-ready forecasting framework leveraging historical revenue data and macroeconomic indicators to improve planning accuracy for mid-market, private equity-backed companies.**

---

## 📌 Executive Overview
This project demonstrates a structured approach to **monthly revenue forecasting**, starting with statistical baselines, adding macroeconomic drivers, and comparing manual machine learning models against AutoML-selected approaches.

The goal is to help finance and operations leaders make **better-informed budgeting, staffing, and capital allocation decisions** by improving forecast accuracy and interpretability.

---

## 💼 Business Context & Value
For mid-market, PE-backed businesses with $50–150M in annual revenue, accurate forecasts can:
- Improve **cash flow management** and debt servicing.
- Align **budgeting** and **resource planning** with realistic revenue expectations.
- Enable **scenario analysis** to prepare for both market headwinds and growth opportunities.

This framework:
- Benchmarks multiple modeling approaches (statistical & ML).
- Highlights when **simpler statistical models** may outperform complex ML.
- Demonstrates the role of **AutoML** in finding optimal models and hyperparameters.

---

## 🛠 Approach

1. **Data Preparation**
   - Load & clean historical financial data.
   - Load, align, and prepare macroeconomic indicators from FRED.
   - Merge datasets and engineer time series features.

2. **Modeling Stages**
   - **Statistical Baselines** – ARIMA, SARIMAX (financial data only).
   - **Machine Learning Baseline** – Gradient Boosted Trees with feature engineering.
   - **AutoML** – PyCaret to test multiple models with optimized hyperparameters.

3. **Evaluation**
   - Metrics: MAPE, MAE, RMSE, R².
   - Business interpretation of each metric.
   - Selection based on lowest MAPE and stable performance.

---

## 📊 Key Results
| Model        | MAPE   | MAE       | RMSE      | R²     |
|--------------|--------|-----------|-----------|--------|
| PyCaret stlf | 0.81%  | 79,891    | 94,662    | 0.709  |
| SARIMAX      | 2.60%  | 252,857   | 468,868   | 0.067  |
| GBT          | 3.12%  | 313,418   | 406,035   | 0.497  |
| ARIMA        | 6.85%  | 708,584   | 767,430   | -2.071 |

**Business Takeaway:**  
- SARIMAX provided a highly reliable forecast using only historical revenue trends.
- GBT added some value over ARIMA but did not surpass SARIMAX.
- PyCaret’s STLForecaster delivered the best performance, showing the potential of AutoML for complex searches and fine-tuning.

---

## 📂 Repository Structure
```

├── DriverFcst\_Final\_202508.ipynb   # Notebook with full analysis & commentary
├── requirements\_driverfcst.txt     # Python dependencies
├── environment\_driverfcst.yml      # Conda environment file
├── README.md                       # This file
└── synthetic\_financial\_data        # Input dataset

````

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/driver-based-forecast.git
   cd driver-based-forecast
   ```

2. **Create the environment**
   Using conda:

   ```bash
   conda env create -f environment_driverfcst.yml
   conda activate driverfcst
   ```

   Using pip:

   ```bash
   pip install -r requirements_driverfcst.txt
   ```

3. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook DriverFcst_Final_202508.ipynb
   ```

4. **Run All Cells**

   * Open the notebook in Jupyter.
   * Select `Kernel > Restart & Run All` to execute the analysis from start to finish.

```