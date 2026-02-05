# Oil Well Location Optimization using Machine Learning

## Project Overview
This project develops a comprehensive machine learning solution for OilyGiant, an oil extraction company, to optimize the selection of drilling locations for 200 new oil wells. Using geological data from three regions, the system predicts oil reserves and performs risk analysis to maximize profitability while minimizing financial exposure.

## Business Challenge
OilyGiant faces a critical investment decision: where to drill 200 new oil wells with a fixed budget of $100 million. The challenge involves:

- **Capital Allocation**: Efficiently distribute $100M across 200 wells ($500K per well)
- **Profitability Assurance**: Each well must generate minimum $500K revenue to break even
- **Risk Management**: Maintain loss probability below 2.5% threshold
- **Regional Selection**: Choose optimal region from three available locations

## Technical Specifications

### **Financial Parameters**
- **Total Budget**: $100,000,000 for 200 oil wells
- **Cost per Well**: $500,000 average investment
- **Revenue Model**: $4.5 per barrel of crude oil
- **Break-even Point**: 111,111 barrels minimum per well
- **Profitability Unit**: $4,500 per thousand barrels

### **Risk Management Criteria**
- **Maximum Loss Probability**: 2.5%
- **Confidence Interval**: 95% for profit estimation
- **Bootstrap Samples**: 1,000 iterations for risk assessment
- **Selection Methodology**: Top 200 wells by predicted reserves

## Dataset Description

### **Data Sources**
The project analyzes geological exploration data from three distinct regions:
- `geo_data_0.csv` - Region 0 exploration data
- `geo_data_1.csv` - Region 1 exploration data  
- `geo_data_2.csv` - Region 2 exploration data

### **Feature Set**
- **id**: Unique identifier for each oil well location
- **f0, f1, f2**: Geological characteristics of drilling points
  - Specific meanings are proprietary but statistically significant
  - Used as predictive features for reserve estimation
- **product**: Target variable - oil reserves volume (thousands of barrels)

### **Data Structure**
- **Sample Size**: 500 exploration points per region
- **Total Observations**: 1,500 data points across three regions
- **Training Split**: 75% for model training, 25% for validation

## Machine Learning Methodology

### **1. Data Preprocessing & Analysis**
- Load and inspect geological data from all three regions
- Perform exploratory data analysis and feature validation
- Ensure data quality and handle any inconsistencies

### **2. Model Development**
- **Algorithm**: Linear Regression (business requirement)
- **Validation Strategy**: Train-test split (75-25 ratio)
- **Performance Metric**: Root Mean Square Error (RMSE)
- **Prediction Focus**: Oil reserve volumes per drilling location

### **3. Location Selection Strategy**
- Rank all 500 points in each region by predicted reserves
- Select top 200 locations with highest predicted oil volumes
- Calculate total expected reserves for selected wells per region

### **4. Financial Analysis**
- **Revenue Calculation**: Predicted reserves × $4,500 per thousand barrels
- **Profit Estimation**: Total revenue - $100M investment
- **Regional Comparison**: Identify most profitable region

### **5. Risk Assessment (Bootstrap Analysis)**
- Generate 1,000 bootstrap samples from top 200 wells per region
- Calculate profit distribution for each sample
- Determine:
  - Average expected profit
  - 95% confidence interval
  - Probability of financial loss
  - Risk-adjusted regional ranking

## Technologies & Libraries
- **Python 3.x** - Core programming language
- **pandas** - Data manipulation and analysis
- **numpy** - Numerical computing and statistical operations
- **scikit-learn** - Machine learning algorithms and model evaluation
- **matplotlib/seaborn** - Data visualization and result presentation
- **Jupyter Notebook** - Interactive development and documentation

## Project Structure
```
├── notebook.ipynb                 # Main analysis notebook
├── README.md                     # Project documentation
├── data/
│   ├── geo_data_0.csv           # Region 0 geological data
│   ├── geo_data_1.csv           # Region 1 geological data
│   └── geo_data_2.csv           # Region 2 geological data
├── results/
│   ├── model_performance.png    # RMSE comparison across regions
│   ├── profit_analysis.png      # Financial analysis visualization
│   └── risk_assessment.png      # Bootstrap risk analysis charts
└── src/
    ├── data_processing.py       # Data loading and preprocessing functions
    ├── model_training.py        # Linear regression model functions
    ├── profit_calculation.py    # Financial analysis functions
    └── risk_analysis.py         # Bootstrap and risk assessment functions
```

## How to Run

### **Prerequisites**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### **Execution Steps**
1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/oil-well-optimization.git
   cd oil-well-optimization
   ```

2. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook notebook.ipynb
   ```

3. **Run the analysis**:
   - Execute cells sequentially for complete analysis
   - Review model performance metrics
   - Examine risk assessment results
   - Analyze final regional recommendations

## Expected Outcomes

### **Model Performance**
- **RMSE Evaluation**: Quantify prediction accuracy for each region
- **Reserve Predictions**: Estimated oil volumes for top 200 wells per region
- **Comparative Analysis**: Model reliability across different geological areas

### **Financial Analysis**
- **Profit Projections**: Expected returns for each region
- **Break-even Analysis**: Validation against $500K minimum per well
- **ROI Calculations**: Return on investment for $100M budget

### **Risk Assessment Results**
- **Loss Probability**: Quantified financial risk for each region
- **Confidence Intervals**: 95% confidence bounds for profit estimates
- **Risk-Adjusted Recommendations**: Optimal region selection considering risk tolerance

## Business Impact

### **Strategic Decision Support**
- **Data-Driven Location Selection**: Replace intuition with quantitative analysis
- **Risk Mitigation**: Systematic approach to minimize financial exposure
- **Resource Optimization**: Maximize return on $100M investment

### **Operational Benefits**
- **Reduced Exploration Costs**: Focus resources on high-probability locations
- **Improved Success Rate**: Higher likelihood of profitable well drilling
- **Scalable Methodology**: Framework applicable to future expansion projects

## Key Performance Indicators
- **Target Profit**: Maximize expected returns while staying within risk tolerance
- **Success Criteria**: 
  - Loss probability < 2.5%
  - Average profit per well > $500K
  - RMSE minimization across regions

## Critical Success Factors
- **Model Accuracy**: Linear regression performance on geological features
- **Risk Management**: Bootstrap analysis reliability
- **Business Alignment**: Solutions meeting OilyGiant's financial constraints

## Contributing
Contributions are welcome! Please feel free to submit pull requests or open issues for improvements.

---
*This project demonstrates advanced application of machine learning for strategic business decision-making in the energy sector, combining predictive modeling with comprehensive risk analysis to optimize capital allocation.*