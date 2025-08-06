# 🛠️ Tools Setup & Configuration
### *Complete Installation Guide for Analytics Stack*

---

## 🛠️ Required Tools Installation

### **🔧 Version Control & Development Environment**

#### **Git & GitHub Setup**
- [ ] **Install Git**
  ```bash
  # macOS (using Homebrew)
  brew install git
  
  # Windows
  # Download from: https://git-scm.com/download/win
  
  # Verify installation
  git --version
  ```

- [ ] **Configure Git**
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  git config --global init.defaultBranch main
  ```

- [ ] **Create GitHub Account**
  - [ ] Sign up at [github.com](https://github.com)
  - [ ] Set up SSH keys for secure authentication
  - [ ] Create your first repository for the learning program

- [ ] **Git Best Practices Setup**
  ```bash
  # Create .gitignore template
  echo "*.log\n*.tmp\n.DS_Store\n__pycache__/\n*.pyc" > .gitignore
  
  # Set up useful Git aliases
  git config --global alias.st status
  git config --global alias.co checkout
  git config --global alias.br branch
  git config --global alias.cm commit
  ```

### **📊 Data Visualization Tools**

| Tool | Purpose | Installation Priority |
|------|---------|---------------------|
| **📊 Tableau Desktop** | Interactive dashboards and visualizations | High |
| **⚡ Power BI Desktop** | KPI tracking and business intelligence | High |
| **🐍 Python + Jupyter** | Advanced analytics and machine learning | High |
| **🗃️ SQL Database** | Query practice and data analysis | Medium |
| **📝 VS Code** | Code editing and project management | Medium |

---

## ✅ Installation Checklist

### **📊 Tableau Desktop**
- [ ] Download Tableau Desktop (14-day free trial or student license)
- [ ] Install and activate with license key
- [ ] Test connection with sample dataset
- [ ] Install Tableau Prep Builder (optional)
- [ ] Set up Tableau Public account for sharing

**Installation Steps:**
1. Visit [tableau.com/products/desktop](https://www.tableau.com/products/desktop)
2. Download installer for your OS
3. Follow installation wizard
4. Activate with license or start trial

### **⚡ Power BI Desktop**
- [ ] Download Power BI Desktop (free)
- [ ] Install and configure initial settings
- [ ] Set up Power BI Service account
- [ ] Test with sample data connection
- [ ] Configure data refresh settings

**Installation Steps:**
1. Visit [powerbi.microsoft.com/desktop](https://powerbi.microsoft.com/desktop/)
2. Download and install Power BI Desktop
3. Create Microsoft account if needed
4. Sign in to Power BI Service

### **🐍 Python Environment**
- [ ] Install Python 3.8+ (recommend Anaconda distribution)
- [ ] Set up virtual environment for project
- [ ] Install required packages (see requirements.txt)
- [ ] Configure Jupyter Notebook/Lab
- [ ] Test installation with sample script

**Installation Steps:**
```bash
# Install Anaconda (recommended)
# Download from: https://www.anaconda.com/products/distribution

# Create project environment
conda create -n marketing_analytics python=3.9
conda activate marketing_analytics

# Install required packages
pip install pandas numpy matplotlib seaborn scikit-learn plotly jupyter kaggle
```

### **🗃️ SQL Database Setup**
- [ ] Install SQLite (lightweight option)
- [ ] Install MySQL or PostgreSQL (advanced option)
- [ ] Set up database management tool (DBeaver, pgAdmin)
- [ ] Create practice databases
- [ ] Test connection and basic queries

**SQLite Setup (Recommended for beginners):**
```bash
# SQLite comes with Python, test installation
python -c "import sqlite3; print('SQLite ready!')"

# Install DB Browser for SQLite (GUI tool)
# Download from: https://sqlitebrowser.org/
```

### **📝 Development Environment**
- [ ] Install VS Code or preferred IDE
- [ ] Install relevant extensions (Python, SQL, Markdown)
- [ ] Configure Git for version control
- [ ] Set up project workspace
- [ ] Test all integrations

**VS Code Extensions:**
- Python
- Jupyter
- SQL Tools
- Tableau (syntax highlighting)
- GitLens

---

## 📋 Configuration Files

### **requirements.txt**
```txt
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
plotly>=5.0.0
jupyter>=1.0.0
kaggle>=1.5.0
sqlalchemy>=1.4.0
openpyxl>=3.0.0
```

### **environment.yml** (Conda users)
```yaml
name: marketing_analytics
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.9
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - plotly
  - jupyter
  - pip
  - pip:
    - kaggle
```

---

## 🔧 Verification Tests

### **Test Tableau Installation**
1. Open Tableau Desktop
2. Connect to "Sample - Superstore" dataset
3. Create simple bar chart
4. Save workbook successfully

### **Test Power BI Installation**
1. Open Power BI Desktop
2. Get data from Excel sample file
3. Create basic visualization
4. Publish to Power BI Service (optional)

### **Test Python Environment**
```python
# Run this script to verify installation
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.cluster import KMeans
import plotly.express as px

print("✅ All packages imported successfully!")
print(f"Pandas version: {pd.__version__}")
print(f"NumPy version: {np.__version__}")
```

### **Test SQL Connection**
```python
import sqlite3

# Test SQLite connection
conn = sqlite3.connect(':memory:')
cursor = conn.cursor()
cursor.execute("SELECT 'SQL connection successful!' as test")
result = cursor.fetchone()
print(result[0])
conn.close()
```

---

## 🎯 Next Steps

1. **Complete Installation:** Check off all items above
2. **Download Sample Data:** Move to `01_Data_Sources/`
3. **Begin Module 1:** Start with Tableau dashboard creation
4. **Set Up Version Control:** Initialize Git repository for project

---

## 🆘 Troubleshooting

### **Common Issues**
- **Tableau License:** Use student email for free license
- **Power BI Sign-in:** Requires work/school account for full features
- **Python Packages:** Use `pip install --upgrade` for version conflicts
- **SQL Connection:** Check firewall settings for database connections

### **Getting Help**
- Tableau: [community.tableau.com](https://community.tableau.com)
- Power BI: [community.powerbi.com](https://community.powerbi.com)
- Python: [stackoverflow.com](https://stackoverflow.com) with specific error messages
- SQL: Database-specific documentation and forums

---

**🎯 Tools ready? Move to Module 1 and start building your first dashboard!**
