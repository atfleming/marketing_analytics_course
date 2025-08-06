# 📊 FedEx Statistical Analysis: A/B Testing & Campaign Optimization
### *Statistical Foundation for Logistics Marketing Analytics*

---

## 🎯 Project Overview

Apply **statistical methods** to analyze FedEx marketing campaign performance, conduct A/B testing, and make data-driven recommendations for budget allocation and campaign optimization using rigorous statistical analysis.

### 📈 **Business Context**
FedEx runs multiple marketing campaigns across different regions and channels. This project uses statistical analysis to determine which campaigns are truly effective, identify significant performance differences, and provide statistically-backed recommendations for marketing strategy.

---

## 📥 Dataset Information

### **🔗 Kaggle Dataset**
**Search Term:** `"Marketing Campaign Dataset"`  
**Dataset ID:** `rodsaldanha/arketing-campaign-dataset`  
**Size:** ~2,240 campaign records with performance metrics  
**Alternative:** `"Digital Marketing Dataset"` - `loveall/clicks-conversion-tracking`

### **📊 Expected Data Schema**
```
Campaign_ID          - Unique campaign identifier
Campaign_Type        - A/B test variants (Control, Variant_A, Variant_B)
Region              - Geographic segments (North, South, East, West, Central)
Channel             - Marketing channels (Digital, Print, Radio, TV, Direct_Mail)
Start_Date          - Campaign start date
End_Date            - Campaign end date
Budget              - Campaign investment ($)
Impressions         - Total ad impressions
Clicks              - Click-through count
Conversions         - Successful conversions
Revenue             - Generated revenue ($)
Cost_Per_Click      - Average cost per click ($)
Conversion_Rate     - Conversion percentage
Customer_Lifetime_Value - Average CLV ($)
```

---

## ✅ Statistical Analysis Checklist

### **📊 Day 1: Descriptive Statistics & Data Exploration**

#### **Data Preparation & Quality Assessment**
- [ ] **Import and Clean Data**
  - [ ] Load dataset into Excel
  - [ ] Check for missing values and outliers
  - [ ] Validate data types and ranges
  - [ ] Create calculated fields for key metrics

- [ ] **Descriptive Statistics Calculation**
  ```excel
  // Conversion Rate Statistics
  =AVERAGE(Conversion_Rate_Range)     // Mean conversion rate
  =MEDIAN(Conversion_Rate_Range)      // Median conversion rate
  =STDEV.S(Conversion_Rate_Range)     // Standard deviation
  =MIN(Conversion_Rate_Range)         // Minimum
  =MAX(Conversion_Rate_Range)         // Maximum
  
  // ROI Statistics
  =AVERAGE((Revenue_Range-Budget_Range)/Budget_Range)  // Mean ROI
  =PERCENTILE.EXC(ROI_Range, 0.25)    // Q1
  =PERCENTILE.EXC(ROI_Range, 0.75)    // Q3
  ```

- [ ] **Distribution Analysis**
  - [ ] Create histograms for key metrics (conversion rate, ROI, CPC)
  - [ ] Calculate skewness and kurtosis
  - [ ] Identify normal vs. non-normal distributions
  - [ ] Create box plots to identify outliers

#### **Regional Performance Analysis**
- [ ] **Summary Statistics by Region**
  - [ ] Calculate mean, median, std dev for each region
  - [ ] Create pivot table with regional breakdowns
  - [ ] Identify best and worst performing regions
  - [ ] Calculate coefficient of variation for consistency

- [ ] **Outlier Detection**
  ```excel
  // IQR Method for Outlier Detection
  =IF(OR(ROI<(Q1-1.5*(Q3-Q1)), ROI>(Q3+1.5*(Q3-Q1))), "Outlier", "Normal")
  
  // Z-Score Method
  =IF(ABS((ROI-AVERAGE(ROI_Range))/STDEV.S(ROI_Range))>2, "Outlier", "Normal")
  ```

### **📈 Day 2: Probability & Confidence Intervals**

#### **Probability Analysis**
- [ ] **Success Rate Modeling**
  - [ ] Model conversion rates using binomial distribution
  - [ ] Calculate probability of achieving target conversion rates
  - [ ] Apply to campaign planning and budgeting
  
  ```excel
  // Probability of at least X conversions
  =1-BINOM.DIST(X-1, Impressions, Conversion_Rate, TRUE)
  
  // Expected conversions with confidence
  =BINOM.INV(Impressions, Conversion_Rate, 0.95)  // 95th percentile
  ```

