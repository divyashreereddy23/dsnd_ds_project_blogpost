# StackOverflow Developer Salary Analysis

![Project Banner](https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80)

## 📊 Project Overview

This project analyzes salary patterns among software developers using machine learning techniques applied to the Stack Overflow Developer Survey data. 
By training predictive models on responses from 21,782 developers worldwide, we uncovered the key factors that drive compensation in the tech industry.

**Key Achievement**: Built a Gradient Boosting model that predicts developer salaries with 67.3% accuracy (R² = 0.673) and mean absolute error of $11,247.

## 🎯 Motivation

Understanding salary drivers in the tech industry helps developers make informed career decisions. This analysis answers four critical questions:

1. **What factors most significantly impact developer salaries?**
2. **What surprising patterns exist in developer compensation data?**
3. **How accurately can we predict salaries using survey data?**
4. **What career scenarios can we model using predictive analytics?**

## 📚 Libraries Used

```python
# Data Processing & Analysis
pandas>=1.5.0
numpy>=1.24.0

# Machine Learning
scikit-learn>=1.2.0

# Visualization
matplotlib>=3.6.0
seaborn>=0.12.0

# Utilities
joblib>=1.2.0
scipy>=1.10.0
```

## 📁 Repository Structure

```
stackoverflow-salary-analysis/
│
├── data/
│   ├── survey_results_public.csv          # Raw StackOverflow survey data
│   ├── stackoverflow_salary_clean.csv     # Cleaned dataset
│   └── stackoverflow_features_engineered.csv  # Final feature-engineered dataset
│
├── notebooks/
│   ├── 01_initialchecks.ipynb             # Initial data exploration
│   ├── 02_feature_engineering.ipynb       # Feature engineering process
│   ├── 03_modeling.ipynb                  # Model training and evaluation
│   └── 04_tailoredanalysis.ipynb          # Creative scenario analysis
│
├── models/
│   ├── best_model_gradient_boosting.pkl   # Trained final model
│   ├── feature_scaler.pkl                 # Feature scaling transformer
│   └── model_summary.json                 # Model performance summary
│
├── results/
│   ├── model_comparison_results.csv       # Performance comparison across algorithms
│   ├── final_feature_importance.csv       # Feature importance rankings
│   ├── feature_engineering_summary.json   # Data processing log
│   └── visualizations/                    # Generated plots and charts
│
├── src/
│   ├── data_preprocessing.py              # Data cleaning functions
│   ├── feature_engineering.py             # Feature creation utilities
│   ├── model_training.py                  # Model training pipeline
│   └── scenario_analysis.py               # Prediction scenario functions
│
├── README.md
├── requirements.txt
└── .gitignore
```

## 🔍 Key Findings

### Most Important Salary Predictors

| Rank | Feature | Importance | Description |
|------|---------|------------|-------------|
| 1 | Geographic Location | 29.4% | Country/region frequency |
| 2 | Professional Experience | 17.8% | Years of coding professionally |
| 3 | Education Level | 9.5% | Degree type and level |
| 4 | Age | 8.2% | Developer age (career stage proxy) |
| 5 | Company Size | 6.3% | Organization employee count |
| 6 | Data Scientist Role | 5.1% | Specialized data science position |
| 7 | Engineering Manager | 4.4% | Management track premium |
| 8 | Python Expertise | 4.1% | Python programming skills |
| 9 | Experience Squared | 3.8% | Non-linear experience effects |
| 10 | DevOps Specialist | 3.5% | DevOps/infrastructure specialization |

### Surprising Insights

- **Data Scientists earn 23% more** than average developers
- **Python developers command 8% salary premium** over JavaScript developers
- **Geographic location matters more than company size** (29% vs 6% importance)
- **Engineering managers earn only 15% more** than senior individual contributors
- **Remote work geography arbitrage** can provide $18,000 purchasing power advantage

## 📈 Model Performance

### Algorithm Comparison

| Model | R² Score | MAE ($) | RMSE ($) | CV Mean | CV Std |
|-------|----------|---------|----------|---------|---------|
| **Gradient Boosting** | **0.673** | **11,247** | **17,892** | **0.669** | **0.021** |
| Random Forest | 0.647 | 11,823 | 18,456 | 0.641 | 0.018 |
| Extra Trees | 0.639 | 12,156 | 18,723 | 0.635 | 0.019 |
| Ridge Regression | 0.592 | 12,891 | 19,734 | 0.588 | 0.025 |
| Lasso Regression | 0.588 | 13,045 | 19,891 | 0.583 | 0.028 |

### Performance Interpretation

- **67.3% of salary variance explained** - Excellent for salary prediction
- **$11,247 average prediction error** - 18.2% of median salary
- **Stable cross-validation performance** - Model generalizes well to new data
- **Gradient Boosting optimal** - Best balance of accuracy and generalization

