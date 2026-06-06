# Talend CRM Excel ETL Demo

![Talend Studio](https://img.shields.io/badge/Talend%20Studio-8.0-F47C20?style=for-the-badge)
![ETL Pipeline](https://img.shields.io/badge/ETL-Pipeline-0078D4?style=for-the-badge)
![Excel Source](https://img.shields.io/badge/Excel-Source-217346?style=for-the-badge)
![Data Transformation](https://img.shields.io/badge/Data-Transformation-FFB000?style=for-the-badge)
![tMap](https://img.shields.io/badge/tMap-Mapping-FFCC00?style=for-the-badge)
![tLogRow](https://img.shields.io/badge/tLogRow-Logging-00C853?style=for-the-badge)
![Java](https://img.shields.io/badge/Java-Runtime-ED8B00?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge)

---

## Project Overview

This project demonstrates a simple ETL (Extract, Transform, Load) workflow developed using Talend Open Studio 8.

The objective of this project is to read CRM data from an Excel spreadsheet, perform column mapping and transformation using Talend's tMap component, and print the transformed data into the Talend console using tLogRow.

<img width="1179" height="451" alt="image" src="https://github.com/user-attachments/assets/e3b7c72e-924d-4885-966e-7ed4371b9012" />


This project was created as a beginner ETL demonstration to understand:

* Data Extraction
* Data Transformation
* Data Mapping
* ETL Workflow Design
* Talend Components
* Logging and Validation

---

# Architecture Diagram

```text
+------------------+
| Excel File (.xlsx)|
+---------+--------+
          |
          v
+------------------+
| tFileInputExcel  |
| Read Source Data |
+---------+--------+
          |
          v
+------------------+
|      tMap        |
| Transform & Map  |
+---------+--------+
          |
          v
+------------------+
|    tLogRow       |
| Print Output Log |
+------------------+
```

---

# Workflow

```text
Excel File
    |
    v
tFileInputExcel
    |
    v
tMap
    |
    v
tLogRow
```

---

# Talend Components Used

| Component       | Purpose                       |
| --------------- | ----------------------------- |
| tFileInputExcel | Reads data from Excel file    |
| tMap            | Maps and transforms columns   |
| tLogRow         | Displays transformed records  |
| PreJob          | Executes initialization tasks |
| PostJob         | Executes cleanup tasks        |

---

# Project Structure

```text
talend-crm-excel-etl-demo
│
├── screenshots
│   ├── 01_new_job_creation.png
│   ├── 02_job_design.png
│   ├── 03_excel_configuration.png
│   ├── 04_tmap_mapping.png
│   ├── 05_tlogrow_configuration.png
│   └── 06_execution_result.png
│
├── sample-data
│   └── crm_data.xlsx
│
├── talend-job
│   └── Talend Project Files
│
└── README.md
```

---

# Step 1 - Create Talend Job

Created a new Talend Job named:

```text
Load_And_Print_CRM_Data_From_Excel
```

Purpose:

```text
Load CRM data from Excel and print transformed records into Talend log.
```

### Screenshot

```markdown
<img width="1179" height="374" alt="image" src="https://github.com/user-attachments/assets/b95ca380-1b82-4428-b0a4-9f40b70a9581" />
```

---

# Step 2 - Design Job Flow

Designed the ETL workflow using Talend components.

Flow:

```text
tFileInputExcel
      |
      v
     tMap
      |
      v
   tLogRow
```

### Screenshot

```markdown
<img width="1179" height="451" alt="image" src="https://github.com/user-attachments/assets/5a2ade6c-6e67-4ba4-beb0-d7bcdba42f5a" />
```

---

# Step 3 - Configure tFileInputExcel

Configured tFileInputExcel component to read CRM data from Excel file.

Key Settings:

* File Format: XLSX
* Source Type: Excel Spreadsheet
* Header Configuration
* Schema Definition
* Column Mapping

### Screenshot

```markdown
<img width="1179" height="776" alt="image" src="https://github.com/user-attachments/assets/15402970-9b0b-42ac-9c3c-4852eb62a8bb" />
```

---

# Step 4 - Configure tMap

Used tMap component to perform data mapping between source and target schemas.

Source Columns:

* Country
* Total
* C3GroupGrievance

Target Columns:

* Total
* C3GroupGrievance
* S1DemographicPressures

Activities Performed:

* Column Mapping
* Data Transformation
* Schema Alignment

### Screenshot

```markdown
<img width="1179" height="618" alt="image" src="https://github.com/user-attachments/assets/a23ba2ff-34d5-4c7e-93dc-b90f9780e08d" />

```

---

# Step 5 - Configure tLogRow

Configured tLogRow component to display output in tabular format.

Settings:

* Mode: Table
* Print Content with Log4j: Enabled

### Screenshot

```markdown
![tLogRow Configuration](screenshots/05_tlogrow_configuration.png)
```
<img width="1179" height="474" alt="image" src="https://github.com/user-attachments/assets/3f665361-3f81-4ff7-b4fa-0acaa82539ea" />
---

# Step 6 - Execute Job

Executed the Talend Job successfully.

Result:

* Data extracted from Excel
* Data mapped using tMap
* Records printed using tLogRow

### Screenshot

```markdown
<img width="1179" height="827" alt="image" src="https://github.com/user-attachments/assets/9285a2ee-2c5a-4965-b449-2ac25db47880" />
```

---

# Sample Output

```text
Year | Country | Rank
2023 | Somalia | 1st
2023 | Yemen | 2nd
2023 | South Sudan | 3rd
2023 | Congo Democratic Republic | 4th
2023 | Syria | 5th
```

---

# ETL Process Breakdown

## Extract

Data is extracted from an Excel spreadsheet using tFileInputExcel.

## Transform

Data mapping and transformation are performed using tMap.

## Load

Transformed data is loaded into Talend logs using tLogRow.

---

# Skills Demonstrated

* ETL Development
* Talend Open Studio 8
* Data Integration
* Data Transformation
* Data Mapping
* Excel Processing
* Schema Management
* Data Validation
* Logging and Monitoring
* Workflow Design
* GitHub Documentation

---

# Tools & Technologies

| Technology           | Usage               |
| -------------------- | ------------------- |
| Talend Open Studio 8 | ETL Development     |
| Excel (.xlsx)        | Source Data         |
| Java                 | Runtime Engine      |
| GitHub               | Version Control     |
| tFileInputExcel      | Data Extraction     |
| tMap                 | Data Transformation |
| tLogRow              | Output Logging      |

---

# Future Enhancements

* Load transformed data into MySQL Database
* Export output to CSV
* Add Data Validation Rules
* Handle Null Values
* Implement Error Handling
* Parameterize File Paths
* Use Context Variables
* Create Reusable Jobs
* Integrate with Cloud Storage

---

# Author

Komal Mahajan

Aspiring MIS Analyst | Data Analyst | ETL Developer 

GitHub: analytics-komal

---

# Repository Topics

```text
talend
etl
data-engineering
data-integration
excel
tmap
tlogrow
talend-open-studio
crm-data
data-transformation
github-portfolio
beginner-project
data-analysis
data-cleaning
data-transformation
data-collection
sync-data
```