- [ ] **Revenue Forecasting**
  - [ ] Apply normal distribution to revenue predictions
  - [ ] Calculate probability ranges for budget planning
  - [ ] Model worst-case and best-case scenarios

#### **Confidence Intervals**
- [ ] **Campaign Performance CIs**
  ```excel
  // 95% CI for Conversion Rate
  =Conversion_Rate ± CONFIDENCE.T(0.05, STDEV.S(Conv_Rate), COUNT(Conv_Rate))
  
  // 95% CI for ROI
  =ROI_Mean ± CONFIDENCE.T(0.05, ROI_StdDev, Sample_Size)
  
  // CI for Revenue per Campaign
  =Revenue_Mean ± T.INV.2T(0.05, DF) * (Revenue_StdDev/SQRT(n))
  ```

- [ ] **Sample Size Calculations**
  - [ ] Calculate required sample sizes for future A/B tests
  - [ ] Determine minimum campaign duration for statistical power
  - [ ] Plan data collection requirements

### **🔬 Day 3: Hypothesis Testing - A/B Campaign Analysis**

#### **Two-Sample t-Tests**
- [ ] **Campaign A vs. Campaign B Comparison**
  ```excel
  // Independent samples t-test
  =T.TEST(Campaign_A_ROI, Campaign_B_ROI, 2, 2)  // Two-tailed, unequal variance
  
  // Effect size (Cohen's d)
  =(AVERAGE(A_ROI)-AVERAGE(B_ROI))/SQRT(((COUNT(A_ROI)-1)*VAR.S(A_ROI)+(COUNT(B_ROI)-1)*VAR.S(B_ROI))/(COUNT(A_ROI)+COUNT(B_ROI)-2))
  ```

- [ ] **Conversion Rate Testing**
  - [ ] Test significance of conversion rate differences
  - [ ] Calculate minimum detectable effect sizes
  - [ ] Determine winner with statistical confidence

- [ ] **Cost-Effectiveness Analysis**
  - [ ] Compare cost per acquisition between campaigns
  - [ ] Test significance of CPA differences
  - [ ] Account for multiple comparisons (Bonferroni correction)

#### **Paired Sample Analysis**
- [ ] **Before/After Campaign Analysis**
  ```excel
  // Paired t-test for pre/post campaign performance
  =T.TEST(Before_Range, After_Range, 2, 1)  // Two-tailed, paired
  
  // Mean difference and CI
  =AVERAGE(After_Range-Before_Range) ± CONFIDENCE.T(0.05, STDEV.S(Differences), COUNT(Differences))
  ```

### **📊 Day 4: ANOVA & Multi-Group Comparisons**

#### **One-Way ANOVA**
- [ ] **Multi-Region Performance Analysis**
  - [ ] Use Excel Data Analysis ToolPak for ANOVA
  - [ ] Test if regional means are significantly different
  - [ ] Calculate F-statistic and p-value
  - [ ] Interpret effect size (eta-squared)

- [ ] **Post-Hoc Analysis**
  ```excel
  // Tukey HSD for pairwise comparisons
  // Critical value calculation
  =SQRT(MSE/n) * QCRIT(alpha, groups, df_error)
  
  // Pairwise difference significance
  =IF(ABS(Mean1-Mean2) > Tukey_HSD, "Significant", "Not Significant")
  ```

#### **Multi-Channel Analysis**
- [ ] **Channel Effectiveness ANOVA**
  - [ ] Compare performance across Digital, Print, Radio, TV, Direct Mail
  - [ ] Identify significantly different channels
  - [ ] Rank channels by statistical performance

### **🔗 Day 5: Correlation & Regression Analysis**

#### **Correlation Analysis**
- [ ] **Marketing Spend vs. Revenue**
  ```excel
  // Pearson correlation
  =CORREL(Budget_Range, Revenue_Range)
  
  // Correlation significance test
  =T.DIST.2T(ABS(r)*SQRT((n-2)/(1-r^2)), n-2)  // p-value
  
  // Spearman rank correlation (for non-normal data)
  =CORREL(RANK(Budget_Range, Budget_Range), RANK(Revenue_Range, Revenue_Range))
  ```

