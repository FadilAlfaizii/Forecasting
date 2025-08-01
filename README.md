Time Series Forecasting

A comprehensive time series analysis and forecasting project implementing multiple advanced techniques for sales prediction using retail dataset.

## 🎯 Project Overview

This project demonstrates end-to-end time series analysis and forecasting capabilities through:
- **Data preprocessing** and exploratory analysis
- **Time series decomposition** using STL method
- **Feature engineering** with temporal and holiday features
- **Advanced forecasting** using SARIMAX and Prophet models
- **Interactive visualizations** with Plotly
- **Model comparison** and performance evaluation

## 📁 Project Structure

```
├── Forecasting.ipynb          # Main analysis notebook
├── data.xls                   # Raw retail dataset
├── new_timesries.ipynb        # Additional time series experiments
├── TimeSeries.html            # HTML export of analysis
└── README.md                  # This file
```

## 🔧 Technologies & Libraries

- **Data Processing:** `pandas`, `numpy`
- **Statistical Analysis:** `statsmodels`, `pmdarima`
- **Forecasting:** `Prophet`, `SARIMAX`
- **Visualization:** `plotly`, `seaborn`, `matplotlib`
- **Machine Learning:** `scikit-learn`

## 📈 Analysis Components

### 1. Data Loading & Exploration (Easy)
- Load dataset from Excel file (9,994 rows × 21 columns)
- Basic data preview and structure analysis
- Descriptive statistics generation

### 2. Summary Statistics (Easy)
- Comprehensive statistical overview
- Data type identification
- Initial data quality assessment

### 3. Missing Value Analysis (Medium)
- Systematic missing data evaluation
- Heatmap visualization of null values
- Data completeness assessment

### 4. Time Series Decomposition (Medium)
- **STL Decomposition** (Seasonal and Trend decomposition using Loess)
- Separation into trend, seasonal, and residual components
- Weekly aggregation with 52-week seasonal period
- Interactive visualization of decomposed components

**Key Insights from Decomposition:**
- Clear positive long-term growth trend
- Strong annual seasonality with year-end peaks
- Seasonal patterns indicating holiday-driven sales spikes

### 5. Feature Engineering (Medium)
- **Temporal Features:** day, weekday, month, weekend indicators
- **Holiday Features:** Black Friday, Christmas, Easter week indicators
- **Business Context:** Integration of discount and quantity metrics

### 6. SARIMAX Forecasting (Hard)
- **Automated parameter selection** using `auto_arima`
- **Exogenous variables** integration (quantity, discount, holidays)
- **Model:** SARIMAX(0,0,0)x(0,0,0)[52] - optimized for external features
- **Performance:** MAE: $4,215.85, MAPE: 34.93%

**Key Finding:** Model relies heavily on exogenous variables rather than ARIMA components, indicating that business features effectively capture temporal patterns.

### 7. Prophet Forecasting (Hard)
- **Meta's Prophet** implementation with holiday effects
- **Custom holiday definitions** (Black Friday, US holidays)
- **Multiple regressors** (quantity, discount, month)
- **Performance:** MAE: $4,399.99, MAPE: 35.51%

**Components Analysis:**
- Automatic trend change detection
- Significant holiday impact identification
- Clear yearly seasonality patterns
- Robust handling of missing data and outliers

## 🏆 Model Performance Comparison

| Model | MAE (Mean Absolute Error) | MAPE (Mean Absolute Percentage Error) |
|-------|---------------------------|----------------------------------------|
| **SARIMAX** | $4,215.85 | 34.93% |
| **Prophet** | $4,399.99 | 35.51% |

Both models demonstrate competitive performance with similar accuracy levels, validating the effectiveness of the feature engineering approach.

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn plotly
pip install statsmodels pmdarima prophet scikit-learn
pip install openpyxl  # for Excel file reading
```

### Running the Analysis
1. Clone this repository
2. Ensure `data.xls` is in the project directory
3. Open `Forecasting.ipynb` in Jupyter Notebook/Lab
4. Run cells sequentially from top to bottom

### Key Execution Notes
- Data is automatically resampled to weekly frequency
- All visualizations are interactive (Plotly-based)
- Models include 80/20 train-test split
- Holiday effects are specifically modeled for US retail context

## 📊 Key Visualizations

- **STL Decomposition:** Interactive 4-panel view of trend, seasonal, and residual components
- **Forecast Plots:** Comparative visualization of actual vs. predicted values with confidence intervals
- **Component Analysis:** Prophet's breakdown of trend, seasonality, and holiday effects
- **Missing Data Heatmap:** Visual assessment of data completeness

## 🔍 Technical Highlights

### Advanced Techniques Used:
1. **STL Decomposition** over classical seasonal decomposition for robustness
2. **Automated hyperparameter tuning** with pmdarima's auto_arima
3. **Multi-variate forecasting** incorporating business context
4. **Holiday effect modeling** with custom business calendar
5. **Interactive visualization** for better insight communication

### Business Intelligence:
- Identification of peak sales periods (year-end holidays)
- Quantification of promotional impact (Black Friday)
- Trend analysis revealing business growth patterns
- Seasonal adjustment for better planning

## 📝 Future Enhancements

- [ ] Implementation of ensemble forecasting methods
- [ ] Integration of external economic indicators
- [ ] Real-time forecasting pipeline development
- [ ] Deep learning approaches (LSTM, Transformer)
- [ ] Anomaly detection and alerting system

## 🤝 Contributing

Feel free to contribute to this project by:
- Suggesting improvements to forecasting accuracy
- Adding new visualization techniques
- Implementing additional forecasting models
- Enhancing feature engineering approaches

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📧 Contact

**Muhammad Fadil Alfaizi**  
Student ID: 123450115  

For questions or collaboration opportunities, please reach out via GitHub issues.

---

*This project demonstrates practical application of time series forecasting in retail analytics, showcasing both statistical and machine learning approaches to predictive modeling.*
