# 📋 Resources & Templates Directory
### *Reusable Templates, Libraries, and Best Practices*

---

## 🎯 Overview

This directory contains **reusable templates, code libraries, and best practices** developed throughout your learning journey, designed to accelerate future analytics projects and ensure consistency across client work.

### 🛠️ **Resource Categories**
- **📊 SQL Libraries** - Reusable query templates and functions
- **🐍 Python Templates** - Standardized analysis and ML pipelines
- **📈 Dashboard Templates** - Tableau and Power BI starter templates
- **📖 Documentation Templates** - Project documentation and reporting formats

---

## 📁 Directory Structure

```
10_Resources_Templates/
├── sql_libraries/          # Reusable SQL queries and functions
│   ├── customer_segmentation.sql
│   ├── campaign_analysis.sql
│   ├── cohort_analysis.sql
│   └── kpi_calculations.sql
├── python_templates/       # Python analysis and ML templates
│   ├── data_exploration_template.ipynb
│   ├── clustering_analysis_template.ipynb
│   ├── predictive_modeling_template.ipynb
│   └── visualization_template.ipynb
├── dashboard_templates/    # Dashboard design templates
│   ├── tableau_templates/
│   ├── powerbi_templates/
│   └── design_guidelines.md
├── documentation_templates/ # Project documentation formats
│   ├── case_study_template.md
│   ├── technical_report_template.md
│   ├── executive_summary_template.md
│   └── methodology_template.md
└── README.md              # This resources guide
```

---

## ✅ Resources Development Checklist

### **🗃️ SQL Libraries Development**
- [ ] **Customer Segmentation Library**
  ```sql
  -- RFM Analysis Template
  WITH rfm_base AS (
      SELECT 
          customer_id,
          DATEDIFF(CURRENT_DATE, MAX(transaction_date)) AS recency,
          COUNT(DISTINCT transaction_id) AS frequency,
          SUM(transaction_amount) AS monetary
      FROM transactions 
      WHERE transaction_date >= DATE_SUB(CURRENT_DATE, INTERVAL 12 MONTH)
      GROUP BY customer_id
  ),
  rfm_scores AS (
      SELECT *,
          NTILE(5) OVER (ORDER BY recency DESC) AS r_score,
          NTILE(5) OVER (ORDER BY frequency ASC) AS f_score,
          NTILE(5) OVER (ORDER BY monetary ASC) AS m_score
      FROM rfm_base
  )
  SELECT 
      customer_id,
      CONCAT(r_score, f_score, m_score) AS rfm_segment,
      CASE 
          WHEN CONCAT(r_score, f_score, m_score) IN ('555', '554', '544') THEN 'Champions'
          WHEN CONCAT(r_score, f_score, m_score) IN ('543', '444', '435') THEN 'Loyal Customers'
          WHEN CONCAT(r_score, f_score, m_score) IN ('155', '154', '144') THEN 'At Risk'
          ELSE 'Other'
      END AS customer_segment
  FROM rfm_scores;
  ```

- [ ] **Campaign Analysis Library**
  ```sql
  -- Multi-Touch Attribution Template
  WITH customer_journey AS (
      SELECT 
          customer_id,
          touchpoint_date,
          channel,
          campaign_id,
          ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY touchpoint_date) AS touch_sequence,
          ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY touchpoint_date DESC) AS reverse_sequence
      FROM marketing_touchpoints
      WHERE touchpoint_date >= DATE_SUB(CURRENT_DATE, INTERVAL 6 MONTH)
  )
  SELECT 
      channel,
      CASE 
          WHEN touch_sequence = 1 THEN 'First Touch'
          WHEN reverse_sequence = 1 THEN 'Last Touch'
          ELSE 'Middle Touch'
      END AS attribution_type,
      COUNT(*) AS touchpoint_count,
      COUNT(DISTINCT customer_id) AS unique_customers
  FROM customer_journey
  GROUP BY channel, attribution_type;
  ```

