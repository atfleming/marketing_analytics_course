# 🗃️ Module 4: SQL Query Mastery
### *Cross-Client Database Analysis and KPI Calculations*

---

## 🧠 Self-Assessment Quiz

### **🗄️ SQL Mastery Check**
*Complete this quiz after finishing all three client SQL projects*

#### **🛠️ Technical Skills Assessment (20 points)**

1. **SQL Fundamentals (5 points)**
   - [ ] Can write complex SELECT statements with multiple conditions
   - [ ] Can use JOINs effectively (INNER, LEFT, RIGHT, FULL OUTER)
   - [ ] Can implement subqueries and CTEs (Common Table Expressions)
   - [ ] Can use window functions for advanced analytics
   - [ ] Can optimize queries for performance

2. **Data Aggregation & Analysis (5 points)**
   - [ ] Can use GROUP BY with HAVING clauses effectively
   - [ ] Can implement complex aggregation functions
   - [ ] Can create pivot tables using SQL
   - [ ] Can perform time-series analysis with date functions
   - [ ] Can handle NULL values appropriately

3. **Advanced SQL Features (5 points)**
   - [ ] Can create and use stored procedures
   - [ ] Can implement triggers for data validation
   - [ ] Can design efficient database indexes
   - [ ] Can use CASE statements for conditional logic
   - [ ] Can implement recursive queries when needed

4. **Database Design & Management (5 points)**
   - [ ] Can design normalized database schemas
   - [ ] Can implement referential integrity constraints
   - [ ] Can create views for data abstraction
   - [ ] Can manage user permissions and security
   - [ ] Can backup and restore databases

#### **🏢 Cross-Client Application Assessment (20 points)**

5. **FedEx Logistics Analytics (7 points)**
   - [ ] Can analyze shipping performance across regions
   - [ ] Can create delivery time trend analysis
   - [ ] Can build customer segmentation queries
   - [ ] Can calculate logistics KPIs efficiently
   - [ ] Can identify operational bottlenecks
   - [ ] Can create executive reporting queries
   - [ ] Can optimize queries for large logistics datasets

6. **AnovoRx Healthcare Analytics (7 points)**
   - [ ] Can analyze patient outcomes with HIPAA compliance
   - [ ] Can create clinical trial analysis queries
   - [ ] Can build patient cohort analysis
   - [ ] Can calculate healthcare quality measures
   - [ ] Can implement data de-identification
   - [ ] Can create regulatory reporting queries
   - [ ] Can handle longitudinal patient data

7. **ATEC Spine Medical Device Analytics (6 points)**
   - [ ] Can analyze surgical outcome patterns
   - [ ] Can create device performance comparisons
   - [ ] Can build surgeon performance analytics
   - [ ] Can calculate clinical significance measures
   - [ ] Can implement risk-adjusted outcomes
   - [ ] Can create FDA-compliant statistical queries

#### **🎯 Professional Database Skills (10 points)**

8. **Query Optimization & Performance (5 points)**
   - [ ] Can identify and resolve performance bottlenecks
   - [ ] Can use execution plans to optimize queries
   - [ ] Can implement appropriate indexing strategies
   - [ ] Can write efficient queries for large datasets
   - [ ] Can monitor and tune database performance

9. **Data Governance & Security (5 points)**
   - [ ] Can implement role-based access controls
   - [ ] Can ensure data quality through constraints
   - [ ] Can create audit trails for data changes
   - [ ] Can implement data retention policies
   - [ ] Can ensure compliance with industry regulations

### **📊 Scoring Guide**

**🏆 SQL Database Expert (45-50 points)**
- Ready for advanced machine learning and integration modules
- Can lead database analytics projects independently
- Qualified for senior database analyst/developer roles

**📈 SQL Professional (35-44 points)**
- Strong foundation for machine learning modules
- Can contribute meaningfully to database teams
- Ready for database analyst roles

**📚 SQL Developing (25-34 points)**
- Good progress, need more practice on advanced features
- Should review window functions and optimization
- Ready for junior database analyst roles with mentorship

**🔄 SQL Beginner (Below 25 points)**
- Recommend additional practice on all client projects
- Focus on fundamental SQL concepts
- Consider additional SQL courses and practice

