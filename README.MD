# Great Expectations

Great Expectations is the leading tool for validating, documenting, and profiling your data to maintain quality and improve communication between teams

# Features

Automated data profiling
The library profiles your data to get basic statistics, and automatically generates a suite of Expectations based on what is observed in the data.
Data validation
Expectation Suite passes or fails, and returns any unexpected values that failed a test
Data Docs
Renders HTML file of Expectations in clean, human-readable documentation containing both Expectation Suites and data Validation Results
Diverse Datasources and Store backends
Various datasources such Pandas dataframes, Spark dataframes, and SQL databases via SQLAlchemy.

# Dataset

posts_cleaned.csv

# Tutorial

Create a python environment and activate it
python -m venv gx
source gx/bin/activate
Install module great_expectations
pip install great_expectations==0.15.46
Verify the version
python --version
# Python 3.9.6

great_expectations --version
# great_expectations, version 0.15.46
Initialize at the base dir
great_expectations init
Confirm the prompt

Download the dataset Place the dataset in the data dir

Launch cli datasource process

great_expectations datasource new
Input following in the prompt

1 - Local File
1 - Pandas
../data - relative path to datasets

This open a Jupyter notebook,

Change to datasource_name var to faa_registration
datasource_name = "faa_registration"
Run all th cells
Close Jupyter notebook
Wait for terminal to show Saving file at /datasource_new.ipynb
Create Expectations suite for faa_registration datasets
great_expectations suite new
Input following in the prompt

3 - Automatically, using a profiler
1 - Select index of file faa_registration.csv
faa_registration_suite - suite name

This open a Jupyter notebook,

To exclude any column Update exclude_column_names
exclude_column_names = [
    "N-NUMBER",
    "SERIAL NUMBER",
    "MFR MDL CODE",
    "ENG MFR MDL",
#    "YEAR MFR",
    "TYPE REGISTRANT",
    "NAME",
    "STREET",
    "STREET2",
    "CITY",
    "STATE",
    "ZIP CODE",
    "REGION",
    "COUNTY",
    "COUNTRY",
#    "LAST ACTION DATE",
#    "CERT ISSUE DATE",
    "CERTIFICATION",
    "TYPE AIRCRAFT",
    "TYPE ENGINE",
    "STATUS CODE",
    "MODE S CODE",
    "FRACT OWNER",
    "AIR WORTH DATE",
    "OTHER NAMES(1)",
    "OTHER NAMES(2)",
    "OTHER NAMES(3)",
    "OTHER NAMES(4)",
    "OTHER NAMES(5)",
#    "EXPIRATION DATE",
#    "UNIQUE ID",
    "KIT MFR",
    "KIT MODEL",
    "MODE S CODE HEX",
    "X35",
]
Run to create default expectation and analyze the result
Wait for terminal to show Saving file at /*.ipynb
Modify expectation as per need
Modified the JSON file great_expectations/expectations/faa_registration_suite.json and kept necessary expectations
Create checkpoint
great_expectations checkpoint new faa_registration_v1
This open a Jupyter notebook,

Run all cells.
Open report in new page
Export the requirements and Commit changes to github