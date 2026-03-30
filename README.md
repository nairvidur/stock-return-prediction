# Stock Return Prediction — FA 590

**Statistical Learning in Finance | Stevens Institute of Technology | Spring 2025**  
**Team:** Hitanshu Reddy, Vidur, Vasil

---

## Project Summary

Built and evaluated machine learning models to predict monthly stock-level returns using 13 years of equity data (2009–2021) from the Compustat database. Compared Linear Regression, Random Forest, and Neural Network models on both predictive accuracy and portfolio performance.

---

## Results

### Predictive Performance (Out-of-Sample)

| Model             | RMSE   | MAE    | R²      |
|-------------------|--------|--------|---------|
| Linear Regression | 0.2185 | 0.1083 | 0.0329  |
| Random Forest     | 0.2287 | 0.1155 | -0.0587 |
| Neural Network    | 0.2225 | 0.1126 | -0.0025 |

### Portfolio Performance

| Model             | Avg Monthly Return | Volatility | Sharpe Ratio |
|-------------------|--------------------|------------|--------------|
| Linear Regression | 2.97%              | 0.2209     | 0.134        |
| Random Forest     | 1.76%              | 0.2222     | 0.079        |
| Neural Network    | 1.34%              | 0.2225     | 0.060        |

**Linear Regression achieved the best performance on both predictive accuracy and portfolio metrics.**

---

## Files

| File | Description |
|------|-------------|
| `final-project-vhv (2) (2).ipynb` | Main notebook — full pipeline from EDA to model evaluation |
| `FA590_FinalProject_corrected.pdf` | Written report with corrected evaluation metrics |
| `README.md` | This file |

> The dataset (`return_predictability_data_2009to2021.csv`) is not included — proprietary course data from Stevens Institute.

---

## Methodology

- **Data:** ~890K observations, 107 features, 2009–2021 subsample
- **Feature Selection:** Correlation-based filtering (threshold = 0.03) → 8 features selected: `macro_tms`, `macro_svar`, `macro_ep`, `baspread`, `macro_dfy`, `retvol`, `maxret`, `macro_tbl`
- **Train/Test Split:** Chronological 80/20 split (~2009–2018 train, 2019–2021 test)
- **Models:** Linear Regression, Random Forest (100 trees), Neural Network (MLP 64→32)
- **Portfolio:** Sign-based strategy on predicted returns, evaluated by Sharpe Ratio

---

## How to Run

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

Place `return_predictability_data_2009to2021.csv` in the same directory as the notebook, then run all cells top to bottom in Jupyter.

---

## Course

FA 590 — Statistical Learning in Finance, Stevens Institute of Technology, Spring 2025
