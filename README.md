# 🏨 Hospitality Revenue Management Dashboard

This project delivers a comprehensive Power BI dashboard for **AtliQ Grands**, a multiple five-star hotel chain, to analyze revenue performance, operational efficiency, and customer satisfaction across 7 properties in India. The dashboard enables data-driven decision-making to address market share decline.

**🔗 [Loom video Dashboard](YOUR_DASHBOARD_LINK)**    
**📄 [Full Documentation](https://drive.google.com/file/d/1Skaamq8E4ox6_k_H264K-x7FdjCnZL02/view)**

# Dashboard
![Image](https://github.com/user-attachments/assets/49a096a3-e213-4958-a9a1-9b0158e59c0c)
![Image](https://github.com/user-attachments/assets/6620dd38-ed29-4547-9e28-14ac68b00bf5)

---

## 📑 Table of Contents

1. **Problem Statement**
   - Business challenge and context
   - Why this dashboard was needed

2. **Data Loading & Preparation**
   - Loading CSV files from folder
   - Power Query transformations
   - Data quality fixes

3. **Data Modeling**
   - Star schema design
   - Table relationships
   - Dimension and fact tables

4. **DAX Measures & Calculations**
   - Core KPIs (Revenue, Occupancy, ADR)
   - Advanced metrics (RevPAR, WoW%, Realization)
   - Business-specific calculations

5. **Dashboard Development**
   - Executive summary cards
   - Trend analysis visuals
   - Property performance matrix
   - Interactive filters

6. **Key Insights & Recommendations**
   - Critical issues identified
   - Opportunities discovered
   - Strategic action plan

---

## 🎯 Problem Statement

### Situation
AtliQ Grand, a multiple five-star hotel chain, noticed a **loss in market share** and wanted to address this issue through data-driven insights.

### Task
Provide an end-to-end dashboard that helps management make informed decisions by tracking:
- Revenue by category (Luxury vs Business)
- Trends by key metrics (occupancy, ADR, RevPAR)
- Property performance comparison
- Booking platform effectiveness
- Week-over-week changes

### Solution Delivered
Built a comprehensive Power BI dashboard analyzing **₹20.79M revenue** across **92 days** and **7 properties**, with **26+ DAX measures** tracking all critical KPIs.

---

## 📊 Dataset Information

| Dataset | Records | Description |
|---------|---------|-------------|
| dim_date | 92 rows | Date dimension with week numbers |
| dim_hotels | 7 rows | Property details (name, city, category) |
| dim_rooms | 4 rows | Room types and classifications |
| fact_bookings | 2,576+ rows | Transaction-level booking records |
| fact_aggregated_bookings | Daily records | Capacity and successful bookings |

**Data Period:** May - July (3 months)  
**Properties:** 7 hotels across Delhi, Mumbai, Hyderabad, Bangalore  
**Categories:** Luxury and Business class hotels

---

## 🛠️ Tools & Technologies Used

| Technology | Purpose |
|------------|---------|
| Power BI Desktop | Dashboard development and visualization |
| Power Query | Data transformation and ETL |
| DAX | Advanced calculations and measures |
| Excel/CSV | Source data files |

---

## 🔄 Project Workflow

### 1. Data Loading & Preparation
- Created folder with all 5 CSV files
- Used "Get Data → Folder" option in Power BI
- Duplicated data source 4 times for each table
- Expanded datasets using "Binary" option

### 2. Power Query Transformations
- **dim_date:** Removed original `day_type` column (incorrect weekend definition)
- **dim_rooms:** Applied "Use First Row as Headers" to fix missing headers
- Validated data types across all tables
- Handled missing values and inconsistencies

### 3. Data Modeling
- Built **Star Schema** architecture
- Created relationships: dimensions → fact tables
- Established one-to-many cardinality
- Optimized for query performance

### 4. DAX Calculations
Created **26+ measures** including:
- Revenue, Total Bookings, Capacity
- Occupancy %, ADR, RevPAR, Realization %
- DBRN, DSRN, DURN
- Cancellation %, No Show Rate %
- Week-over-Week % changes for all KPIs

### 5. Dashboard Design
- Executive summary with KPI cards
- Revenue distribution by category (donut chart)
- Trend analysis (line chart with multiple metrics)
- Day type performance comparison table
- Platform performance analysis
- Detailed property-level matrix
- Interactive filters (City, Room Class, Week)

---

## 📈 Key Metrics Explained

| Metric | Formula | Business Meaning |
|--------|---------|------------------|
| **Revenue** | Sum of revenue_realized | Total money received by hotels |
| **Occupancy %** | Successful bookings ÷ Total capacity | Room utilization rate |
| **ADR** | Revenue ÷ Total bookings | Average price per room sold |
| **RevPAR** | Revenue ÷ Total capacity | Revenue per available room |
| **Realization %** | 1 - (Cancellation % + No Show %) | Successful revenue conversion |
| **DSRN** | Total capacity ÷ Number of days | Daily sellable room nights |

---

## 💡 Key Insights Discovered

### Critical Issues Identified
✔ **17.9% WoW Revenue Decline** - Urgent intervention needed  
✔ **24.5% Cancellation Rate** - Significant revenue leakage  
✔ **51% Occupancy** - Nearly 50% capacity unutilized  
✔ **3.57 Average Rating** - Below industry standard (4.0+)

### Opportunities Found
✔ **Luxury segment** contributes **62.45% of revenue** (focus area)  
✔ **Direct bookings** achieve **75% realization** vs 68% through OTAs  
✔ **Weekend occupancy** is **13.8% higher** than weekdays  
✔ **Top property** (Atliq Bay) achieves **₹5,127 RevPAR** benchmark

### Revenue Opportunity
- **₹20M+ potential** from improving 51% occupancy to 70%
- **₹5M+ savings** possible by reducing 24.5% cancellation rate
- **6-8% revenue gain** by shifting bookings to direct channels

---

## 🎯 Strategic Recommendations

### Immediate Actions (0-30 Days)
- Implement **dynamic pricing** for weekends vs weekdays
- Launch **direct booking incentive** campaign (leveraging 75% realization)
- Review **cancellation policies** to reduce 24.5% rate
- Target mid-week **promotional campaigns** to boost occupancy

### Short-term Initiatives (30-90 Days)
- **Service quality improvement** program (target 4.0+ rating)
- **OTA commission negotiation** or reduce dependency
- **Luxury segment expansion** (given 62.45% revenue contribution)
- **Weekend pricing premium** strategy implementation

### Long-term Strategy (90+ Days)
- Deploy **revenue management system** with automated pricing
- **Capacity optimization** to utilize 49% idle inventory
- **Market expansion** in high-performing cities
- Develop **loyalty program** to increase direct bookings

---

## 🚧 Challenges Faced & Solutions

### Challenge 1: Incorrect Weekend Definition
**Problem:** Dataset had Saturday-Sunday as weekends, but hospitality industry uses Friday-Saturday  
**Solution:** Deleted original `day_type` column and recreated using DAX with correct logic

### Challenge 2: Missing Column Headers
**Problem:** dim_rooms CSV didn't auto-detect headers properly  
**Solution:** Applied "Use First Row as Headers" transformation in Power Query

### Challenge 3: Complex Revenue Logic
**Problem:** Different revenue realization for cancelled (40%) vs completed (100%) bookings  
**Solution:** Used pre-calculated `revenue_realized` column and built conditional measures

### Challenge 4: Week-over-Week Calculations
**Problem:** Dynamic WoW% needed to work with slicer selections  
**Solution:** Implemented HASONEFILTER and variable-based DAX pattern for all 6 metrics

### Challenge 5: Performance Optimization
**Problem:** Slow refresh times with initial denormalized structure  
**Solution:** Redesigned to star schema with aggregated fact table (60% faster refresh)

---

## 🎓 Key Learning Outcomes

- How to build **end-to-end BI solutions** from raw data to insights
- **Hospitality domain knowledge** (ADR, RevPAR, DSRN, industry standards)
- **Star schema data modeling** for optimal performance
- **Advanced DAX calculations** with filter context manipulation
- Creating **executive-level dashboards** that tell a story
- Translating **data insights into business recommendations**
- Handling **real-world data quality issues** systematically

---

## 🎯 Project Impact

**Business Value Delivered:**
- ✅ Single source of truth for all stakeholders
- ✅ Real-time visibility into ₹20.79M revenue performance
- ✅ Identified ₹25M+ in revenue opportunities and cost savings
- ✅ Enabled data-driven pricing and channel decisions
- ✅ Week-over-week trend tracking for agile management

**Skills Demonstrated:**
- Power BI development
- Data modeling (star schema)
- DAX formula creation
- Business intelligence
- Hospitality domain expertise
- Problem-solving and optimization

---

## 👤 Author

**ANIKET KUMAR**  
Data Analyst | Power BI Developer | Business Intelligence Enthusiast

**Connect with me:**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aniket-kumar-995424324/)
[![Github](https://img.shields.io/badge/Portfolio-FF5722?style=flat&logo=google-chrome&logoColor=white)](https://github.com/aniketkumariitp)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](aniketkumariitp@gmail.com)

---

> 📝 *This project demonstrates end-to-end business intelligence capabilities advanced analytics, and strategic business acumen in the hospitality domain.*