### **🎯 Action Items Based on Score**

**If you scored 40+ points:**
- [ ] Move confidently to Machine Learning module
- [ ] Start building database portfolio projects
- [ ] Consider SQL certification (Microsoft, Oracle, PostgreSQL)

**If you scored 30-39 points:**
- [ ] Review and practice weak SQL areas
- [ ] Complete additional query optimization tutorials
- [ ] Seek feedback on database design principles

**If you scored below 30 points:**
- [ ] Repeat client projects with focus on fundamentals
- [ ] Take additional SQL courses (W3Schools, SQLBolt, Coursera)
- [ ] Practice with simpler queries before complex analysis

---

**🎯 Ready to master SQL for cross-client analytics? Follow this systematic approach to build database skills that enable advanced data analysis across all client industries!**

---

*📧 Questions about SQL techniques or need help with specific queries? SQL mastery is fundamental to all advanced analytics and opens doors to database-focused roles across industries.*

### 📊 **Expected Deliverables**
- Comprehensive SQL query library by client vertical
- Advanced segmentation and attribution queries
- Automated KPI calculation scripts
- Database optimization and performance tuning

---

## 🎯 Module Objectives

Master **SQL query writing and database analysis** across all client verticals, focusing on campaign effectiveness, segmentation, and KPI calculations for enterprise-level analytics.

### 📊 **Expected Deliverables**
- Comprehensive SQL query library by client vertical
- Advanced segmentation and attribution queries
- Automated KPI calculation scripts
- Database optimization and performance tuning

---

## 📁 Directory Structure

```
06_Module_4_SQL/
├── queries/             # SQL query files organized by client
│   ├── fedex_logistics/
│   ├── anovorx_pharma/
│   ├── atec_spine/
│   └── campbell_clinic/
├── schemas/             # Database schemas and ERD diagrams
├── practice/            # Practice exercises and solutions
└── README.md           # This guide and checklist
```

---

## ✅ Module 4 Completion Checklist

### **🔧 Database Setup (Week 7, Day 1)**
- [ ] Set up SQLite database for practice
- [ ] Install database management tool (DBeaver, DB Browser)
- [ ] Import logistics company dataset for SQL practice
- [ ] Create database connections for each client dataset
- [ ] Test basic connectivity and query execution

### **📊 Fundamental SQL Skills (Week 7, Days 1-2)**
- [ ] **Basic Query Operations**
  - [ ] SELECT statements with filtering (WHERE)
  - [ ] Sorting and limiting results (ORDER BY, LIMIT)
  - [ ] Grouping and aggregation (GROUP BY, HAVING)
  - [ ] Join operations (INNER, LEFT, RIGHT, FULL OUTER)
  - [ ] Subqueries and CTEs (Common Table Expressions)

- [ ] **Data Manipulation**
  - [ ] INSERT, UPDATE, DELETE operations
  - [ ] Data type conversions and formatting
  - [ ] String manipulation functions
  - [ ] Date/time calculations and formatting
  - [ ] NULL handling and COALESCE functions

### **🚚 FedEx Logistics Queries (Week 7, Days 2-3)**
- [ ] **Customer Segmentation Analysis**
  ```sql
  -- RFM Analysis for Customer Segmentation
  WITH rfm_calc AS (
      SELECT customer_id,
             DATEDIFF(CURRENT_DATE, MAX(order_date)) AS recency,
             COUNT(DISTINCT order_id) AS frequency,
             SUM(order_value) AS monetary
      FROM orders 
      WHERE order_date >= DATE_SUB(CURRENT_DATE, INTERVAL 12 MONTH)
      GROUP BY customer_id
  )
  SELECT customer_id, recency, frequency, monetary,
         NTILE(5) OVER (ORDER BY recency DESC) AS r_score,
         NTILE(5) OVER (ORDER BY frequency ASC) AS f_score,
         NTILE(5) OVER (ORDER BY monetary ASC) AS m_score
  FROM rfm_calc;
  ```

