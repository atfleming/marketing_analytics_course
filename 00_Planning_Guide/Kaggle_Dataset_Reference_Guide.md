# 📊 Kaggle Dataset Reference Guide
### *Curated Industry-Specific Datasets for Client-Focused Analytics Learning*

---

## 🎯 Dataset Overview

Master real-world analytics with **carefully selected Kaggle datasets** that mirror your enterprise client scenarios. Each dataset is mapped to specific client verticals and includes detailed use cases, project applications, and learning objectives.

### 🏢 **Client-Dataset Alignment**
- **🚚 FedEx** - Logistics & Supply Chain Datasets
- **💊 AnovoRx** - Pharmaceutical & Healthcare Datasets  
- **🏥 ATEC Spine** - Medical Device & MedTech Datasets
- **⚕️ Campbell Clinic** - Healthcare Services & Patient Analytics

---

## 🚚 FedEx (Logistics & Supply Chain)

### 📦 **Primary Datasets**

#### **🌟 Logistics and Supply Chain Dataset**
**Kaggle Search:** `"Logistics and Supply Chain Dataset"`  
**Dataset ID:** `datasetengineer/logistics-and-supply-chain-dataset`

**📊 Dataset Overview:**
- **Size:** 180,000+ records of real operational logistics data
- **Time Range:** Multi-year logistics network operations
- **Key Features:** Delivery performance, route optimization, customer satisfaction, cost analysis

**🔍 Data Schema:**
```
- Order_ID: Unique order identifier
- Customer_ID: Customer reference number
- Product_Category: Type of shipped product
- Origin_Location: Shipping origin point
- Destination_Location: Delivery destination
- Shipping_Date: Order dispatch date
- Delivery_Date: Actual delivery date
- Delivery_Status: On-time/Late/Failed delivery
- Shipping_Cost: Transportation cost
- Customer_Rating: Delivery satisfaction (1-5)
- Route_Efficiency: Optimized route score
- Weather_Impact: Weather delay factor
```

**🎯 Perfect For:**
- Multi-channel campaign ROI analysis
- Customer journey mapping and churn prediction
- Regional performance benchmarking
- Delivery satisfaction correlation with retention

**📈 Project Applications:**
- Build FedEx-style campaign effectiveness dashboard
- Predict customer churn based on delivery performance
- Optimize marketing spend by regional delivery efficiency
- Create executive KPI tracking for logistics operations

#### **🚛 Transportation and Logistics Tracking Dataset**
**Kaggle Search:** `"Transportation and Logistics Tracking Dataset"`  
**Dataset ID:** `nicolemachado/transportation-and-logistics-tracking-dataset`

**📊 Dataset Overview:**
- **Size:** 50,000+ shipment tracking records
- **Features:** Real-time tracking, delivery performance, route analysis
- **Complexity:** Intermediate to advanced analytics

**🔍 Data Schema:**
```
- Shipment_ID: Tracking number
- Vehicle_Type: Transportation method
- Route_Distance: Total miles/kilometers
- Estimated_Delivery: Predicted arrival
- Actual_Delivery: Real delivery time
- Delay_Reason: Cause of delays
- Fuel_Consumption: Transportation efficiency
- Driver_Rating: Service quality score
- Congestion_Level: Traffic impact factor
- Weather_Conditions: Environmental factors
```

**🎯 Perfect For:**
- On-time delivery impact analysis
- Route optimization and efficiency modeling
- Customer satisfaction correlation studies
- Predictive delivery time algorithms

#### **🏭 Logistics Company Dataset for SQL**
**Kaggle Search:** `"Logistics Company Dataset for SQL"`  
**Dataset ID:** `aashokaacharya/logistics-company-dataset-for-sql`

**📊 Dataset Overview:**
- **Size:** Multiple related tables (Customers, Orders, Inventory, Shipments)
- **Format:** Normalized SQL database structure
- **Complexity:** Beginner to intermediate SQL practice

**🔍 Database Schema:**
```sql
-- Customers Table
Customer_ID, Company_Name, Contact_Person, Phone, Email, Address, City, Country

-- Orders Table  
Order_ID, Customer_ID, Order_Date, Required_Date, Shipped_Date, Freight, Ship_Country

-- Inventory Table
Product_ID, Product_Name, Category, Unit_Price, Units_In_Stock, Reorder_Level

-- Shipments Table
Shipment_ID, Order_ID, Carrier, Tracking_Number, Ship_Date, Delivery_Date
```

**🎯 Perfect For:**
- SQL query practice and optimization
- Database relationship analysis
- KPI calculation and reporting
- Campaign impact measurement through SQL

---

## 💊 AnovoRx (Specialty Pharma)

### 💉 **Primary Datasets**

#### **🌟 Pharma Drug Sales Dataset**
**Kaggle Search:** `"Pharma Drug Sales Dataset"`  
**Dataset ID:** `ybifoundation/pharma-drug-sales`

