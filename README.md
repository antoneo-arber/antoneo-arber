# Hi there, I'm Antoneo Arber
### Senior Power BI & Business Intelligence Solutions Architect
📍 **Anna / Dallas-Fort Worth, TX** | ✉️ antoneoarber@gmail.com
---
## 🚀 About Me
Senior Business Intelligence Solutions Architect with **8+ years of enterprise experience** designing scalable analytical solutions, modern cloud data architectures, and high-performance BI ecosystems. 

Specialized in migrating legacy reporting platforms (Tableau, Alteryx, SSRS) into unified **Microsoft Fabric and Power BI** semantic layers. Proven track record of reducing operational costs by up to **$1.2M** and delivering optimized, governed analytics for **1,500+ global users**.
---
## 🛠️ Technical Stack & Core Competencies
| Technical Domain | Tools, Languages & Frameworks |
| :--- | :--- |
| **Power BI Ecosystem** | Advanced DAX, M Code, Star Schema, Power Query, Tabular Editor, DAX Studio, Performance Analyzer, Dynamic RLS/OLS, Paginated Reports, Data Activator (Reflex) |
| **Microsoft Fabric & Cloud** | OneLake, Direct Lake Mode, Dataflows Gen2, Lakehouse Architecture, Azure Data Factory (ADF), Azure Synapse Analytics, Azure SQL, Snowflake, Databricks (PySpark) |
| **Data Engineering & Languages** | T-SQL (Stored Procedures, CTEs, Window Functions, Index Tuning), Python (Pandas, PySpark), SSIS, REST API Integration |
| **Governance & DevOps** | Power BI Center of Excellence (CoE), Git Version Control, Deployment Pipelines, ALM Toolkit, Agile/Scrum Frameworks |
---
## 📁 Featured Projects & Architecture Case Studies
### 1. 📦 [Enterprise Inventory Forecasting Engine (Microsoft Fabric + Power BI)](https://github.com/antoneo-arber/fabric-direct-lake-retail-engine)
* **Business Challenge:** High annual holding costs and supply chain bottlenecks caused by fragmented data across Shopify, Google Analytics, and 15+ internal APIs.
* **Architectural Solution:**
  * Ingested real-time API data streams into a **Microsoft Fabric OneLake** Lakehouse environment using **Azure Data Factory** pipelines.
  * Engineered a predictive inventory model in Power BI using time-series DAX algorithms to forecast reorder thresholds dynamically.
  * Configured **Direct Lake Mode** connectivity to eliminate refresh delays for high-frequency inventory tracking.
* **Quantified Impact:** Eliminated manual stock audits and prevented **$1.2M+ in annual excess inventory holding costs**.
* **Key Technologies:** `Microsoft Fabric`, `Direct Lake`, `Azure Data Factory`, `Advanced DAX`, `Python (Pandas)`
```dax
// Sample DAX: Dynamic Reorder Point Calculation
Reorder_Point = 
VAR AvgDailySales = AVERAGE('Fact_Sales'[Quantity])
VAR LeadTimeDays = SELECTEDVALUE('Dim_Supplier'[Lead_Time_Days], 14)
VAR SafetyStock = [AvgDailySales] * LeadTimeDays * 0.5
RETURN
    (AvgDailySales * LeadTimeDays) + SafetyStock
```
### 2. ⚡ [Enterprise Semantic Model Optimization & Direct Lake Migration](https://github.com/antoneo-arber/powerbi-performance-optimization-toolkit)
* **Business Challenge:** Executive reports on a dataset of 20M+ rows were taking over 2 minutes to render, causing low stakeholder adoption and high server load.
* **Execution & Technical Strategy:**
  * Restructured flat, denormalized tables into a pure **Kimball Star Schema** with single-direction 1-to-many relationships.
  * Used **DAX Studio** and **Performance Analyzer** to identify bottleneck iterators (`FILTER`, `SUMX`) and replaced them with vectorized calculations.
  * Applied **Tabular Editor** scripts to automate calculation group creation and enforced query folding across all upstream Power Query layers.
