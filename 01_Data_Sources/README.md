# 📊 Data Sources Directory
### *Kaggle Datasets and Sample Data for Client-Focused Analytics*

---

## 📁 Directory Structure

```
01_Data_Sources/
├── kaggle_datasets/           # Downloaded Kaggle datasets by client
│   ├── fedex_logistics/      # FedEx logistics and supply chain data
│   ├── anovorx_pharma/       # AnovoRx pharmaceutical datasets
│   ├── atec_spine/           # ATEC Spine medical device data
│   └── campbell_clinic/      # Campbell Clinic healthcare data
├── sample_data/              # Processed sample datasets for practice
└── client_specific/          # Custom datasets and client examples
```

---

## 🎯 Dataset Download Checklist

### **🚚 FedEx (Logistics & Supply Chain)**
- [ ] **Logistics and Supply Chain Dataset** - `datasetengineer/logistics-and-supply-chain-dataset`
- [ ] **Transportation and Logistics Tracking** - `nicolemachado/transportation-and-logistics-tracking-dataset`
- [ ] **Logistics Company SQL Dataset** - `aashokaacharya/logistics-company-dataset-for-sql`

### **💊 AnovoRx (Specialty Pharma)**
- [ ] **Pharma Drug Sales Dataset** - `ybifoundation/pharma-drug-sales`
- [ ] **Pharma Sales Data (Large Scale)** - `milanzdravkovic/pharma-sales-data`

### **🏥 ATEC Spine (Medical Devices)**
- [ ] **Medical Device Companies Dataset** - `mathurinache/medicaldevicecompanies`
- [ ] **FDA Medical Device with De Novo** - `waszabbyryugami/fda-medical-device-with-de-novo-certification`

### **⚕️ Campbell Clinic (Healthcare Services)**
- [ ] **Healthcare Dataset** - `prasad22/healthcare-dataset`
- [ ] **Health Insurance Marketplace** - `hhs/health-insurance-marketplace`

---

## 📥 Download Instructions

### **Method 1: Web Interface**
1. Visit [kaggle.com](https://kaggle.com)
2. Search for dataset using the provided names above
3. Click "Download" button
4. Extract ZIP files to appropriate client folder

### **Method 2: Kaggle API (Advanced)**
```bash
# Install Kaggle API
pip install kaggle

# Download specific dataset
kaggle datasets download -d [dataset-id]

# Extract to appropriate folder
unzip [dataset-name].zip -d kaggle_datasets/[client_folder]/
```

---

## 🔍 Data Quality Checklist

For each downloaded dataset, complete this checklist:

### **📊 Initial Assessment**
- [ ] Verify file integrity and completeness
- [ ] Check dataset size and record count
- [ ] Review column names and data types
- [ ] Identify missing values and outliers

### **📋 Documentation**
- [ ] Create data dictionary for key columns
- [ ] Document data source and collection method
- [ ] Note any data limitations or biases
- [ ] Record download date and version

### **🧹 Data Preparation**
- [ ] Clean and standardize column names
- [ ] Handle missing values appropriately
- [ ] Convert data types as needed
- [ ] Create sample datasets for practice

---

## 🎯 Next Steps

1. **Download Priority Datasets:** Start with your preferred client vertical
2. **Data Exploration:** Use the provided Python scripts in each module
3. **Quality Assessment:** Complete the checklist for each dataset
4. **Begin Analysis:** Move to Module 1 (Tableau) when data is ready

---

**📧 Need help with specific datasets or data quality issues? Check the Kaggle Dataset Reference Guide in `00_Planning_Guide/`**