**📊 Dataset Overview:**
- **Size:** 600,000+ pharmaceutical transaction records
- **Time Range:** Multi-year sales and prescription data
- **Features:** Drug categories, sales volumes, geographic distribution, temporal trends

**🔍 Data Schema:**
```
- Transaction_ID: Unique sale identifier
- Drug_Name: Pharmaceutical product name
- Drug_Category: Therapeutic classification
- Prescription_Date: Date of prescription
- Quantity_Prescribed: Units prescribed
- Unit_Price: Cost per unit
- Total_Sales: Transaction value
- Pharmacy_ID: Dispensing pharmacy
- Physician_ID: Prescribing doctor
- Patient_Age_Group: Demographic segment
- Insurance_Type: Payer category
- Geographic_Region: Sales territory
- Adherence_Flag: Treatment completion indicator
```

**🎯 Perfect For:**
- Patient adherence analysis and prediction
- Prescription-to-treatment conversion tracking
- Physician engagement and prescribing patterns
- Payer performance and approval rate analysis

**📈 Project Applications:**
- Build AnovoRx-style patient adherence dashboard
- Analyze conversion rates from prescription to treatment
- Segment patients by adherence likelihood
- Track physician engagement and prescribing trends

#### **📊 Pharma Sales Data (Large Scale)**
**Kaggle Search:** `"Pharma Sales Data"`  
**Dataset ID:** `milanzdravkovic/pharma-sales-data`

**📊 Dataset Overview:**
- **Size:** 1M+ pharmaceutical sales transactions
- **Granularity:** Daily sales data with geographic segmentation
- **Complexity:** Advanced time-series and geographic analysis

**🔍 Data Schema:**
```
- Date: Daily transaction date
- Product_Code: Drug identifier
- Product_Name: Pharmaceutical name
- ATC_Code: Anatomical Therapeutic Chemical classification
- Sales_Volume: Units sold
- Sales_Value: Revenue generated
- Country: Geographic market
- Distributor: Sales channel
- Therapeutic_Area: Medical specialty
- Launch_Date: Product introduction date
```

**🎯 Perfect For:**
- Time-series forecasting and trend analysis
- Geographic market penetration studies
- Product lifecycle and adoption analysis
- Therapeutic area performance comparison

**📈 Advanced Applications:**
- Predict market demand for new drug launches
- Analyze geographic expansion opportunities
- Model seasonal prescription patterns
- Optimize distribution channel performance

---

## 🏥 ATEC Spine (Medical Devices & MedTech)

### 🦴 **Primary Datasets**

#### **🌟 Medical Device Companies Dataset**
**Kaggle Search:** `"Medical Device Companies Dataset"`  
**Dataset ID:** `mathurinache/medicaldevicecompanies`

**📊 Dataset Overview:**
- **Size:** 15,000+ medical device company records
- **Features:** Company profiles, device categories, market performance, regulatory status
- **Focus:** Device adoption trends and market analysis

**🔍 Data Schema:**
```
- Company_ID: Device manufacturer identifier
- Company_Name: Medical device company
- Device_Category: Product classification
- FDA_Approval_Date: Regulatory approval
- Market_Launch_Date: Commercial availability
- Annual_Revenue: Company financial performance
- Employee_Count: Organization size
- Geographic_Presence: Market coverage
- Device_Type: Specific product category
- Regulatory_Status: Approval and compliance
- Innovation_Score: Technology advancement rating
- Market_Share: Competitive position
```

**🎯 Perfect For:**
- Device adoption trend analysis
- Competitive market positioning
- Regulatory approval impact studies
- Innovation correlation with market success

**📈 Project Applications:**
- Build ATEC-style device adoption dashboard
- Analyze competitive positioning and market share
- Predict success likelihood for new device launches
- Track regulatory approval impact on sales

#### **🏛️ FDA Medical Device with De Novo Certification**
**Kaggle Search:** `"FDA Medical Device with De Novo Certification"`  
**Dataset ID:** `waszabbyryugami/fda-medical-device-with-de-novo-certification`

**📊 Dataset Overview:**
- **Size:** 2,000+ FDA device certification records
- **Features:** Regulatory pathway, approval timelines, device classifications
- **Complexity:** Regulatory and compliance analytics

**🔍 Data Schema:**
```
- Device_Name: FDA-approved device
- Manufacturer: Company name
- De_Novo_Number: Regulatory identifier
- Classification: Device risk category
- Approval_Date: FDA clearance date
- Indication: Medical use case
- Predicate_Device: Reference comparison
- Review_Time: Approval process duration
- Clinical_Data_Required: Evidence requirements
- Post_Market_Requirements: Ongoing obligations
```

