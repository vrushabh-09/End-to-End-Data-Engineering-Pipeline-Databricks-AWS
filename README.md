# End-to-End Data Engineering Pipeline: Databricks & AWS



> A robust, scalable data engineering pipeline demonstrating full and incremental ETL loads, dimensional modeling, and business intelligence integration using Databricks and AWS cloud infrastructure.

---

## Table of Contents

* [About The Project](https://www.google.com/search?q=%23about-the-project)
* [Tech Stack](https://www.google.com/search?q=%23tech-stack)
* [Getting Started](https://www.google.com/search?q=%23getting-started)
* [Usage](https://www.google.com/search?q=%23usage)
* [Configuration](https://www.google.com/search?q=%23configuration)
* [Contributing](https://www.google.com/search?q=%23contributing)
* [License](https://www.google.com/search?q=%23license)
* [Contact / Support](https://www.google.com/search?q=%23contact--support)

---

## About The Project

Modern data ecosystems require resilient architectures capable of handling both historical data dumps and daily incremental updates. This project implements a comprehensive end-to-end data engineering pipeline designed to ingest, process, and analyze data from multiple simulated business entities (Parent and Child companies).

The pipeline processes raw CSV data (orders, customers, products, and pricing), models it into a structured schema (Fact and Dimension tables), and prepares denormalized views to power an FMCG (Fast-Moving Consumer Goods) dashboard.

**Core Features:**

* **Hybrid Data Loading:** Automated handling of both Full Loads and Incremental Loads for continuous data integration.


* **Dimensional Modeling:** Structured processing of dimension tables (Customers, Products, Pricing) and fact tables (Orders).


* **Scalable Infrastructure:** Built on Databricks utilizing scalable notebook workflows and utility scripts.


* **Business Intelligence Integration:** Outputs denormalized datasets specifically tailored for FMCG dashboarding and reporting.



---

## Tech Stack

* **Databricks:** Core compute engine for executing data transformations via Notebooks.


* **AWS (Amazon Web Services):** Cloud infrastructure for distributed data storage (S3).
* **Python / PySpark:** Primary programming languages used for data manipulation and ETL logic.


* **SQL:** Utilized for data querying, catalog setup, and denormalization tasks.


* **Power BI / Tableau:** Target BI tools for consuming the final `fmcg_dashboard` reporting views.



---

## Getting Started

Follow these instructions to set up the project locally or in your cloud environment.

### Prerequisites

* A Databricks workspace (Community Edition or Enterprise).
* An AWS Account with S3 access and configured IAM roles.
* Python 3.8+ installed locally (if running external scripts).
* Git installed on your local machine.

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/vrushabh-09/End-to-End-Data-Engineering-Pipeline-Databricks-AWS.git
cd End-to-End-Data-Engineering-Pipeline-Databricks-AWS

```


2. **Upload Data to Cloud Storage:**
Upload the contents of the `0_data/` directory (including both `1_parent_company` and `2_child_company` folders) to your designated AWS S3 bucket.


3. **Import Databricks Notebooks:**
Import the `1_codes/` directory into your Databricks Workspace.



---

## Usage

To successfully execute the pipeline, the Databricks notebooks must be run in a specific sequence to ensure referential integrity between tables.

**Step 1: Environment Setup**
Initialize the catalogs and core utility functions.

```text
Run -> 1_codes/1_setup/setup_catalog.ipynb
Run -> 1_codes/1_setup/dim_date_table_creation.ipynb
Run -> 1_codes/1_setup/utilities.ipynb

```

**Step 2: Dimension Data Processing**
Process the static and slowly changing dimensions first.

```text
Run -> 1_codes/2_dimension_data_processing/1_customers_data_processing.ipynb
Run -> 1_codes/2_dimension_data_processing/2_products_data_processing.ipynb
Run -> 1_codes/2_dimension_data_processing/3_pricing_data_processing.ipynb

```

**Step 3: Fact Data Processing**
Process the transactional order data. Execute the full load first to establish the baseline, followed by the incremental load to simulate daily operations.

```text
Run -> 1_codes/3_fact_data_processing/1_full_load_fact.ipynb
Run -> 1_codes/3_fact_data_processing/2_incremental_load_fact.ipynb

```

**Step 4: Dashboarding**
Use the SQL queries provided in `2_dashboarding/denormalise_table_query_fmcg.txt` to generate the final views used for the FMCG Dashboard.

---

## Configuration

* **AWS S3 Paths:** Update the base storage paths in `1_codes/1_setup/utilities.ipynb` to point to your specific S3 buckets.


* **Cluster Configuration:** Ensure your Databricks cluster has the appropriate IAM instance profiles attached to read from and write to your S3 buckets.

---

## Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## License

Distributed under the MIT License. See `LICENSE` for more information.

---

## Contact / Support

**Vrushabh Patil**

* **Email:** vrushabhpatil97711@gmail.com
* **LinkedIn:** [Vrushabh Patil]([https://www.google.com/search?q=https://www.linkedin.com/](https://www.linkedin.com/in/patilvrushabh/))
* **Project Link:** [https://github.com/vrushabh-09/End-to-End-Data-Engineering-Pipeline-Databricks-AWS](https://github.com/vrushabh-09/End-to-End-Data-Engineering-Pipeline-Databricks-AWS)


If you encounter any issues or have questions regarding the pipeline setup, please open an issue in the repository.

---

*What specific metrics or KPIs are you planning to highlight in the final FMCG dashboard?*
