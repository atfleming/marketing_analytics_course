# 📊 Module 2: Excel Analytics Fundamentals
### *Client-Focused Data Analysis and Dashboard Creation*

---

## 🎯 Module Objectives

Master **Excel for marketing data analytics** through three comprehensive client projects that demonstrate Excel's power for data analysis, visualization, and executive reporting across your key enterprise verticals.

### 📈 **Expected Deliverables**
- Three client-specific Excel analytics projects
- Advanced Excel formulas and pivot table mastery
- Interactive dashboards with slicers and dynamic charts
- Executive-ready reports and presentations

---

## 📁 Directory Structure

```
02_Module_Excel/
├── projects/               # Three client-specific Excel projects
│   ├── fedex_campaign_tracker/
│   ├── anovorx_adherence_dashboard/
│   └── atec_patient_cohorts/
├── templates/              # Reusable Excel templates and formulas
├── data_samples/           # Sample datasets for practice
└── README.md              # This guide and checklist
```

---

## ✅ Module 2 Completion Checklist

### **📊 Excel Fundamentals Setup (Week 2, Day 1)**
- [ ] Install Microsoft Excel (Office 365 recommended)
- [ ] Enable Data Analysis ToolPak add-in
- [ ] Set up Power Query (Get Data functionality)
- [ ] Configure Excel for analytics (show formulas, developer tab)
- [ ] Download practice datasets from Kaggle

### **🚚 Project 1: FedEx Multi-Region Campaign Performance Tracker (Week 2, Days 1-2)**

#### **📊 Project Overview**
Build a comprehensive Excel dashboard to analyze and visualize ROI of marketing campaigns across different regions for logistics operations.

#### **📥 Dataset & Setup**
- [ ] **Download Dataset:** Search "Logistics and Supply Chain Dataset" on Kaggle
- [ ] **Data Import:** Use Data > Get Data to import CSV files
- [ ] **Data Validation:** Check for missing values and inconsistencies
- [ ] **Data Cleaning:** Remove duplicates and standardize formats

#### **🔧 Excel Skills Development**
- [ ] **Data Import and Cleaning**
  ```excel
  // Remove duplicates
  Data > Remove Duplicates
  
  // Clean text data
  =TRIM(UPPER(A2))  // Remove spaces and standardize case
  =SUBSTITUTE(B2," ","")  // Remove all spaces
  
  // Handle missing values
  =IF(ISBLANK(C2),"Unknown",C2)
  ```

- [ ] **Calculated Fields Creation**
  ```excel
  // ROI Calculation
  =IF(D2=0,"N/A",(E2-D2)/D2)  // ROI = (Revenue-Spend)/Spend
  
  // Cost Per Lead
  =IF(F2=0,"N/A",D2/F2)  // Cost Per Lead = Spend/Leads
  
  // Revenue Per Lead
  =IF(F2=0,"N/A",E2/F2)  // Revenue Per Lead = Revenue/Leads
  
  // Performance Category
  =IF(G2>0.5,"High",IF(G2>0.2,"Medium","Low"))
  ```

- [ ] **Pivot Table Analysis**
  - [ ] Create pivot table: Regions (Rows) vs Campaigns (Columns) vs ROI (Values)
  - [ ] Add calculated fields for average ROI by region
  - [ ] Group data by quarters and campaign types
  - [ ] Apply conditional formatting to highlight performance

- [ ] **Dynamic Charts Creation**
  - [ ] Clustered bar chart: Spend vs Revenue by Region
  - [ ] Line chart: ROI trends over time
  - [ ] Scatter plot: Spend vs ROI correlation
  - [ ] Combo chart: Campaign volume and performance

- [ ] **Interactive Dashboard Elements**
  - [ ] Insert slicers for Region, Campaign Type, and Quarter
  - [ ] Create dropdown filters using Data Validation
  - [ ] Add timeline slicer for date-based filtering
  - [ ] Link charts to update dynamically with filters

#### **🎯 FedEx-Specific Analysis**
- [ ] **Regional Performance Ranking**
  ```excel
  =RANK(ROI_Column,ROI_Range,0)  // Rank regions by ROI
  ```
- [ ] **Underperforming Campaign Identification**
  ```excel
  =IF(ROI<AVERAGE(ROI_Range),"Below Average","Above Average")
  ```
- [ ] **Executive Summary Metrics**
  - [ ] Total campaign spend and revenue
  - [ ] Best and worst performing regions
  - [ ] Recommended budget reallocation
  - [ ] Projected ROI improvements