**🎯 Perfect For:**
- Regulatory pipeline analysis
- Approval timeline prediction
- Device classification impact studies
- Market entry strategy optimization

---

## ⚕️ Campbell Clinic (Healthcare Services)

### 🏥 **Primary Datasets**

#### **🌟 Healthcare Dataset (Comprehensive)**
**Kaggle Search:** `"Healthcare Dataset"`  
**Dataset ID:** `prasad22/healthcare-dataset`

**📊 Dataset Overview:**
- **Size:** 55,000+ synthetic patient records
- **Features:** Demographics, treatments, outcomes, satisfaction, engagement
- **Privacy:** HIPAA-compliant synthetic data

**🔍 Data Schema:**
```
- Patient_ID: Unique patient identifier
- Age: Patient age
- Gender: Patient gender
- Medical_Condition: Primary diagnosis
- Treatment_Type: Intervention category
- Admission_Date: Service start date
- Discharge_Date: Service completion
- Hospital_Stay_Days: Length of treatment
- Billing_Amount: Treatment cost
- Insurance_Provider: Payer information
- Satisfaction_Score: Patient satisfaction (1-10)
- Readmission_Flag: Return visit indicator
- Physician_ID: Treating provider
- Department: Medical specialty
- Outcome_Status: Treatment result
```

**🎯 Perfect For:**
- Patient segmentation and persona development
- Treatment outcome analysis
- Satisfaction correlation studies
- Service line performance comparison

**📈 Project Applications:**
- Build Campbell Clinic-style patient analytics dashboard
- Analyze treatment outcomes by specialty
- Predict patient satisfaction and retention
- Optimize service line resource allocation

#### **🏥 Health Insurance Marketplace Dataset**
**Kaggle Search:** `"Health Insurance Marketplace Dataset"`  
**Dataset ID:** `hhs/health-insurance-marketplace`

**📊 Dataset Overview:**
- **Size:** 3M+ insurance marketplace records
- **Features:** Plan details, enrollment data, geographic coverage, pricing
- **Scope:** National healthcare insurance market analysis

**🔍 Data Schema:**
```
- State: Geographic location
- County: Local market area
- Plan_ID: Insurance plan identifier
- Plan_Name: Insurance product name
- Issuer_Name: Insurance company
- Plan_Type: Coverage category
- Metal_Tier: Plan level (Bronze, Silver, Gold, Platinum)
- Premium: Monthly cost
- Deductible: Out-of-pocket threshold
- Network_Size: Provider count
- Enrollment_Count: Subscribers
- Rating_Area: Pricing region
```

**🎯 Perfect For:**
- Insurance market analysis
- Patient acquisition cost modeling
- Payer mix optimization
- Geographic market penetration studies

---

## 🎯 Cross-Industry Analytics Datasets

### 📊 **Universal Marketing Analytics**

#### **📈 Marketing Campaign Performance Dataset**
**Kaggle Search:** `"Marketing Campaign Performance Dataset"`  
**Multiple Options Available**

**🎯 Perfect For:**
- Cross-channel campaign analysis
- ROI optimization studies
- Attribution modeling
- Customer journey mapping

#### **👥 Customer Segmentation Dataset**
**Kaggle Search:** `"Customer Segmentation Dataset"`  
**Multiple Variations Available**

**🎯 Perfect For:**
- RFM analysis and customer scoring
- Behavioral segmentation
- Lifetime value modeling
- Persona development

---

## 🔍 Dataset Selection Matrix

| Client Focus | Primary Dataset | Secondary Dataset | SQL Practice | Advanced Analytics |
|--------------|----------------|-------------------|--------------|-------------------|
| **🚚 FedEx** | Logistics and Supply Chain | Transportation Tracking | Logistics Company SQL | Delivery Prediction |
| **💊 AnovoRx** | Pharma Drug Sales | Pharma Sales Data | Healthcare SQL | Adherence Modeling |
| **🏥 ATEC Spine** | Medical Device Companies | FDA De Novo Certification | Device Analytics SQL | Adoption Prediction |
| **⚕️ Campbell Clinic** | Healthcare Dataset | Insurance Marketplace | Patient Analytics SQL | Outcome Modeling |

---

## 📥 Dataset Download & Setup Guide

### 🔧 **Step-by-Step Download Process**

