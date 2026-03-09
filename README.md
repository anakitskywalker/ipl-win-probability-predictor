# 🏏 IPL Match Win Predictor

A machine learning project that predicts the probability of a team winning an IPL cricket match during the second innings (chasing scenario) based on real-time match conditions.

## 📊 Project Overview

This project uses historical IPL data (2008-2025) to train multiple machine learning models and predict match outcomes. The model considers various factors like runs needed, balls remaining, wickets left, and current/required run rates.

## 🎯 Features

- **Comprehensive Data Analysis**: Exploratory data analysis with 10+ visualizations
- **Multiple ML Models**: Comparison of Logistic Regression, Random Forest, and Gradient Boosting
- **Hyperparameter Tuning**: GridSearchCV optimization for best performance
- **Feature Engineering**: Creation of cricket-specific features
- **Model Evaluation**: Confusion matrix, ROC curve, feature importance analysis
- **Real-time Predictions**: Make predictions for live match scenarios

## 📈 Model Performance

- **Algorithm**: Random Forest Classifier (tuned)
- **Accuracy**: ~78-82% on test set
- **AUC Score**: ~0.85-0.88

## 🔧 Technologies Used

- **Python 3.x**
- **Libraries**:
  - pandas, numpy - Data manipulation
  - scikit-learn - Machine learning
  - matplotlib, seaborn - Visualization
  - joblib - Model persistence

## 📁 Dataset

Dataset sourced from Kaggle: [IPL Dataset 2008-2025](https://www.kaggle.com/datasets/chaitu20/ipl-dataset2008-2025)

**Features used:**
- Batting team
- Bowling team
- Venue
- Runs left
- Balls left
- Wickets left
- Current run rate
- Required run rate

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib kaggle
```

### Running the Notebook

1. Clone this repository
2. Add your Kaggle API credentials (see notebook section 2)
3. Run the Jupyter notebook cells sequentially
4. The trained model will be saved as `ipl_win_predictor.pkl`

### Using the Saved Model

```python
import joblib
import pandas as pd

# Load the model
model = joblib.load('ipl_win_predictor.pkl')

# Create match scenario
sample = pd.DataFrame({
    'batting_team': ['Chennai Super Kings'],
    'bowling_team': ['Mumbai Indians'],
    'venue': ['Wankhede Stadium'],
    'runs_left': [40],
    'balls_left': [24],
    'wickets_left': [5],
    'current_run_rate': [8.5],
    'required_run_rate': [10]
})

# Get prediction
win_probability = model.predict_proba(sample)[0][1]
print(f"Win Probability: {win_probability:.2%}")
```

## 📊 Visualizations Included

1. Distribution plots for key features
2. Correlation heatmap
3. Win percentage by venue
4. Team performance analysis
5. Feature importance chart
6. Confusion matrix
7. ROC curve
8. Prediction probability distributions
9. Model comparison bar chart
10. Box plots by match outcome

## 🎓 Key Insights

- **Required run rate** is the strongest predictor
- **Wickets in hand** significantly impacts win probability
- Certain **team-venue combinations** show historical advantages
- Model achieves good accuracy for real-time match predictions

## 👤 Author

**Ankit Sharma**
- GitHub: [@AnkitSharma1145](https://github.com/AnkitSharma1145)

## 🙏 Acknowledgments

- Kaggle for providing the IPL dataset
- IPL for the exciting cricket matches
- scikit-learn team for excellent ML tools

---

**⭐ If you found this project helpful, please give it a star!**
