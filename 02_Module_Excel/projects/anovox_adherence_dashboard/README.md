# 💊 AnovoRx Patient Adherence and Program Impact Dashboard
### *Excel Analytics Project for Specialty Pharma Marketing Optimization*

---

## 🎯 Project Overview

Build a comprehensive **Excel dashboard** to analyze patient adherence patterns, program effectiveness, and marketing ROI for specialty pharmaceutical programs, mirroring AnovoRx's patient-centric analytics needs.

### 📊 **Business Context**
AnovoRx specializes in complex specialty medications requiring intensive patient support programs. This project helps identify adherence barriers, optimize patient engagement strategies, and demonstrate program value through data-driven insights while maintaining HIPAA compliance.

---

## 📥 Dataset Information

### **🔗 Kaggle Dataset**
**Search Term:** `"Healthcare Analytics Dataset"`  
**Dataset ID:** `prasad22/healthcare-dataset`  
**Size:** ~10,000 patient records with treatment outcomes  
**Alternative:** `"Pharmaceutical Sales Dataset"` - `milanzdravkovic/pharma-sales-data`

### **📊 Expected Data Schema**
```
Patient_ID          - De-identified patient identifier
Program_Type        - Support program (Basic, Enhanced, Premium)
Medication_Class    - Therapeutic area (Oncology, Rheumatology, etc.)
Enrollment_Date     - Program start date (YYYY-MM-DD)
Adherence_Rate      - Medication adherence % (0-100)
Days_in_Program     - Program duration (days)
Support_Touchpoints - Number of support interactions
Cost_Per_Patient    - Program cost allocation ($)
Clinical_Outcome    - Improvement score (1-10 scale)
Patient_Satisfaction - Satisfaction rating (1-5 scale)
Geographic_Region   - Patient location (anonymized)
```

---

## ✅ Project Completion Checklist

### **📥 Data Preparation (Day 1)**
- [ ] **Download and Import Data**
  - [ ] Download healthcare dataset from Kaggle
  - [ ] Open Excel and use Data > Get Data > From Text/CSV
  - [ ] Apply data privacy filters (remove any PII)
  - [ ] Save as Excel workbook with password protection

- [ ] **HIPAA Compliance Check**
  - [ ] Verify no direct patient identifiers present
  - [ ] Confirm geographic data is sufficiently aggregated
  - [ ] Add data privacy disclaimer to workbook
  - [ ] Document de-identification methods used

- [ ] **Data Quality Assessment**
  - [ ] Check adherence rates are within 0-100% range
  - [ ] Validate date formats and chronological order
  - [ ] Identify and handle missing clinical outcomes
  - [ ] Flag outliers in cost and satisfaction data

- [ ] **Data Cleaning**
  ```excel
  // Standardize program types
  =PROPER(TRIM(B2))
  
  // Clean adherence percentages
  =IF(C2>1,C2/100,C2)
  
  // Handle missing satisfaction scores
  =IF(ISBLANK(J2),AVERAGE($J$2:$J$1000),J2)
  ```

### **🧮 Calculated Fields Creation (Day 1)**
- [ ] **Program ROI Calculation**
  ```excel
  // ROI based on clinical improvement (Column L)
  =IF(H2=0,"N/A",ROUND((I2*1000-H2)/H2,4))
  
  // ROI Category
  =IF(L2="N/A","No Data",
     IF(L2>2,"High ROI",
        IF(L2>0.5,"Medium ROI","Low ROI")))
  ```

- [ ] **Adherence Performance Category**
  ```excel
  // Adherence Category (Column M)
  =IF(E2>=0.8,"Excellent",
     IF(E2>=0.6,"Good",
        IF(E2>=0.4,"Fair","Poor")))
  ```

- [ ] **Program Effectiveness Score**
  ```excel
  // Effectiveness Score (Column N)
  =ROUND((E2*0.4)+(I2/10*0.3)+(J2/5*0.3),2)
  ```

- [ ] **Time to Improvement**
  ```excel
  // Days to Clinical Improvement (Column O)
  =IF(I2>5,F2*0.7,F2*1.2)
  ```

### **📊 Pivot Table Analysis (Day 2)**
- [ ] **Program Performance Pivot**
  - [ ] Insert > PivotTable
  - [ ] Rows: Program_Type
  - [ ] Columns: Medication_Class
  - [ ] Values: Average Adherence_Rate, Average Clinical_Outcome
  - [ ] Add calculated field for program efficiency

- [ ] **Regional Analysis Pivot**
  - [ ] Rows: Geographic_Region
  - [ ] Columns: Adherence_Category
  - [ ] Values: Count of Patient_ID, Average Cost_Per_Patient
  - [ ] Show values as % of row total

- [ ] **Time-Based Trends Pivot**
  - [ ] Rows: Enrollment_Date (grouped by quarter)
  - [ ] Columns: Program_Type
  - [ ] Values: Average Adherence_Rate, Count of Patients
  - [ ] Add timeline slicer for dynamic filtering