- [ ] **Multi-Variable Correlations**
  - [ ] Create correlation matrix for all key metrics
  - [ ] Identify strongest predictors of campaign success
  - [ ] Check for multicollinearity issues

#### **Simple Linear Regression**
- [ ] **Revenue Prediction Model**
  ```excel
  // Regression coefficients
  =SLOPE(Revenue_Range, Budget_Range)     // Beta coefficient
  =INTERCEPT(Revenue_Range, Budget_Range) // Alpha (intercept)
  
  // R-squared
  =RSQ(Revenue_Range, Budget_Range)
  
  // Standard error of estimate
  =STEYX(Revenue_Range, Budget_Range)
  ```

- [ ] **Model Validation**
  - [ ] Check regression assumptions (linearity, normality, homoscedasticity)
  - [ ] Calculate prediction intervals
  - [ ] Validate model with holdout data

---

## 📊 Statistical Reporting Templates

### **📈 Executive Summary Template**
```
FEDEX CAMPAIGN STATISTICAL ANALYSIS SUMMARY

Key Findings:
• Campaign B outperformed Campaign A by X% (p < 0.05, Cohen's d = Y)
• Regional analysis shows significant differences (F = X, p < 0.001)
• Strong correlation between budget and revenue (r = 0.XX, p < 0.01)

Recommendations:
• Allocate XX% more budget to high-performing regions
• Implement Campaign B strategy across all channels
• Minimum campaign budget of $X for statistical significance

Statistical Confidence: 95% confidence intervals provided for all estimates
Sample Size: N = XXX campaigns analyzed
Effect Sizes: All significant effects are practically meaningful (d > 0.5)
```

### **🔬 Detailed Statistical Report**
- [ ] **Methods Section:** Describe all statistical tests used
- [ ] **Results Section:** Present findings with appropriate statistics
- [ ] **Assumptions:** Document assumption checking and violations
- [ ] **Limitations:** Acknowledge statistical and practical limitations

---

## 🎯 Key Statistical Insights to Identify

### **📊 Campaign Effectiveness**
- [ ] Which campaigns show statistically significant improvement?
- [ ] What is the minimum effect size that's practically meaningful?
- [ ] How confident can we be in our recommendations?

### **📈 Regional Optimization**
- [ ] Are regional differences statistically significant or due to chance?
- [ ] Which regions should receive increased investment?
- [ ] What's the expected ROI range for each region?

### **💰 Budget Allocation**
- [ ] What's the optimal budget allocation based on statistical evidence?
- [ ] How much budget is needed for statistically reliable results?
- [ ] What's the predicted revenue range for different budget levels?

---

## 🚀 Success Criteria

### **📊 Statistical Rigor**
- [ ] All hypothesis tests properly conducted with assumption checking
- [ ] Appropriate statistical methods chosen for data types
- [ ] Effect sizes calculated and interpreted alongside p-values
- [ ] Confidence intervals provided for all key estimates

### **🏢 Business Impact**
- [ ] Statistically-backed recommendations for campaign optimization
- [ ] Clear identification of significant vs. non-significant differences
- [ ] Quantified uncertainty in all business projections
- [ ] Actionable insights supported by rigorous analysis

### **📈 Professional Presentation**
- [ ] Statistical results communicated clearly to non-technical stakeholders
- [ ] Appropriate visualizations for statistical concepts
- [ ] Limitations and assumptions clearly stated
- [ ] Reproducible analysis with documented methods

---

## 📚 Statistical Concepts Applied

### **🔧 Descriptive Statistics**
- Central tendency and variability measures
- Distribution analysis and outlier detection
- Percentiles and quartiles for performance benchmarking

### **🎲 Inferential Statistics**
- Hypothesis testing for campaign comparisons
- Confidence intervals for performance estimates
- ANOVA for multi-group comparisons

### **📈 Relationship Analysis**
- Correlation analysis for variable relationships
- Simple linear regression for prediction
- Effect size calculations for practical significance

---

**🎯 Ready to apply statistical rigor to FedEx marketing analytics? This project builds the foundation for evidence-based marketing decisions backed by solid statistical analysis!**

---

*📧 Questions about specific statistical tests or need help interpreting results? Statistical thinking transforms marketing intuition into data-driven strategy.*