### **🐍 Python Templates Development**
- [ ] **Data Exploration Template**
  ```python
  # Standard Data Exploration Template
  import pandas as pd
  import numpy as np
  import matplotlib.pyplot as plt
  import seaborn as sns
  
  def explore_dataset(df, target_column=None):
      """
      Comprehensive dataset exploration function
      """
      print("="*50)
      print("DATASET OVERVIEW")
      print("="*50)
      print(f"Shape: {df.shape}")
      print(f"Memory Usage: {df.memory_usage(deep=True).sum() / 1024**2:.2f} MB")
      
      print("\n" + "="*50)
      print("DATA TYPES")
      print("="*50)
      print(df.dtypes.value_counts())
      
      print("\n" + "="*50)
      print("MISSING VALUES")
      print("="*50)
      missing_data = df.isnull().sum()
      missing_percent = 100 * missing_data / len(df)
      missing_table = pd.DataFrame({
          'Missing Count': missing_data,
          'Missing Percentage': missing_percent
      })
      print(missing_table[missing_table['Missing Count'] > 0].sort_values('Missing Count', ascending=False))
      
      # Visualizations
      fig, axes = plt.subplots(2, 2, figsize=(15, 10))
      
      # Missing values heatmap
      sns.heatmap(df.isnull(), ax=axes[0,0], cbar=True, yticklabels=False)
      axes[0,0].set_title('Missing Values Heatmap')
      
      # Numeric columns distribution
      numeric_cols = df.select_dtypes(include=[np.number]).columns
      if len(numeric_cols) > 0:
          df[numeric_cols].hist(bins=20, ax=axes[0,1], alpha=0.7)
          axes[0,1].set_title('Numeric Distributions')
      
      # Correlation matrix
      if len(numeric_cols) > 1:
          corr_matrix = df[numeric_cols].corr()
          sns.heatmap(corr_matrix, annot=True, ax=axes[1,0], cmap='coolwarm')
          axes[1,0].set_title('Correlation Matrix')
      
      # Target distribution (if provided)
      if target_column and target_column in df.columns:
          df[target_column].value_counts().plot(kind='bar', ax=axes[1,1])
          axes[1,1].set_title(f'{target_column} Distribution')
      
      plt.tight_layout()
      plt.show()
      
      return missing_table
  ```

- [ ] **Machine Learning Pipeline Template**
  ```python
  # ML Pipeline Template
  from sklearn.model_selection import train_test_split, cross_val_score
  from sklearn.preprocessing import StandardScaler, LabelEncoder
  from sklearn.ensemble import RandomForestClassifier
  from sklearn.metrics import classification_report, confusion_matrix
  import joblib
  
  class MLPipeline:
      def __init__(self, model=None):
          self.model = model or RandomForestClassifier(random_state=42)
          self.scaler = StandardScaler()
          self.label_encoders = {}
          self.feature_names = None
          
      def prepare_data(self, df, target_column, test_size=0.2):
          """Prepare data for modeling"""
          # Separate features and target
          X = df.drop(columns=[target_column])
          y = df[target_column]
          
          # Handle categorical variables
          categorical_cols = X.select_dtypes(include=['object']).columns
          for col in categorical_cols:
              le = LabelEncoder()
              X[col] = le.fit_transform(X[col].astype(str))
              self.label_encoders[col] = le
          
          # Store feature names
          self.feature_names = X.columns.tolist()
          
          # Split data
          X_train, X_test, y_train, y_test = train_test_split(
              X, y, test_size=test_size, random_state=42, stratify=y
          )
          
          # Scale features
          X_train_scaled = self.scaler.fit_transform(X_train)
          X_test_scaled = self.scaler.transform(X_test)
          
          return X_train_scaled, X_test_scaled, y_train, y_test
      
      def train_and_evaluate(self, X_train, X_test, y_train, y_test):
          """Train model and evaluate performance"""
          # Train model
          self.model.fit(X_train, y_train)
          
          # Cross-validation
          cv_scores = cross_val_score(self.model, X_train, y_train, cv=5)
          print(f"Cross-validation scores: {cv_scores}")
          print(f"Mean CV score: {cv_scores.mean():.3f} (+/- {cv_scores.std() * 2:.3f})")
          
          # Test set evaluation
          y_pred = self.model.predict(X_test)
          print("\nClassification Report:")
          print(classification_report(y_test, y_pred))
          
          return y_pred
      
      def save_model(self, filepath):
          """Save trained model and preprocessing objects"""
          model_data = {
              'model': self.model,
              'scaler': self.scaler,
              'label_encoders': self.label_encoders,
              'feature_names': self.feature_names
          }
          joblib.dump(model_data, filepath)
          print(f"Model saved to {filepath}")
  ```