### **📈 Chart Creation (Day 2)**
- [ ] **Adherence Rate Distribution (Histogram)**
  - [ ] Select adherence rate data
  - [ ] Insert > Charts > Histogram
  - [ ] Format with healthcare colors (Blue #0066CC, Green #00AA44)
  - [ ] Add target adherence line at 80%

- [ ] **Program ROI Comparison (Column Chart)**
  - [ ] Select Program_Type and ROI data
  - [ ] Insert > Charts > Clustered Column Chart
  - [ ] Add data labels and error bars
  - [ ] Color-code by ROI performance level

- [ ] **Patient Journey Timeline**
  - [ ] Create scatter plot with Days_in_Program vs Clinical_Outcome
  - [ ] Add trendline with confidence intervals
  - [ ] Color-code points by Program_Type
  - [ ] Add annotations for key milestones

- [ ] **Support Touchpoint Effectiveness**
  - [ ] Create bubble chart with:
    - X-axis: Support_Touchpoints
    - Y-axis: Adherence_Rate
    - Bubble size: Clinical_Outcome
  - [ ] Add quadrant lines for performance segments

### **🎛️ Interactive Dashboard Creation (Day 3)**
- [ ] **Dashboard Layout Setup**
  - [ ] Create new worksheet named "Patient_Dashboard"
  - [ ] Set up HIPAA compliance header (5% of height)
  - [ ] Design KPI section (20% of height)
  - [ ] Main analytics area (65% of height)
  - [ ] Footer with data source and disclaimers (10% of height)

- [ ] **Slicer Implementation**
  - [ ] Insert slicers for Program_Type, Medication_Class, Region
  - [ ] Position slicers in sidebar or header
  - [ ] Connect slicers to all relevant pivot tables
  - [ ] Format with consistent healthcare branding

- [ ] **Timeline Filter**
  - [ ] Insert > Timeline for Enrollment_Date filtering
  - [ ] Connect to all pivot tables and charts
  - [ ] Set default to last 12 months
  - [ ] Add quarter and year grouping options

- [ ] **Dynamic Chart Linking**
  - [ ] Copy charts from analysis sheets
  - [ ] Paste as linked objects on dashboard
  - [ ] Verify charts update with slicer changes
  - [ ] Arrange for logical patient journey flow

### **📋 Executive KPI Section (Day 3)**
- [ ] **Patient Outcome KPIs**
  ```excel
  // Overall Adherence Rate
  =AVERAGEIFS(Adherence_Range,Program_Range,Selected_Program)
  
  // Clinical Improvement Rate
  =COUNTIFS(Clinical_Range,">5",Program_Range,Selected_Program)/
   COUNTIFS(Program_Range,Selected_Program)
  
  // Patient Satisfaction Score
  =AVERAGEIFS(Satisfaction_Range,Program_Range,Selected_Program)
  
  // Program Efficiency Ratio
  =AVERAGEIFS(Clinical_Range,Program_Range,Selected_Program)/
   AVERAGEIFS(Cost_Range,Program_Range,Selected_Program)*1000
  ```

- [ ] **Performance Indicators**
  - [ ] Use conditional formatting for KPI cards
  - [ ] Green for above-benchmark performance (>80% adherence)
  - [ ] Red for below-benchmark performance (<60% adherence)
  - [ ] Yellow for at-benchmark performance (60-80% adherence)

- [ ] **Risk Alert System**
  ```excel
  // Patient Risk Alert
  =IF(AND(Adherence_Rate<0.6,Days_in_Program>30),
     "HIGH RISK: Intervention Needed",
     IF(Adherence_Rate<0.8,"MEDIUM RISK: Monitor Closely","LOW RISK"))
  ```

### **🎨 Design and Formatting (Day 4)**
- [ ] **Healthcare Brand Application**
  - [ ] Apply professional healthcare color scheme
  - [ ] Use clean, readable fonts (Arial or Calibri)
  - [ ] Add AnovoRx-style branding elements
  - [ ] Maintain clinical, trustworthy appearance

- [ ] **HIPAA-Compliant Design**
  - [ ] Add privacy disclaimers prominently
  - [ ] Use aggregate data displays only
  - [ ] Avoid individual patient identification
  - [ ] Include data security notices

- [ ] **Visual Hierarchy**
  - [ ] Largest elements: Critical patient safety KPIs
  - [ ] Medium elements: Program performance metrics
  - [ ] Smallest elements: Supporting data and notes
  - [ ] Use white space for clinical clarity

### **📊 Advanced Healthcare Analytics (Day 4)**
- [ ] **Predictive Adherence Modeling**
  ```excel
  // Adherence Prediction Score
  =0.3*Support_Touchpoints/10 + 0.4*Patient_Satisfaction/5 + 
   0.3*IF(Days_in_Program>90,1,Days_in_Program/90)
  ```

- [ ] **Patient Segmentation Analysis**
  - [ ] Create patient risk segments using clustering
  - [ ] High-risk: Low adherence + High cost
  - [ ] Medium-risk: Moderate adherence + Medium engagement
  - [ ] Low-risk: High adherence + Good outcomes

- [ ] **Program Optimization Recommendations**
  ```excel
  // Intervention Recommendation
  =IF(Adherence_Rate<0.6,
     "Increase Support Frequency",
     IF(Clinical_Outcome<5,
        "Review Treatment Plan",
        "Maintain Current Program"))
  ```

- [ ] **Cost-Effectiveness Analysis**
  - [ ] Calculate cost per quality-adjusted outcome
  - [ ] Compare program types by efficiency
  - [ ] Identify optimization opportunities
  - [ ] Build budget allocation recommendations

---

## 🎯 Key Metrics to Track

### **📈 Primary Patient KPIs**
- **Medication Adherence Rate:** `% of prescribed doses taken`
- **Clinical Improvement Score:** `Post-treatment outcome rating`
- **Patient Satisfaction:** `Program satisfaction rating (1-5)`
- **Time to Improvement:** `Days from enrollment to clinical benefit`
- **Program Completion Rate:** `% of patients completing full program`

### **📊 Business Performance Metrics**
- **Cost per Patient Outcome:** `Program Cost / Clinical Improvement`
- **Program ROI:** `(Clinical Value - Program Cost) / Program Cost`
- **Support Efficiency:** `Clinical Outcomes / Support Touchpoints`
- **Patient Retention Rate:** `% of patients staying in program >90 days`
- **Risk-Adjusted Outcomes:** `Clinical improvement adjusted for patient risk`

---

## 🚀 Success Criteria

### **📊 Technical Excellence**
- [ ] Dashboard loads quickly with large patient datasets
- [ ] All calculations maintain HIPAA compliance
- [ ] Interactive elements work smoothly
- [ ] Professional healthcare design standards met

### **🏥 Clinical Value**
- [ ] Identifies patient adherence improvement opportunities
- [ ] Highlights program effectiveness variations by >20%
- [ ] Provides actionable intervention recommendations
- [ ] Demonstrates measurable clinical outcome improvements

### **🎯 Learning Outcomes**
- [ ] Understanding of healthcare analytics compliance requirements
- [ ] Experience with patient outcome measurement
- [ ] Mastery of Excel healthcare dashboard design
- [ ] Confidence in presenting clinical data to stakeholders

---

## 📚 Excel Functions Reference

### **🔧 Healthcare-Specific Formulas**
```excel
// Patient Risk Scoring
=IF(AND(Adherence<0.6,Satisfaction<3,Days>30),"High Risk",
   IF(OR(Adherence<0.8,Satisfaction<4),"Medium Risk","Low Risk"))

// Clinical Effectiveness
=SUMPRODUCT((Clinical_Outcome>5)*(Program_Type="Enhanced"))/
 SUMPRODUCT((Program_Type="Enhanced")*1)

// Cost-Effectiveness Ratio
=AVERAGEIFS(Cost_Range,Clinical_Range,">7")/
 AVERAGEIFS(Clinical_Range,Clinical_Range,">7")

// Patient Journey Analysis
=DATEDIF(Enrollment_Date,TODAY(),"D")
=NETWORKDAYS(Enrollment_Date,Improvement_Date)
```

### **🔍 Advanced Analytics Functions**
```excel
// Cohort Analysis
=SUMIFS(Patient_Count,Enrollment_Month,A2,Adherence_Category,"Excellent")

// Survival Analysis (Program Retention)
=1-COUNTIFS(Dropout_Date,"<="&B2,Enrollment_Date,"<="&B2-90)/
  COUNTIFS(Enrollment_Date,"<="&B2-90)

// Statistical Significance Testing
=T.TEST(Group1_Outcomes,Group2_Outcomes,2,2)
=CONFIDENCE.T(0.05,STDEV(Outcomes),COUNT(Outcomes))
```

---

## 🔒 HIPAA Compliance Guidelines

### **📋 Data Privacy Requirements**
- [ ] **De-identification:** All patient identifiers removed or encrypted
- [ ] **Aggregation:** Individual patient data not displayed
- [ ] **Access Control:** Password-protected workbook
- [ ] **Audit Trail:** Document all data transformations
- [ ] **Secure Storage:** Store in encrypted, access-controlled location

### **⚠️ Privacy Safeguards**
- [ ] Minimum cell size of 5 patients for any metric
- [ ] Geographic regions aggregated to prevent identification
- [ ] Date ranges used instead of specific dates
- [ ] Clinical outcomes reported in ranges, not exact values
- [ ] Regular privacy impact assessments documented

---

## 🎯 Next Steps

Upon completion of the AnovoRx project:
1. **Clinical Insights Report:** Document key patient adherence findings
2. **Move to ATEC Spine Project:** Apply Excel skills to medical device analytics
3. **Portfolio Addition:** Add anonymized screenshots and methodology
4. **Compliance Validation:** Review all outputs for HIPAA compliance

---

**🎯 Ready to build your healthcare analytics expertise? Follow the checklist systematically while maintaining the highest standards of patient privacy and clinical accuracy!**

---

*📧 Questions about healthcare analytics compliance or need help with clinical outcome calculations? Healthcare data requires special attention to privacy and accuracy.*