- [ ] **Campaign ROI Analysis**
  ```sql
  -- Campaign Performance with ROI Ranking
  SELECT campaign_id, campaign_name,
         SUM(revenue) AS total_revenue,
         SUM(spend) AS total_spend,
         ROUND(SUM(revenue) / NULLIF(SUM(spend), 0), 2) AS roi,
         RANK() OVER (ORDER BY SUM(revenue) / NULLIF(SUM(spend), 0) DESC) AS roi_rank
  FROM campaign_results cr
  JOIN campaigns c ON cr.campaign_id = c.id
  WHERE campaign_date >= DATE_SUB(CURRENT_DATE, INTERVAL 6 MONTH)
  GROUP BY campaign_id, campaign_name
  ORDER BY roi DESC;
  ```

- [ ] **Churn Prediction Features**
  ```sql
  -- Customer Churn Risk Indicators
  SELECT customer_id,
         AVG(shipment_frequency) AS avg_monthly_shipments,
         AVG(satisfaction_score) AS avg_satisfaction,
         COUNT(DISTINCT service_type) AS service_diversity,
         DATEDIFF(CURRENT_DATE, MAX(shipment_date)) AS days_since_last_shipment,
         CASE 
           WHEN DATEDIFF(CURRENT_DATE, MAX(shipment_date)) > 90 THEN 'High Risk'
           WHEN DATEDIFF(CURRENT_DATE, MAX(shipment_date)) > 30 THEN 'Medium Risk'
           ELSE 'Low Risk'
         END AS churn_risk_category
  FROM customer_shipments
  GROUP BY customer_id;
  ```

### **💊 AnovoRx Pharma Queries (Week 7, Days 3-4)**
- [ ] **Patient Adherence Analysis**
  ```sql
  -- Adherence Rates by Treatment Program
  SELECT treatment_program,
         COUNT(DISTINCT patient_id) AS total_patients,
         ROUND(AVG(adherence_rate), 2) AS avg_adherence,
         COUNT(CASE WHEN adherence_rate >= 0.8 THEN 1 END) AS high_adherence_count,
         ROUND(COUNT(CASE WHEN adherence_rate >= 0.8 THEN 1 END) * 100.0 / COUNT(*), 2) AS high_adherence_pct
  FROM patient_adherence pa
  JOIN treatment_programs tp ON pa.program_id = tp.program_id
  WHERE start_date >= DATE_SUB(CURRENT_DATE, INTERVAL 12 MONTH)
  GROUP BY treatment_program
  ORDER BY avg_adherence DESC;
  ```

- [ ] **Speed-to-Treatment Analysis**
  ```sql
  -- Time from Prescription to Treatment Start
  SELECT patient_id, prescription_date, treatment_start_date,
         DATEDIFF(treatment_start_date, prescription_date) AS days_to_treatment,
         payer_type, treatment_program,
         CASE 
           WHEN DATEDIFF(treatment_start_date, prescription_date) <= 7 THEN 'Fast Track'
           WHEN DATEDIFF(treatment_start_date, prescription_date) <= 21 THEN 'Standard'
           ELSE 'Delayed'
         END AS speed_category
  FROM patient_treatments pt
  JOIN prescriptions p ON pt.patient_id = p.patient_id
  ORDER BY days_to_treatment;
  ```

- [ ] **Payer Performance Analysis**
  ```sql
  -- Insurance Payer Approval Rates and Processing Times
  SELECT payer_name,
         COUNT(*) AS total_requests,
         SUM(CASE WHEN approval_status = 'Approved' THEN 1 ELSE 0 END) AS approved_count,
         ROUND(SUM(CASE WHEN approval_status = 'Approved' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 2) AS approval_rate,
         ROUND(AVG(processing_days), 1) AS avg_processing_days
  FROM payer_requests
  WHERE request_date >= DATE_SUB(CURRENT_DATE, INTERVAL 3 MONTH)
  GROUP BY payer_name
  HAVING COUNT(*) >= 10
  ORDER BY approval_rate DESC;
  ```