* **Quantified Impact:** Reduced dashboard load times from **2 minutes to <5 seconds** and maintained **99.5% reporting uptime** for 1,500+ users.
* **Key Technologies:** `DAX Studio`, `Tabular Editor`, `Performance Analyzer`, `Direct Lake Mode`, `Power BI Premium`
```sql
-- Sample T-SQL: Query Folding & Aggregation View for Semantic Layer
CREATE VIEW [bi].[vw_Fact_Sales_Summary] AS
SELECT 
    CAST(TransactionDate AS DATE) AS SalesDate,
    ProductID,
    StoreID,
    COUNT(TransactionID) AS TotalTransactions,
    SUM(SalesAmount) AS TotalRevenue,
    SUM(MarginAmount) AS TotalMargin
FROM [dbo].[Raw_Transactions]
GROUP BY CAST(TransactionDate AS DATE), ProductID, StoreID;
```
### 3. 🛡️ [Multi-Tenant Financial Risk & Operational Performance Hub](https://github.com/antoneo-arber/powerbi-dynamic-rls-governance-framework)
* **Business Challenge:** C-suite stakeholders required real-time financial risk dashboards, but multi-tenant healthcare and finance data required strict HIPAA and FINRA compliance.
* **Execution:**
  * Developed dynamic **Row-Level Security (RLS)** and **Object-Level Security (OLS)** roles integrated with Azure Active Directory (Microsoft Entra ID) user groups.
  * Modernized 300+ legacy Tableau workbooks and Alteryx workflows into streamlined Power BI semantic models and ADF pipelines.
  * Integrated **Power Automate** alerts triggered when quarterly forecast variance exceeded target safety limits.
* **Quantified Impact:** Improved quarterly forecasting accuracy by **18%** and delivered secure, real-time KPI tracking across global business units.
* **Key Technologies:** `Power BI Desktop/Service`, `Dynamic RLS/OLS`, `Power Automate`, `Azure Data Factory`, `SSAS Cubes`
```dax
// Sample DAX: Dynamic Row-Level Security Filter
[User_Security_Filter] = 
LOOKUPVALUE(
    'User_Security_Mapping'[Access_Region],
    'User_Security_Mapping'[User_Email], USERPRINCIPALNAME(),
    'User_Security_Mapping'[Access_Region], 'Dim_Store'[Region]
)
```
---
### 4. 🏢 [Center of Excellence (CoE) & Self-Service BI Governance Framework](https://github.com/antoneo-arber/powerbi-coe-self-service-governance)
* **Business Challenge:** Unregulated report creation across departments resulted in duplicate metrics, inconsistent KPI definitions, and high IT ad-hoc ticket volume.
* **Execution:**
  * Established an enterprise **Power BI Center of Excellence (CoE)** for 300+ business analysts.
  * Designed standardized, certified semantic models and workspace governance policies.
  * Built **Git-integrated CI/CD deployment pipelines** (Dev -> Test -> Prod) using **ALM Toolkit** to manage version control and deployment lifecycle.
* **Quantified Impact:** Reduced ad-hoc IT report requests by **85%** and established a single source of truth for corporate reporting.
* **Key Technologies:** `Power BI Governance`, `Deployment Pipelines`, `Git`, `ALM Toolkit`, `Dataflows Gen2`
---
## 📜 Certifications
* **Microsoft Certified:** Fabric Analytics Engineer Associate (`DP-600`)
* **Microsoft Certified:** Power BI Data Analyst Associate (`PL-300`)
* **Microsoft Certified:** Azure Data Engineer Associate (`DP-203`)
* **Google:** Data Analytics Professional Certificate
---
## 🎓 Education
* **Master of Business Intelligence & AI** — University of Dallas
* **Bachelor of Business Administration (BBA)**
---
## 📬 Connect & Collaborate
* 📧 **Email:** [antoneoarber@gmail.com](mailto:antoneoarber@gmail.com)
* 📍 **Location:** Anna / Dallas-Fort Worth, TX
