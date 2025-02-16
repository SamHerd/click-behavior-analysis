# Click Behavior Analysis & Ad ROI Prediction

## Overview
This project analyzes customer click behavior and predicts purchase likelihood using a Neural Network Multi-Task Learning (MTL) model. Additionally, an Ad Spend ROI Prediction model, implemented using XGBoost, helps optimize marketing budget allocation. The project also includes a Power BI dashboard for visualization and a KMeans segmentation script for clustering users based on behavior.

## Repository Structure
- **models/**: Contains the trained models and scripts for inference.
- **data/**: Reference datasets used for training and evaluation.
- **dashboard/**: Power BI dashboard files.
- **requirements.txt**: List of dependencies.

## Models
### 1. Multi-Task Learning (MTL) Neural Network for Drop-Off Analysis
#### **How It Works**
- This model predicts two key metrics:
  1. **Click-to-Conversion Efficiency** – likelihood that a click leads to a conversion.
  2. **Click Drop-Off Probability** – probability of a user abandoning the session after a click.
- Implemented using a multi-task learning approach to optimize both objectives simultaneously.
- Uses behavioral features such as click sequences, time-on-page, and previous interactions.

#### **Key Insights**
- Users with multiple interactions across sessions tend to have higher conversion probabilities.
- High drop-off rates are associated with specific product categories and pages.

#### **Shortcomings**
- The model performs well on past data but struggles with extreme behavior shifts (e.g., seasonal effects).
- The dataset lacks detailed timestamp data, limiting session-based insights.

### 2. Ad Spend ROI Prediction (XGBoost Regression Model)
#### **How It Works**
- Predicts return on ad spend (ROAS) based on campaign data, user interactions, and conversion rates.
- Features include ad type, placement, engagement metrics, and historical performance.
- Uses XGBoost for its robustness against missing data and ability to handle nonlinear patterns.

#### **Key Insights**
- Certain ad types significantly outperform others in terms of ROAS.
- Targeted campaigns yield better conversion rates than broad-reach ads.

#### **Shortcomings**
- Model accuracy decreases for newer campaigns with minimal historical data.
- Does not account for external factors such as competitor actions or economic trends.

## Power BI Dashboard
### **How to Access & Use**
- The Power BI dashboard visualizes click behavior trends, conversion patterns, and ad spend efficiency.
- Includes interactive filters for date ranges, user segments, and campaign types.
- Key pages:
  - **Overview**: Summary of key metrics.
  - **Click Behavior Analysis**: Drop-off rates, conversion paths, and efficiency scores.
  - **Ad Spend Performance**: ROI analysis across different campaigns.
  - **Segmentation & Trends**: KMeans clusters and seasonal insights.

## KMeans Segmentation Script
### **How It Works**
- Uses behavioral clickstream data to cluster users into segments.
- Features include session length, frequency, and interaction depth.
- Helps identify high-value users and drop-off-prone groups.

## Drop-Off Calculation in Reference Datasets
- Drop-off is calculated as:
  \[ Drop-off \% = \frac{\text{Users Who Clicked But Did Not Convert}}{\text{Total Users Who Clicked}} \times 100 \]
- The dataset includes labeled sequences to track drop-off at different stages.

## Getting Started
### **Installation & Requirements**
- Python 3.8+
- Required packages: `pandas`, `numpy`, `tensorflow`, `xgboost`, `scikit-learn`

### **Running the Models**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/click-behavior-analysis.git
   cd click-behavior-analysis
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the MTL Neural Network model script:
   ```bash
   jupyter notebook models/Multi-Task Learning Neural Network Predictive Model.ipynb
   ```
4. Run the Ad ROI Prediction Model script:
   ```bash
   jupyter notebook models/Ad ROI Feature Importance Analysis.ipynb
   ```

### **Accessing the Dashboard**
- Open the `dashboard/ClickBehaviorDashboard.pbix` file in Power BI.
- Use slicers to filter data by date range, campaign, or user segment.

## Future Improvements
- Improve session tracking by incorporating timestamp data.
- Enhance the MTL model with reinforcement learning for adaptive decision-making.
- Expand the dataset with external market trend data to refine the Ad ROI model.

## Contact
For questions or collaboration opportunities, reach out via [LinkedIn](https://www.linkedin.com/in/yourprofile).