### **🏥 ATEC Spine MedTech Queries (Week 7, Days 4-5)**
- [ ] **Surgeon Performance Analysis**
  ```sql
  -- Procedure Volume and Outcome Analysis by Surgeon
  SELECT s.surgeon_name, s.specialty,
         COUNT(p.procedure_id) AS total_procedures,
         ROUND(AVG(p.procedure_duration_minutes), 0) AS avg_duration,
         ROUND(AVG(po.outcome_score), 2) AS avg_outcome_score,
         COUNT(DISTINCT p.device_type) AS device_types_used,
         RANK() OVER (ORDER BY COUNT(p.procedure_id) DESC) AS volume_rank
  FROM surgeons s
  LEFT JOIN procedures p ON s.surgeon_id = p.surgeon_id
  LEFT JOIN procedure_outcomes po ON p.procedure_id = po.procedure_id
  WHERE p.procedure_date >= DATE_SUB(CURRENT_DATE, INTERVAL 12 MONTH)
  GROUP BY s.surgeon_id, s.surgeon_name, s.specialty
  ORDER BY total_procedures DESC;
  ```

- [ ] **Device Adoption Tracking**
  ```sql
  -- New Device Adoption Rates and Success Metrics
  SELECT d.device_name, d.launch_date,
         COUNT(DISTINCT p.surgeon_id) AS adopting_surgeons,
         COUNT(p.procedure_id) AS total_procedures,
         ROUND(AVG(po.patient_satisfaction), 2) AS avg_satisfaction,
         COUNT(CASE WHEN po.complication_flag = 0 THEN 1 END) AS successful_procedures,
         ROUND(COUNT(CASE WHEN po.complication_flag = 0 THEN 1 END) * 100.0 / COUNT(p.procedure_id), 2) AS success_rate
  FROM devices d
  JOIN procedures p ON d.device_id = p.device_id
  JOIN procedure_outcomes po ON p.procedure_id = po.procedure_id
  WHERE d.launch_date >= DATE_SUB(CURRENT_DATE, INTERVAL 24 MONTH)
  GROUP BY d.device_id, d.device_name, d.launch_date
  ORDER BY success_rate DESC;
  ```

### **⚕️ Campbell Clinic Healthcare Queries (Week 7, Days 5-6)**
- [ ] **Event ROI Analysis**
  ```sql
  -- Community Event Impact and Conversion Analysis
  SELECT e.event_name, e.event_date, e.event_location,
         COUNT(DISTINCT ea.attendee_id) AS total_attendance,
         COUNT(DISTINCT np.patient_id) AS new_patients,
         ROUND(COUNT(DISTINCT np.patient_id) * 100.0 / COUNT(DISTINCT ea.attendee_id), 2) AS conversion_rate,
         SUM(np.estimated_lifetime_value) AS projected_value,
         ROUND(SUM(np.estimated_lifetime_value) / e.event_cost, 2) AS roi_multiple
  FROM events e
  LEFT JOIN event_attendance ea ON e.event_id = ea.event_id
  LEFT JOIN new_patients np ON ea.attendee_id = np.source_attendee_id
  WHERE e.event_date >= DATE_SUB(CURRENT_DATE, INTERVAL 12 MONTH)
  GROUP BY e.event_id, e.event_name, e.event_date, e.event_location, e.event_cost
  ORDER BY conversion_rate DESC;
  ```

- [ ] **Patient Satisfaction Analysis**
  ```sql
  -- Provider Performance and Patient Satisfaction
  SELECT provider_name, service_line,
         COUNT(*) AS total_reviews,
         ROUND(AVG(satisfaction_score), 2) AS avg_satisfaction,
         COUNT(CASE WHEN satisfaction_score >= 9 THEN 1 END) AS promoters,
         COUNT(CASE WHEN satisfaction_score <= 6 THEN 1 END) AS detractors,
         ROUND((COUNT(CASE WHEN satisfaction_score >= 9 THEN 1 END) - 
                COUNT(CASE WHEN satisfaction_score <= 6 THEN 1 END)) * 100.0 / COUNT(*), 2) AS nps_score
  FROM patient_feedback pf
  JOIN providers p ON pf.provider_id = p.provider_id
  WHERE feedback_date >= DATE_SUB(CURRENT_DATE, INTERVAL 3 MONTH)
  GROUP BY provider_id, provider_name, service_line
  HAVING COUNT(*) >= 10
  ORDER BY nps_score DESC;
  ```

### **🔍 Advanced SQL Techniques (Week 7, Days 6-7)**
- [ ] **Window Functions Mastery**
  - [ ] ROW_NUMBER(), RANK(), DENSE_RANK()
  - [ ] LAG(), LEAD() for time-series analysis
  - [ ] Running totals and moving averages
  - [ ] Percentile calculations (NTILE, PERCENT_RANK)

