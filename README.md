# Light-weight-RPA-for-SMEs
This repository contains supplementary materials for the:
"A Lightweight Robotic Process Automation Framework for Financial Analytics in Spreadsheet-Centric SMEs"
Authors: Sumukhi Nandam and Carlos D. Paternina-Arboleda
Affiliation: San Diego State University
---
About
This project presents a modular RPA framework built in UiPath Studio that automates profit and loss computation for small and medium-sized enterprises relying on spreadsheet-based financial records. The pipeline handles structured data ingestion, validation and standardization of transaction attributes, and financial metric aggregation — all operating directly on Excel workbooks without requiring enterprise system integration or cloud infrastructure.
The framework was benchmarked against manual Excel processing across five performance dimensions (execution time, error rate, labor cost, scalability, and reporting latency). 
Repository Contents
```
rpa-smes-/
│
├── README.md
├── LICENSE
│
├── workflow/
│   └── P&L_Automation.xaml          # Sample UiPath workflow covering data ingestion,
│                                     # and P&L computation
│
├── data/
│   └── Sample_Dataset.xlsx           # Representative subset of the 300-transaction
│                                     # anonymized dataset used in the study
│
├── screenshots/
│   ├── activity-flow/                # UiPath Studio activity flow captures showing
│   │   ├── 01_data_ingestion.jpg     # the sequential pipeline structure
│   │   ├── 02_financial_computation.jpg
|   |   ├── 03_microsoft_outlook_integration.jpg
│   └── output/
│       └── email_report_sample.jpg   # Sample of the automated financial summary
│                                     # dispatched via Microsoft 365
│
└── figures/
    ├── system_architecture.tiff       # Conceptual architecture diagram
    ├── uipath_workflow.tiff           # UiPath-based workflow diagram
    ├── performance_metrics.tiff       # Manual vs RPA performance comparison
    ├── expense_distribution.tiff      # COGS distribution by product category
    ├── monthly_trend.tiff             # Monthly revenue and profitability trend
    └── scalability_analysis.tiff      # Runtime scaling behavior across transaction volumes 
```
Workflow Scope
The included `.xaml` file implements the modules of data ingestion, financial computation and email reporting:
Module	Status	Description
Data Ingestion	Included Reading structured transaction data from Excel workbooks using UiPath workbook activities; performs initial completeness checks on required fields (date, revenue, expense type)
Financial Computation	Included	Aggregates revenue and cost entries over the reporting period; derives total revenue.
Reporting & Notification	 included	Structured email dispatch via Microsoft 365 integration; a sample output is provided in `screenshots/output/`
The anomaly detection and reporting modules are described in detail in the manuscript but are not included as standalone workflow files in this repository. The email output screenshot provides a representative example of the final report delivered to stakeholders.
Dataset
The `data/` directory contains a representative subset of the anonymized simulated dataset used in the experimental evaluation. The full dataset comprises 300 transactions spanning January 15 to February 14, 2024 (27 trading days), structured across 8 columns.
Key characteristics of the full dataset:
Parameter	Value
Total transactions	300
Time horizon	2 months (Jan 15 – Feb 14, 2024)
Trading days	27 (Mon–Sat, Sundays excluded)
Product categories	6 (Bakery, Beverages, Dairy, Groceries, Personal Care, Snacks)
Mean daily revenue	$1,464.65 (σ = $444.14)
Revenue range per transaction	$3.21 – $482.07
The full dataset is available from the corresponding author upon reasonable request. 
Requirements
To run the UiPath workflow:
UiPath Studio (Community Edition — free tier is sufficient)
Microsoft Excel (local installation; the workflow uses workbook-based activities for offline processing)
Operating System: Windows 10 or later
Hardware: Consumer-grade laptop (the study was conducted without specialized computing infrastructure)
Email dispatch functionality (not included in the workflow file) additionally requires Microsoft 365 integration configured within UiPath.
Reproducing the Experiments
Clone or download this repository.
Open `workflow/PnL_Automation.xaml` in UiPath Studio.
Place the dataset file in the input path expected by the workflow (configurable within the Data Ingestion sequence).
Execute the workflow. The pipeline will read the transaction data, apply checks, and compute financial aggregates.
The workflow processes 300 transactions in approximately 2.1 minutes on a consumer-grade laptop. Detailed benchmarking methodology and replication procedures are described in the manuscript.
Figures
All figures included in this repository correspond to those presented in the manuscript. They are provided here for reference and to support transparency in the reported results.

```
License
This project is licensed under the MIT License. See `LICENSE` for details.
Contact
For questions regarding the framework, dataset access, or replication:
Sumukhi Nandam — snandam9717@sdsu.edu
Carlos D. Paternina-Arboleda — cpaternina@sdsu.edu