### **📊 Dashboard Templates Development**
- [ ] **Tableau Template Guidelines**
  ```markdown
  # Tableau Dashboard Template Guidelines
  
  ## Standard Layout Structure
  1. **Header Section** (10% of height)
     - Dashboard title and key metrics
     - Filter controls and date selectors
     - Company branding elements
  
  2. **Main Content Area** (75% of height)
     - Primary visualizations (2-3 key charts)
     - Logical flow from overview to details
     - Consistent color scheme and formatting
  
  3. **Footer Section** (15% of height)
     - Data source information
     - Last updated timestamp
     - Navigation and export options
  
  ## Color Palette Standards
  - **Primary:** Client brand colors
  - **Secondary:** Neutral grays (#F5F5F5, #E0E0E0)
  - **Accent:** Performance indicators (Green: #28A745, Red: #DC3545, Yellow: #FFC107)
  - **Text:** Dark gray (#333333) for readability
  
  ## Interactive Elements
  - Consistent filter placement (top or left sidebar)
  - Hover tooltips with relevant context
  - Click-through actions for drill-down analysis
  - Clear visual feedback for user interactions
  ```

- [ ] **Power BI Template Standards**
  ```markdown
  # Power BI Dashboard Template Standards
  
  ## Page Layout Structure
  1. **Title Bar** - Company logo, dashboard title, refresh timestamp
  2. **KPI Cards** - 3-5 key performance indicators
  3. **Main Visualizations** - 2-3 primary charts/tables
  4. **Filter Panel** - Slicers and date controls
  5. **Detail Section** - Supporting charts and breakdowns
  
  ## Visual Hierarchy
  - **Level 1:** KPI cards and primary metrics
  - **Level 2:** Trend analysis and comparisons
  - **Level 3:** Detailed breakdowns and drill-through
  
  ## Responsive Design
  - Mobile-friendly layout considerations
  - Consistent spacing and alignment
  - Readable fonts and appropriate sizing
  - Touch-friendly interactive elements
  ```

### **📖 Documentation Templates**
- [ ] **Executive Summary Template**
  ```markdown
  # [Project Name] Executive Summary
  
  ## Business Challenge
  [2-3 sentences describing the business problem or opportunity]
  
  ## Analytical Approach
  [Brief description of methodology and tools used]
  
  ## Key Findings
  - [Finding 1 with quantified impact]
  - [Finding 2 with quantified impact]
  - [Finding 3 with quantified impact]
  
  ## Recommendations
  1. **[Recommendation 1]** - Expected ROI: [X%], Timeline: [Y months]
  2. **[Recommendation 2]** - Expected ROI: [X%], Timeline: [Y months]
  3. **[Recommendation 3]** - Expected ROI: [X%], Timeline: [Y months]
  
  ## Next Steps
  - [Immediate action item 1]
  - [Immediate action item 2]
  - [Long-term strategic initiative]
  
  ## Investment Required
  - **Technology:** $[amount] for [tools/infrastructure]
  - **Resources:** [number] FTE for [duration]
  - **Training:** $[amount] for [team development]
  
  **Total ROI Projection:** [X%] return within [Y] months
  ```

---

## 🎯 Template Usage Guidelines

### **📋 When to Use Templates**
- **New Project Kickoff:** Start with exploration and methodology templates
- **Client Presentations:** Use executive summary and case study formats
- **Code Development:** Leverage Python and SQL libraries for efficiency
- **Dashboard Creation:** Apply design standards for consistency

### **🔄 Template Customization**
- **Client Branding:** Adapt colors, logos, and terminology
- **Industry Context:** Modify examples and use cases
- **Technical Requirements:** Adjust for specific tools and platforms
- **Compliance Needs:** Add healthcare, financial, or other regulatory elements

---

## 🚀 Success Metrics

### **⚡ Efficiency Gains**
- [ ] **Development Speed:** 50% faster project initiation with templates
- [ ] **Quality Consistency:** Standardized outputs across all projects
- [ ] **Error Reduction:** Fewer mistakes through proven methodologies
- [ ] **Knowledge Transfer:** Easier onboarding of new team members

### **📈 Business Value**
- [ ] **Client Satisfaction:** Consistent, professional deliverables
- [ ] **Scalability:** Ability to handle multiple projects simultaneously
- [ ] **Expertise Demonstration:** Showcase of best practices and methodologies
- [ ] **Competitive Advantage:** Faster delivery and higher quality outputs

---

## 🎯 Continuous Improvement

### **🔄 Template Evolution**
- [ ] **Regular Updates:** Incorporate learnings from each project
- [ ] **Industry Trends:** Adapt to new tools and methodologies
- [ ] **Client Feedback:** Refine based on stakeholder input
- [ ] **Performance Metrics:** Track and optimize template effectiveness

### **📚 Knowledge Sharing**
- [ ] **Team Training:** Share templates and best practices
- [ ] **Documentation:** Maintain comprehensive usage guides
- [ ] **Version Control:** Track template changes and improvements
- [ ] **Community Contribution:** Share insights with analytics community

---

**🎯 Ready to accelerate your analytics work with proven templates and best practices? Build your resource library systematically and refine continuously!**
