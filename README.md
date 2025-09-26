# Azure Data Factory & DevOps Retail-Sales-Analytics End-to-End Project 🚀

## 📖 Project Overview
This was my **first data engineering project on Azure**, built with the primary purpose of **learning** and practicing real-world workflows in Azure.  
All datasets used in this project are **dummy data generated for demonstration purposes only**.  

The project demonstrates an **end-to-end data engineering solution** on **Azure**, integrated with **CI/CD pipelines** in **Azure DevOps**.  
The solution ingests raw data from multiple sources, transforms it using ADF Data Flows, and loads it into a **Data Lake** and **SQL Database** for analytics.  

The project follows **industry best practices** with **separate Dev, Test, and Prod environments** and automated deployments.  

---

## 🏗️ Architecture
- **Resource Group** containing:
  - Azure Data Factory (Dev, Test, Prod)
  - Azure Data Lake Storage Gen2 (Dev, Test, Prod)
  - Azure Blob Storage (Dev, Test, Prod)
  - Azure SQL Database (Dev, Test, Prod)
  - Azure Key Vault (for secrets)
- **Azure DevOps Pipelines** for CI/CD



---

## ⚙️ Data Factory Components
- **Pipelines** for orchestration  
- **Triggers** (Tumbling Window for scheduled loads)  
- **Activities**:
  - Copy Activity
  - Lookup Activity
  - For Each Activity
- **Transformations**:
  - Aggregate, Join, Select
  - Sorter, Derived Column
  - Sink & Source  
- **Data Flows** for data transformation

---

## 🔄 Data Pipeline Workflow
1. **Source Data** (dummy datasets):  
   - Customers (CSV)  
   - Products (JSON)  
   - Sales (CSV)  
   - Exchange Rates (JSON)  
   - Country-Currency mapping (CSV)  

2. **Transformations**:  
   - Join customers, sales, and product data  
   - Convert currencies to USD using exchange rates  
   - Derive `TotalSpendUSD` per customer and `TotalRevenueUSD` per product  
   - Aggregate data for reporting  

3. **Sink**:  
   - Store results in Azure Data Lake (CSV)  
   - Load curated data into Azure SQL Database for BI tools  

---

## 🚀 DevOps CI/CD Setup
- **Build Pipeline**  
  - Generates ARM templates   
- **Release Pipeline**  
  - Deploys ADF pipelines automatically to **Dev → Test → Prod**  
  - Uses **pipeline variables** to reference environment-specific resources  
- **Two Deployment Approaches**:
  1. Manual publish → Release pipeline trigger  
  2. Fully automated CI/CD (triggered after pull request approval → build → release)

---

## 📊 Expected Outputs
1. **sales_summary**: Customer-level spend in USD + number of orders  
2. **top_products**: Best-selling products by quantity and revenue  

---

## 🧰 Skills Demonstrated
- Azure Data Factory (pipelines, triggers, data flows)  
- Azure Data Lake Gen2 & Blob Storage  
- Azure SQL Database integration  
- Azure Key Vault for secure secrets management  
- CI/CD with Azure DevOps (Build & Release pipelines)  
- Infrastructure-as-Code with ARM Templates  
- Orchestration & transformation of structured/unstructured data  

---
## 📖 Documentation
1. [Azure Data Factory Documentation](https://learn.microsoft.com/en-us/azure/data-factory/)
2. [Automate continuous integration using Azure Pipelines releases](https://learn.microsoft.com/en-us/azure/data-factory/continuous-integration-delivery-automate-azure-pipelines)
3. [Sample pre- and post-deployment script](https://learn.microsoft.com/en-us/azure/data-factory/continuous-integration-delivery-sample-script)
4. [Automated publishing for CI/CD](https://learn.microsoft.com/en-us/azure/data-factory/continuous-integration-delivery-improvements)


