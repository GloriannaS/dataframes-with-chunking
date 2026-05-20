# Python Data Engineering: Memory Optimization & Chunking

This repository contains two projects focused on processing large datasets within constrained memory environments. Both projects demonstrate the use of **pandas** for data transformation and **chunking** strategies to handle datasets that exceed available RAM.

---

## 1. Data Cleaning & SQLite Integration: Crunchbase Investments

This project focuses on the end-to-end ETL (Extract, Transform, Load) process. We take a messy, inconsistent dataset and transform it into a lean, queryable SQLite database to uncover trends in the venture capital landscape.

**Key Objectives:**

* **Schema Consistency:** Resolved data type fluctuations across chunks by explicitly defining schemas, preventing "mixed-type" errors common in large CSVs.
* **Numeric Downcasting:** Optimized storage by converting standard 64-bit integers and floats into compact 16-bit and 32-bit formats.
* **Low-Cardinality Categorization:** Reduced memory footprint by converting repetitive string columns into the `category` datatype.
* **Database Integration:** Streamlined the data flow from Python "staging" directly into **SQLite** using chunked appending.

**Key Analysis Results:**

* **Wealth Concentration:** Discovered a classic "Power Law" distribution where the **top 1% of startups raised nearly 20%** of total funds, while the bottom 10% accounted for less than 0.3%.
* **Sector Trends:** Identified **Software** as the most dominant category, with **Series-A** being the most frequent funding stage.
* **Investor Insights:** Identified top-tier firms like **Kleiner Perkins Caufield & Byers** (Total Capital) and **Marlin Equity Partners** (Average Investment) as the dataset's primary movers.

**Dataset:** October 2013 snapshot of startup fundraising rounds.
**Memory Reduction:** Optimized from **50.44 MB** to **34.37 MB**.

View this project live on Google Colab [here](https://colab.research.google.com/drive/1y6Vqb2VxwlEIGY__yEYQVqMTH1ieLRr6?usp=sharing)

---

## 2. Constraints & Benchmarking: Lending Club Financials

In this project, we simulate a highly constrained hardware environment to establish strict benchmarks for memory management. By operating under an artificial limit, we demonstrate how to maintain high-performance processing when system resources are scarce.

**Key Objectives:**

* **Constraint Simulation:** Operated under a strict **10 MB memory limit** to establish a clear "benchmark" for effective chunking.
* **Footprint Analysis:** Analyzed memory usage per chunk to identify "memory hog" columns and optimize ingestion.
* **Aggressive Downcasting:** Optimized numeric and string types with intent, demonstrating how to process data that exceeds available system memory.
* **Robust Frameworks:** Established a workflow for maintaining data integrity while achieving massive reductions in resource overhead.

**Dataset:** Peer-to-peer lending data (2007–2011) tailored from the original Lending Club dataset.
**Memory Reduction:** Optimized from nearly **60 MB** to **14.91 MB**.

View this project live on Google Colab [here](https://colab.research.google.com/drive/1-LSfnDKGJBBh6mYwEaNPdOfbZk7YorT-?usp=sharing)

---

## Technical Skills Demonstrated

* **Python Libraries:** Pandas, NumPy, SQLite3
* **Data Engineering:** ETL Pipelines, Chunking, Data Cleaning, Schema Enforcement
* **Optimization:** Memory Management, Numeric Downcasting, Category Mapping, Resource Constraint Simulation
* **Storage:** Database Schema Design and SQLite Integration
* **Data Analysis:** Exploratory Data Analysis (EDA), Statistical Distributions (Power Law), Percentile-based Wealth Concentration Analysis
