# 🚚 FedEx Multi-Region Campaign Performance Tracker
### *Excel Analytics Project for Logistics Marketing Optimization*

---

## 🎯 Project Overview

Build a comprehensive **Excel dashboard** to analyze and visualize ROI of marketing campaigns across different regions for logistics operations, mirroring FedEx's marketing analytics needs.

### 📊 **Business Context**
FedEx operates across multiple regions with diverse marketing channels. This project helps identify high-performing and underperforming markets, optimize budget allocation, and improve campaign effectiveness through data-driven insights.

---

## 📥 Dataset Information

### **🔗 Kaggle Dataset**
**Search Term:** `"Logistics and Supply Chain Dataset"`  
**Dataset ID:** `datasetengineer/logistics-and-supply-chain-dataset`  
**Size:** ~180,000 records of operational logistics data

### **📊 Expected Data Schema**
```
Campaign_ID          - Unique campaign identifier
Campaign_Name        - Descriptive campaign name
Region              - Geographic segments (North, South, East, West)
Channel             - Marketing channels (Digital, Print, Events, Direct Mail)
Date                - Campaign dates (YYYY-MM-DD format)
Spend               - Campaign investment ($)
Revenue             - Generated revenue ($)
Leads               - Lead generation count
Conversions         - Successful conversions
Customer_Satisfaction - Rating (1-5 scale)
```

---

## ✅ Project Completion Checklist

### **📥 Data Preparation (Day 1)**
- [ ] **Download and Import Data**
  - [ ] Download dataset from Kaggle
  - [ ] Open Excel and use Data > Get Data > From Text/CSV
  - [ ] Preview data and adjust column types
  - [ ] Save as Excel workbook (.xlsx format)

- [ ] **Data Quality Assessment**
  - [ ] Check for missing values using filters
  - [ ] Identify and handle duplicates (Data > Remove Duplicates)
  - [ ] Validate date formats and numeric fields
  - [ ] Document any data quality issues

- [ ] **Data Cleaning**
  ```excel
  // Clean region names
  =PROPER(TRIM(A2))
  
  // Standardize channel names
  =SUBSTITUTE(SUBSTITUTE(B2,"digital","Digital"),"print","Print")
  
  // Handle missing values
  =IF(ISBLANK(C2),"Unknown",C2)
  ```

### **🧮 Calculated Fields Creation (Day 1)**
- [ ] **ROI Calculation**
  ```excel
  // ROI Formula (Column H)
  =IF(D2=0,"N/A",ROUND((E2-D2)/D2,4))
  
  // ROI Percentage Format
  =IF(D2=0,"N/A",TEXT((E2-D2)/D2,"0.00%"))
  ```

- [ ] **Cost Per Lead**
  ```excel
  // Cost Per Lead (Column I)
  =IF(F2=0,"N/A",ROUND(D2/F2,2))
  ```

- [ ] **Revenue Per Lead**
  ```excel
  // Revenue Per Lead (Column J)
  =IF(F2=0,"N/A",ROUND(E2/F2,2))
  ```

- [ ] **Performance Category**
  ```excel
  // Performance Rating (Column K)
  =IF(H2="N/A","No Data",
     IF(H2>0.5,"High Performance",
        IF(H2>0.2,"Medium Performance","Low Performance")))
  ```

### **📊 Pivot Table Analysis (Day 2)**
- [ ] **Regional Performance Pivot**
  - [ ] Insert > PivotTable
  - [ ] Rows: Region
  - [ ] Columns: Channel
  - [ ] Values: Sum of Revenue, Sum of Spend, Average ROI
  - [ ] Add calculated field for Total ROI

- [ ] **Campaign Performance Pivot**
  - [ ] Rows: Campaign_Name
  - [ ] Columns: Quarter (group dates by quarter)
  - [ ] Values: Sum of Leads, Sum of Conversions
  - [ ] Add conversion rate calculated field

