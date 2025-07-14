# CSI-Week-6-Assignments


# Azure Data Factory – FTP to Azure SQL Pipeline (Incremental Load)

## 🔧 Technologies Used
- Azure Data Factory
- Azure SQL Database
- FTP Server (FileZilla)
- Self-hosted Integration Runtime

## 📁 Pipeline Overview
This pipeline:
1. Extracts data from a local FTP server (`ftp_products.csv`)
2. Loads it into a staging table (`Products_Staging`)
3. Inserts only new or modified records into the `Products` table
4. Updates a watermark table (`Watermark`) for incremental logic
5. Runs daily and on the last Saturday of each month

## 🧪 Test Scenarios
- ✅ Inserted 3 rows – verified in `Products` table
- ✅ Changed `LastModifiedDate` and re-ran pipeline
- ✅ Validated incremental logic and retry mechanism

## 📤 How to Run
1. Open ADF Studio
2. Go to Pipelines → Run `FTP_Incremental_Load`
3. Monitor activity → Check Azure SQL Database tables

## 📂 Contents
- `arm_template/` – JSON templates of the ADF pipeline
- `ftp_products.csv` – Sample dataset used
- `README.md` – This file
    