### **💊 Project 2: AnovoRx Patient Adherence and Program Impact Dashboard (Week 2, Days 2-3)**

#### **📊 Project Overview**
Create an Excel dashboard to track and report patient adherence rates, satisfaction scores, and time-to-treatment across pharmaceutical marketing programs.

#### **📥 Dataset & Setup**
- [ ] **Download Dataset:** Search "Pharma Sales Data" or "Pharma Drug Sales" on Kaggle
- [ ] **Privacy Considerations:** Ensure no patient identifiers are used
- [ ] **Data Structure:** Organize by Program, Channel, and Time Period
- [ ] **Compliance Check:** Validate data meets healthcare analytics standards

#### **🔧 Advanced Excel Techniques**
- [ ] **Healthcare-Specific Calculations**
  ```excel
  // Adherence Rate Calculation
  =COUNTIFS(Adherence_Range,">=80%")/COUNT(Adherence_Range)
  
  // Time to Treatment (days)
  =DATEDIF(Prescription_Date,Treatment_Start,"D")
  
  // Patient Satisfaction Average
  =AVERAGEIFS(Satisfaction_Range,Program_Range,"Program A")
  
  // Cohort Analysis
  =COUNTIFS(Start_Date_Range,">="&DATE(2024,1,1),
            Start_Date_Range,"<"&DATE(2024,4,1))
  ```

- [ ] **Advanced Pivot Table Features**
  - [ ] Create pivot table with Programs (Rows), Channels (Columns), Adherence (Values)
  - [ ] Add calculated fields for adherence percentages
  - [ ] Group patients by age ranges and treatment types
  - [ ] Show values as percentage of row total

- [ ] **Healthcare Dashboard Visualizations**
  - [ ] Gauge charts for adherence rate KPIs
  - [ ] Funnel chart for patient journey (Prescription → Treatment → Completion)
  - [ ] Heatmap for adherence by program and channel
  - [ ] Timeline chart for treatment initiation trends

- [ ] **Data Validation and Quality Checks**
  ```excel
  // Validate adherence percentages
  =IF(AND(A2>=0,A2<=1),A2,"Invalid")
  
  // Check date consistency
  =IF(Treatment_Start>=Prescription_Date,"Valid","Check Date")
  
  // Flag outliers
  =IF(ABS(A2-AVERAGE(A:A))>2*STDEV(A:A),"Outlier","Normal")
  ```

#### **🎯 AnovoRx-Specific Analysis**
- [ ] **Channel Effectiveness Comparison**
- [ ] **Payer Impact Analysis**
- [ ] **Treatment Bottleneck Identification**
- [ ] **Patient Cohort Segmentation**

### **🏥 Project 3: ATEC Spine/Campbell Clinic Patient Cohort and Outcome Analysis (Week 2, Days 3-4)**

#### **📊 Project Overview**
Build an Excel report tracking patient cohorts by procedure type, post-operative engagement, and outcome scores to inform targeted marketing campaigns.

#### **📥 Dataset & Setup**
- [ ] **Download Dataset:** Search "Healthcare Dataset" on Kaggle
- [ ] **Alternative:** Use "Customer Segmentation Dataset" for cohort logic
- [ ] **Medical Context:** Focus on orthopedic and spine-related procedures
- [ ] **Outcome Metrics:** Patient satisfaction, recovery time, engagement scores

#### **🔧 Advanced Analytics in Excel**
- [ ] **Cohort Analysis Setup**
  ```excel
  // Create cohort groups by procedure date
  =TEXT(Procedure_Date,"YYYY-MM")  // Monthly cohorts
  
  // Calculate cohort size
  =COUNTIFS(Cohort_Range,A2)
  
  // Retention analysis
  =COUNTIFS(Cohort_Range,A2,Follow_up_Range,"Yes")/COUNTIFS(Cohort_Range,A2)
  
  // Engagement scoring
  =SUMPRODUCT(Engagement_Factors,Weights)/SUM(Weights)
  ```

- [ ] **Statistical Analysis Functions**
  ```excel
  // Outcome score analysis
  =AVERAGE(Outcome_Range)  // Mean outcome score
  =STDEV(Outcome_Range)    // Standard deviation
  =PERCENTILE(Outcome_Range,0.9)  // 90th percentile
  
  // Correlation analysis
  =CORREL(Engagement_Range,Outcome_Range)
  
  // Regression analysis (using Data Analysis ToolPak)
  Data > Data Analysis > Regression
  ```