- [ ] **Time-Based Analysis Pivot**
  - [ ] Rows: Date (grouped by month)
  - [ ] Columns: Region
  - [ ] Values: Sum of Spend, Sum of Revenue
  - [ ] Show values as % of grand total

### **📈 Chart Creation (Day 2)**
- [ ] **Regional ROI Comparison (Bar Chart)**
  - [ ] Select regional ROI data from pivot table
  - [ ] Insert > Charts > Clustered Bar Chart
  - [ ] Format with FedEx colors (Purple #4B0082, Orange #FF6600)
  - [ ] Add data labels and title

- [ ] **Spend vs Revenue Scatter Plot**
  - [ ] Select Spend (X-axis) and Revenue (Y-axis) data
  - [ ] Insert > Charts > Scatter Plot
  - [ ] Add trendline with R-squared value
  - [ ] Color-code points by region

- [ ] **Campaign Performance Timeline**
  - [ ] Create line chart with Date vs ROI
  - [ ] Add multiple series for different regions
  - [ ] Format with clear legend and axis labels
  - [ ] Add data markers for key campaigns

- [ ] **Channel Effectiveness Combo Chart**
  - [ ] Primary axis: Lead volume (columns)
  - [ ] Secondary axis: ROI percentage (line)
  - [ ] Group by marketing channel
  - [ ] Add target ROI reference line

### **🎛️ Interactive Dashboard Creation (Day 3)**
- [ ] **Dashboard Layout Setup**
  - [ ] Create new worksheet named "Dashboard"
  - [ ] Set up header section (10% of height)
  - [ ] Design main content area (75% of height)
  - [ ] Add footer with data source info (15% of height)

- [ ] **Slicer Implementation**
  - [ ] Insert slicers for Region, Channel, and Campaign Type
  - [ ] Position slicers in header or sidebar
  - [ ] Connect slicers to all relevant pivot tables
  - [ ] Format slicers with consistent styling

- [ ] **Timeline Filter**
  - [ ] Insert > Timeline for date-based filtering
  - [ ] Connect to all pivot tables and charts
  - [ ] Position prominently in dashboard
  - [ ] Set default to last 12 months

- [ ] **Dynamic Chart Linking**
  - [ ] Copy charts from analysis sheets
  - [ ] Paste as linked objects on dashboard
  - [ ] Verify charts update with slicer changes
  - [ ] Arrange charts for logical flow

### **📋 Executive Summary Section (Day 3)**
- [ ] **KPI Cards Creation**
  ```excel
  // Total Campaign Spend
  =SUMPRODUCT((Region_Range=Selected_Region)*(Spend_Range))
  
  // Average ROI
  =AVERAGEIF(Region_Range,Selected_Region,ROI_Range)
  
  // Best Performing Region
  =INDEX(Region_Range,MATCH(MAX(ROI_Range),ROI_Range,0))
  
  // Worst Performing Region
  =INDEX(Region_Range,MATCH(MIN(ROI_Range),ROI_Range,0))
  ```

- [ ] **Performance Indicators**
  - [ ] Use conditional formatting for KPI cards
  - [ ] Green for above-target performance
  - [ ] Red for below-target performance
  - [ ] Yellow for at-target performance

- [ ] **Recommendation Engine**
  ```excel
  // Budget Reallocation Suggestion
  =IF(ROI_Current>ROI_Target,"Increase Budget",
     IF(ROI_Current<ROI_Threshold,"Reduce Budget","Maintain Budget"))
  ```

### **🎨 Design and Formatting (Day 4)**
- [ ] **FedEx Brand Application**
  - [ ] Apply FedEx color scheme throughout
  - [ ] Use consistent fonts (Arial or Calibri)
  - [ ] Add FedEx logo to header (if available)
  - [ ] Maintain professional appearance

- [ ] **Visual Hierarchy**
  - [ ] Largest elements: Key KPIs and primary charts
  - [ ] Medium elements: Supporting charts and filters
  - [ ] Smallest elements: Data source and notes
  - [ ] Use white space effectively

- [ ] **Conditional Formatting**
  - [ ] Color-code performance metrics
  - [ ] Use data bars for comparative metrics
  - [ ] Apply icon sets for trend indicators
  - [ ] Highlight outliers and exceptions

### **📊 Advanced Features (Day 4)**
- [ ] **What-If Analysis**
  - [ ] Create scenario manager for budget allocation
  - [ ] Use Goal Seek for target ROI achievement
  - [ ] Build sensitivity analysis table
  - [ ] Add data validation for input controls

- [ ] **Automated Alerts**
  ```excel
  // Performance Alert Formula
  =IF(Current_ROI<Target_ROI*0.8,"ALERT: Low Performance","OK")
  ```

- [ ] **Export Functionality**
  - [ ] Create print-friendly version
  - [ ] Set up PDF export settings
  - [ ] Prepare email-ready summary
  - [ ] Build PowerPoint export template

---

## 🎯 Key Metrics to Track

### **📈 Primary KPIs**
- **Campaign ROI:** `(Revenue - Spend) / Spend`
- **Cost Per Lead:** `Total Spend / Total Leads`
- **Revenue Per Lead:** `Total Revenue / Total Leads`
- **Conversion Rate:** `Conversions / Leads`
- **Regional Performance Index:** Weighted average of all metrics

### **📊 Secondary Metrics**
- Lead volume trends by region and time
- Channel effectiveness comparison
- Campaign performance seasonality
- Customer satisfaction correlation with ROI
- Budget utilization efficiency

---

## 🚀 Success Criteria

### **📊 Technical Excellence**
- [ ] Dashboard loads quickly and updates smoothly
- [ ] All formulas calculate correctly
- [ ] Charts and slicers work interactively
- [ ] Professional design follows brand guidelines

### **🏢 Business Value**
- [ ] Identifies top 3 underperforming regions with specific metrics
- [ ] Highlights optimization opportunities worth 15%+ ROI improvement
- [ ] Provides actionable budget reallocation recommendations
- [ ] Enables data-driven regional strategy decisions

### **🎯 Learning Outcomes**
- [ ] Mastery of Excel pivot tables and calculated fields
- [ ] Understanding of logistics industry KPIs
- [ ] Experience with interactive dashboard design
- [ ] Confidence in presenting data insights to executives

---

## 📚 Excel Functions Reference

### **🔧 Essential Formulas Used**
```excel
// Data Analysis
=SUMIFS(Revenue_Range,Region_Range,"North",Channel_Range,"Digital")
=AVERAGEIFS(ROI_Range,Region_Range,"South",Date_Range,">="&DATE(2024,1,1))
=COUNTIFS(Performance_Range,"High",Region_Range,"East")

// Lookup Functions
=VLOOKUP(Campaign_ID,Campaign_Table,3,FALSE)
=INDEX(Region_Range,MATCH(MAX(ROI_Range),ROI_Range,0))
=XLOOKUP(Region,"North",ROI_Range)

// Statistical Analysis
=PERCENTILE(ROI_Range,0.9)
=RANK(ROI_Value,ROI_Range,0)
=CORREL(Spend_Range,Revenue_Range)

// Date Functions
=YEAR(Date_Range)
=MONTH(Date_Range)
=EOMONTH(Date_Range,0)
```

---

## 🎯 Next Steps

Upon completion of the FedEx project:
1. **Document Insights:** Create executive summary of findings
2. **Move to AnovoRx Project:** Apply Excel skills to healthcare analytics
3. **Portfolio Addition:** Add screenshots and methodology to portfolio
4. **Client Application:** Consider how insights apply to real FedEx scenarios

---

**🎯 Ready to build your first professional Excel analytics dashboard? Follow the checklist systematically and focus on actionable business insights!**

---

*📧 Questions about specific Excel techniques or need help with formula troubleshooting? Excel mastery is the foundation of all advanced analytics work.*