- [ ] **Complex Joins and Subqueries**
  - [ ] Self-joins for hierarchical data
  - [ ] Correlated subqueries for advanced filtering
  - [ ] EXISTS and NOT EXISTS operations
  - [ ] UNION and INTERSECT operations

- [ ] **Performance Optimization**
  - [ ] Index creation and optimization
  - [ ] Query execution plan analysis
  - [ ] Partitioning strategies
  - [ ] Query refactoring for performance

---

## 🎯 Advanced Analytics Queries

### **📊 Multi-Touch Attribution**
```sql
-- Marketing Attribution Analysis
WITH customer_journey AS (
    SELECT customer_id, touchpoint_date, channel, campaign_id,
           ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY touchpoint_date) AS touch_sequence,
           ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY touchpoint_date DESC) AS reverse_sequence
    FROM marketing_touchpoints
    WHERE touchpoint_date >= DATE_SUB(CURRENT_DATE, INTERVAL 6 MONTH)
)
SELECT channel,
       CASE 
         WHEN touch_sequence = 1 THEN 'First Touch'
         WHEN reverse_sequence = 1 THEN 'Last Touch'
         ELSE 'Middle Touch'
       END AS attribution_type,
       COUNT(*) AS touchpoint_count,
       COUNT(DISTINCT customer_id) AS unique_customers
FROM customer_journey
GROUP BY channel, attribution_type
ORDER BY channel, attribution_type;
```

### **📈 Cohort Analysis**
```sql
-- Customer Cohort Retention Analysis
WITH cohort_data AS (
    SELECT customer_id,
           DATE_FORMAT(MIN(order_date), '%Y-%m') AS cohort_month,
           PERIOD_DIFF(DATE_FORMAT(order_date, '%Y%m'), 
                      DATE_FORMAT(MIN(order_date) OVER (PARTITION BY customer_id), '%Y%m')) AS period_number
    FROM orders
    GROUP BY customer_id, DATE_FORMAT(order_date, '%Y-%m')
)
SELECT cohort_month,
       period_number,
       COUNT(DISTINCT customer_id) AS customers,
       ROUND(COUNT(DISTINCT customer_id) * 100.0 / 
             FIRST_VALUE(COUNT(DISTINCT customer_id)) OVER (PARTITION BY cohort_month ORDER BY period_number), 2) AS retention_rate
FROM cohort_data
GROUP BY cohort_month, period_number
ORDER BY cohort_month, period_number;
```

---

## 🚀 Success Criteria

### **📊 Technical Proficiency**
- [ ] Write complex queries with multiple joins and subqueries
- [ ] Optimize query performance for large datasets
- [ ] Use window functions for advanced analytics
- [ ] Create reusable query templates

### **🏢 Business Impact**
- [ ] Generate actionable insights from database analysis
- [ ] Automate KPI calculations and reporting
- [ ] Identify optimization opportunities through data analysis
- [ ] Support decision-making with data-driven recommendations

### **🎯 Query Library Development**
- [ ] Build comprehensive query library for each client
- [ ] Document query logic and business context
- [ ] Create parameterized queries for reusability
- [ ] Establish query performance benchmarks

---

## 📚 Additional Resources

### **🔗 SQL Learning Resources**
- [SQLBolt Interactive Tutorial](https://sqlbolt.com/)
- [W3Schools SQL Tutorial](https://www.w3schools.com/sql/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [MySQL Reference Manual](https://dev.mysql.com/doc/)

### **📖 Advanced SQL Books**
- "Learning SQL" by Alan Beaulieu
- "SQL Performance Explained" by Markus Winand
- "Advanced SQL" by Joe Celko

---

## 🎯 Next Steps

Upon completion of Module 4:
1. **Build Query Library:** Organize all queries by client and use case
2. **Move to Module 5:** Machine learning and predictive analytics
3. **Database Optimization:** Apply performance tuning techniques
4. **Integration Planning:** Prepare for cross-platform analytics

---

**🎯 Ready to master SQL for enterprise analytics? Build your query library systematically and focus on business-relevant insights!**