## 🎭 Creative Scenario Analysis

### Scenario 1: Career Switcher Paths
**Profile**: 28-year-old bootcamp graduate in Austin, TX
- **Frontend Developer**: $59,000 ± $11,247
- **Backend Python Developer**: $63,500 ± $11,247  
- **Full-Stack Developer**: $59,500 ± $11,247

**Insight**: Backend Python offers $4,500 premium for career switchers

### Scenario 2: Remote Work Geography
**Profile**: 5-year experienced developer, different locations
- **San Francisco**: $107,000 (but lower purchasing power)
- **Austin**: $94,000 (balanced cost/salary ratio)
- **Rural Montana**: $77,000 (highest purchasing power: ~$95,000 equivalent)

**Insight**: Geographic arbitrage worth $18,000 in real purchasing power

### Scenario 3: Technology Investment ROI
**Profile**: 3-year JavaScript developer learning new skills
- **Data Science Transition**: +35.4% salary increase ($24,080)
- **DevOps Specialization**: +25.3% salary increase ($17,200)
- **Senior Frontend Path**: +35.3% salary increase (over 2-4 years)

**Insight**: Data science and DevOps offer fastest salary growth

## 🚀 How to Reproduce This Analysis

### 1. Environment Setup
```bash
# Clone the repository
git clone https://github.com/divyashreereddy23/stackoverflow-salary-analysis.git
cd stackoverflow-salary-analysis

# Install dependencies
pip install -r requirements.txt
```

### 2. Data Preparation
```bash
# Download StackOverflow Developer Survey data
# Visit: https://insights.stackoverflow.com/survey
# Place survey_results_public.csv in data/ folder
```

### 3. Run Analysis Pipeline
```bash
# Execute notebooks in order:
jupyter notebook notebooks/01_data_exploration.ipynb
jupyter notebook notebooks/02_feature_engineering.ipynb
jupyter notebook notebooks/03_modeling_analysis.ipynb
jupyter notebook notebooks/04_scenario_predictions.ipynb
```

### 4. Model Training
```python
# Alternatively, run the complete pipeline:
python src/model_training.py
```

## 📊 Data Quality & Limitations

### Dataset Characteristics
- **Source**: Stack Overflow Developer Survey 2023
- **Sample Size**: 21,782 developers with salary data
- **Geographic Coverage**: Global, with US/Europe emphasis
- **Response Rate**: ~35% salary disclosure rate

### Model Limitations
- **Geographic Bias**: Overrepresentation of US/European developers
- **Self-Selection**: Survey respondents may not represent entire developer population
- **Temporal Scope**: Reflects 2023 market conditions
- **Experience Range**: Most accurate for 1-15 years experience
- **Currency Normalization**: All salaries converted to USD equivalent

### Confidence Intervals
All salary predictions include ±$11,247 confidence interval reflecting model uncertainty.

## 🎯 Business Applications

### For Individual Developers
- **Career Path Planning**: Compare salary potential across specializations
- **Skill Investment**: Identify highest-ROI technology learning opportunities
- **Geographic Strategy**: Optimize location for salary/cost-of-living balance
- **Negotiation Data**: Benchmark current compensation against market predictions

### For Organizations
- **Compensation Benchmarking**: Market-rate salary setting
- **Talent Acquisition**: Competitive offer structuring
- **Retention Analysis**: Identify flight-risk compensation gaps
- **Skills Gap Planning**: ROI analysis for team upskilling investments

## 🔬 Technical Methodology

### Data Processing Pipeline
1. **Data Cleaning**: Outlier removal, missing value imputation
2. **Feature Engineering**: Categorical encoding, interaction features
3. **Feature Selection**: Variance thresholding, importance-based selection
4. **Model Training**: Hyperparameter tuning with 3-fold cross-validation
5. **Evaluation**: Multiple metrics, residual analysis, learning curves

### Model Architecture
- **Algorithm**: Gradient Boosting Regressor
- **Features**: 156 engineered features from 182 original survey questions
- **Hyperparameters**: Learning rate: 0.15, Max depth: 5, Estimators: 200
- **Validation**: 3-fold cross-validation with temporal split consideration

## 📝 Future Improvements

- **Temporal Analysis**: Multi-year trend modeling
- **Deep Learning**: Neural network architecture exploration
- **Ensemble Methods**: Model stacking for improved accuracy
- **Causal Inference**: Beyond correlation to causal relationships
- **Real-time Updates**: Automated retraining pipeline

## 🙏 Acknowledgments

- **Stack Overflow**: For providing comprehensive developer survey data
- **Open Source Community**: scikit-learn, pandas, and visualization libraries
- **Data Science Community**: Methodological best practices and inspiration

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📧 Contact

- **Author**: Divyashree Reddy
- **Email**: divyashreereddy23@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/divyashree-reddy 
- **Blog Post**: 

---
