# Apache Server Log ETL Pipeline (Python \& SQL)

[![Python CI](https://github.com/Mavis0210/Apache-Log-ETL-Pipeline/actions/workflows/python-ci.yml/badge.svg)](https://github.com/Mavis0210/Apache-Log-ETL-Pipeline/actions/workflows/python-ci.yml)

### Project Overview

As a Technical Operations Engineer, I developed this Python ETL pipeline to automate Apache server log analysis. The project demonstrates how automation improves operational visibility by extracting key metrics from raw logs, supporting troubleshooting, log investigation, and reliability monitoring.

The project also includes a GitHub Actions Continuous Integration (CI) workflow that automatically validates the code whenever changes are pushed to the repository.


### The Problem

Raw server logs are messy, unstructured text files. Analyzing them manually to find security threats (DDoS attacks) or operational failures (404 errors) is impossible at scale.


### The Solution

I developed a Python script that:

1. Extract – Downloads Apache server logs from a remote GitHub source using the Requests library.
2. Parse – Converts raw log entries into structured fields (IP address, timestamp, HTTP method, endpoint, status code and response size).
3. Transform – Cleans and converts the data using Pandas.
4. Load – Stores the processed data in a SQLite database using SQLAlchemy.
5. Analyse – Produces SQL reports and visualises HTTP error distributions using Matplotlib and Seaborn.


### Continuous Integration

This project uses GitHub Actions to automate code validation.

On every push to the repository, GitHub Actions automatically:
 - Checks out the repository
 - Creates a fresh Ubuntu runner
 - Installs Python 3.11
 - Installs project dependencies
 - Performs a Python syntax check

This helps ensure that code changes do not introduce syntax errors before further development.

### Tech Stack

* Python
* Pandas
* Requests
* SQLAlchemy
* SQLite
* Matplotlib
* Seaborn
* GitHub Actions
* Git


### Key Insights

* Processed over 10,000 Apache log records.
* Identified the most active client IP addresses to highlight potential bot traffic.
* Analysed HTTP status code distribution to identify application errors.
* Stored structured log data for SQL-based querying and investigation.


### How to Run
1. git clone <repository-url>
2. cd Apache-Log-ETL-Pipeline
3. pip install -r requirements.txt
4. python server_log_pipeline.py
    

### Repository Structure

```text
Apache-Log-ETL-Pipeline
│
├── .github/
│   └── workflows/
│       └── python-ci.yml
├── server_log_pipeline.py
├── requirements.txt
├── README.md
└── production_logs.db
```