- [ ] **Advanced Charting Techniques**
  - [ ] Cohort heatmap using conditional formatting
  - [ ] Box and whisker plots for outcome distributions
  - [ ] Scatter plots with trend lines for correlations
  - [ ] Waterfall charts for patient journey stages

- [ ] **Dynamic Reporting Features**
  - [ ] Procedure type filter with dependent dropdowns
  - [ ] Date range selectors for cohort analysis
  - [ ] Outcome threshold sliders using scroll bars
  - [ ] Automated report generation with macros

#### **🎯 ATEC/Campbell-Specific Analysis**
- [ ] **Procedure Success Rate Analysis**
- [ ] **Patient Engagement Correlation**
- [ ] **Recovery Time Optimization**
- [ ] **Referral Pattern Analysis**

### **📊 Advanced Excel Features (Week 2, Days 4-5)**
- [ ] **Power Query for Data Transformation**
  - [ ] Connect to multiple data sources
  - [ ] Merge and append datasets
  - [ ] Create automated refresh workflows
  - [ ] Handle data type conversions

- [ ] **Advanced Formulas and Functions**
  ```excel
  // Array formulas
  =SUM(IF(Condition_Range=Criteria,Value_Range))
  
  // Dynamic ranges
  =OFFSET(A1,0,0,COUNTA(A:A),1)
  
  // Advanced lookups
  =INDEX(Return_Range,MATCH(1,(Criteria1_Range=Criteria1)*
         (Criteria2_Range=Criteria2),0))
  
  // Text manipulation
  =TEXTJOIN(",",TRUE,IF(Condition_Range=Criteria,Text_Range))
  ```

- [ ] **Dashboard Design Best Practices**
  - [ ] Consistent color schemes and branding
  - [ ] Clear visual hierarchy and layout
  - [ ] Mobile-friendly design considerations
  - [ ] Print-ready formatting options

---

## 🎯 Excel Proficiency Targets

### **📊 Technical Skills**
- [ ] **Data Management:** Import, clean, and validate datasets efficiently
- [ ] **Formula Mastery:** Use advanced functions for complex calculations
- [ ] **Pivot Table Expertise:** Create dynamic analysis with calculated fields
- [ ] **Visualization Skills:** Build professional charts and dashboards
- [ ] **Automation:** Implement basic macros and automated workflows

### **🏢 Business Applications**
- [ ] **Executive Reporting:** Create presentation-ready summaries
- [ ] **KPI Tracking:** Monitor key performance indicators effectively
- [ ] **Trend Analysis:** Identify patterns and insights in data
- [ ] **Scenario Planning:** Build models for what-if analysis
- [ ] **Data Storytelling:** Present insights clearly and persuasively

---

## 🚀 Success Criteria

### **📈 Project Deliverables**
- [ ] **FedEx Project:** Campaign ROI tracker with regional optimization insights
- [ ] **AnovoRx Project:** Patient adherence dashboard with program recommendations
- [ ] **ATEC/Campbell Project:** Cohort analysis with outcome predictions

### **🎯 Learning Outcomes**
- [ ] **Excel Mastery:** Confident use of advanced Excel features
- [ ] **Analytics Thinking:** Ability to structure and solve business problems
- [ ] **Client Relevance:** Understanding of industry-specific metrics and KPIs
- [ ] **Professional Presentation:** Executive-ready reports and dashboards

---

## 📚 Additional Resources

### **🔗 Excel Learning Resources**
- [Microsoft Excel Help Center](https://support.microsoft.com/excel)
- [ExcelJet - Excel Tips and Tutorials](https://www.exceljet.net/)
- [Chandoo.org - Excel Dashboard School](https://chandoo.org/)
- [Excel Campus - Advanced Excel Training](https://www.excelcampus.com/)

### **📖 Recommended Books**
- "Excel Dashboards and Reports" by Michael Alexander
- "Advanced Excel Essentials" by Jordan Goldmeier
- "Excel Data Analysis For Dummies" by Stephen L. Nelson

---

## 🎯 Next Steps

Upon completion of Module 2:
1. **Document Excel Expertise:** Create portfolio examples of each project
2. **Move to Module 3:** Tools setup and environment configuration
3. **Integration Planning:** Consider how Excel connects with other analytics tools
4. **Client Application:** Apply Excel skills to real client scenarios

---

**🎯 Ready to master Excel for marketing analytics? Start with the FedEx campaign tracker and build your foundation systematically!**

---

*📧 Questions about specific Excel techniques or need help with formula troubleshooting? Excel is often the gateway to advanced analytics - master it well!*