#### **1. Kaggle Account Setup**
- Create free Kaggle account at [kaggle.com](https://kaggle.com)
- Verify email and complete profile setup
- Generate API token for programmatic access (optional)

#### **2. Dataset Search & Download**
```bash
# Method 1: Web Interface
1. Navigate to kaggle.com
2. Search using provided dataset names
3. Click "Download" button
4. Extract ZIP files to project directory

# Method 2: Kaggle API (Advanced)
pip install kaggle
kaggle datasets download -d [dataset-id]
unzip [dataset-name].zip
```

#### **3. Data Preparation Checklist**
- [ ] Verify data quality and completeness
- [ ] Check for missing values and outliers
- [ ] Understand data schema and relationships
- [ ] Create data dictionary for reference
- [ ] Set up appropriate file structure for analysis

### 📊 **Data Quality Assessment Template**

```python
# Standard data exploration script
import pandas as pd
import numpy as np

# Load dataset
df = pd.read_csv('dataset_name.csv')

# Basic information
print("Dataset Shape:", df.shape)
print("\nColumn Data Types:")
print(df.dtypes)

# Missing values analysis
print("\nMissing Values:")
print(df.isnull().sum())

# Basic statistics
print("\nDescriptive Statistics:")
print(df.describe())

# Unique values in categorical columns
categorical_cols = df.select_dtypes(include=['object']).columns
for col in categorical_cols:
    print(f"\n{col} - Unique Values: {df[col].nunique()}")
    print(df[col].value_counts().head())
```

---

## 🎯 Learning Path Recommendations

### 📅 **Beginner Path (Weeks 1-4)**
1. **Week 1:** Start with Logistics Company SQL Dataset for basic query practice
2. **Week 2:** Move to Healthcare Dataset for patient analytics fundamentals
3. **Week 3:** Explore Pharma Drug Sales for time-series analysis
4. **Week 4:** Practice with Medical Device Companies for competitive analysis

### 📅 **Intermediate Path (Weeks 5-8)**
1. **Week 5:** Logistics and Supply Chain Dataset for advanced dashboard building
2. **Week 6:** Pharma Sales Data for geographic and temporal analysis
3. **Week 7:** FDA Medical Device Dataset for regulatory analytics
4. **Week 8:** Insurance Marketplace Dataset for market analysis

### 📅 **Advanced Path (Weeks 9-12)**
1. **Week 9:** Transportation Tracking Dataset for predictive modeling
2. **Week 10:** Combined pharma datasets for comprehensive patient journey analysis
3. **Week 11:** Multi-dataset integration for cross-industry insights
4. **Week 12:** Custom dataset creation and advanced analytics projects

---

## 🚀 Project Implementation Framework

### 📊 **Standard Project Structure**
```
project_name/
├── data/
│   ├── raw/                 # Original Kaggle datasets
│   ├── processed/           # Cleaned and transformed data
│   └── external/            # Additional reference data
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_analysis.ipynb
│   └── 04_visualization.ipynb
├── src/
│   ├── data_processing.py
│   ├── analysis.py
│   └── visualization.py
├── dashboards/
│   ├── tableau_workbooks/
│   ├── powerbi_reports/
│   └── streamlit_apps/
├── sql/
│   ├── data_exploration.sql
│   ├── kpi_calculations.sql
│   └── segmentation_queries.sql
└── documentation/
    ├── data_dictionary.md
    ├── methodology.md
    └── results_summary.md
```

### 🎯 **Success Metrics by Dataset Type**

#### **📊 Logistics Datasets**
- [ ] Build interactive delivery performance dashboard
- [ ] Predict customer churn with 80%+ accuracy
- [ ] Identify optimization opportunities worth 15%+ cost reduction
- [ ] Create executive-ready ROI analysis

#### **💊 Pharma Datasets**
- [ ] Develop patient adherence prediction model
- [ ] Analyze prescription-to-treatment conversion rates
- [ ] Segment patients by engagement likelihood
- [ ] Create HIPAA-compliant reporting framework

#### **🏥 MedTech Datasets**
- [ ] Model device adoption lifecycle
- [ ] Predict regulatory approval timelines
- [ ] Analyze competitive market positioning
- [ ] Create physician engagement scoring system

#### **⚕️ Healthcare Service Datasets**
- [ ] Build patient satisfaction prediction model
- [ ] Analyze treatment outcome correlations
- [ ] Optimize service line resource allocation
- [ ] Create community engagement ROI framework

---

## 🔗 Additional Resources

### 📚 **Dataset Documentation**
- Comprehensive data dictionaries for each recommended dataset
- Schema diagrams and relationship mappings
- Data quality assessment reports
- Best practice guides for each industry vertical

### 🛠️ **Analysis Templates**
- Jupyter notebook templates for each dataset type
- SQL query libraries optimized for specific schemas
- Tableau and Power BI dashboard templates
- Python analysis scripts with industry-specific metrics

### 📈 **Advanced Analytics Extensions**
- Machine learning model templates for each vertical
- Time-series forecasting frameworks
- Customer segmentation algorithms
- Predictive analytics pipelines

---

**🎯 Ready to dive into real-world data analysis? Start with your preferred client vertical and begin building expertise with industry-relevant datasets that directly translate to client value!**

---

*📧 Need help with specific dataset setup, data quality issues, or custom analysis approaches? Let's create targeted solutions that accelerate your learning and maximize analytical impact!*
