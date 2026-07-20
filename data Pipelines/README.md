Data Pipelines ETL Project (Day 1)
This is my first ETL (Extract, Transform, Load) pipeline project. The goal was to practice the full data flow: creating raw data, cleaning it, loading it into a database, and then making reports.

What It Does
Data Generation: I used the Faker library to make fake e-commerce data (customers, products, orders). Some bad data (nulls, duplicates, wrong formats) was added on purpose to test the pipeline.

ETL Pipeline:

Extract: Reads the raw CSV files.

Transform: Cleans the data (removes duplicates, fixes prices, checks foreign keys). Bad rows go into a separate file called rejected_records.csv.

Load: Puts the cleaned data into a PostgreSQL database.

Reporting: Runs SQL queries on the database (like totals, top customers, revenue trends) and saves the results into a CSV report.

There’s also a small script (pipeline.py) that shows how to pull data from an API and load it into MySQL.

Requirements
Python 3.8+

PostgreSQL (main database)

MySQL (only needed for the API demo script)

Setup
Clone the repo and open the folder.

Create a virtual environment and activate it.

Install dependencies with:

Code
pip install -r requirements.txt
Add your database info in the .env file (host, port, user, password, db name).

How to Run
Generate Data:

Code
python generate_data.py
→ Creates raw CSV files in data/.

Run ETL:

Code
python extract_load.py
→ Cleans data, loads into PostgreSQL, saves rejected rows.

Make Reports:

Code
python export_report.py
→ Creates a CSV report in reports/.

Project Files
generate_data.py → makes fake CSV data
extract_load.py → main ETL script
export_report.py → reporting script
pipeline.py → MySQL pipeline
Day1.sql → SQL schema and practice queries
requirements.txt → dependencies
.env → DB settings
