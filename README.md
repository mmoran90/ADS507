# Data pipeline objective: 
The objective of this data pipeline is to ingest data for alcoholic and non-alcoholic beverages via an Extract, Transform, and Load (ETL) approach that will generate a final MySQL dataset.
The final dataset will then be used to support a searchable catalog for users.

# Data for the data pipeline originate from the following sources:
- Drinks API: https://www.thecocktaildb.com/
    # Data:
    - Glass
    - Drink a-z
    - Drink 1-10
- Comma Seperated Values (CSV) files
    # Data:
    - Category
    - Ingredients

## Repositoy content overview:
To illustrate the structure of the target data pipeline, reference the 'Datapipeline.pfd' file.
In it, one can visually denote each of the Extract, Transform, and Load (ETL) components of the pipeline. 

Supporting data is also stored in this repository, both as CSV files and a JSON file.
The 'category.csv' file and 'ingredients' file are the 2 target CSV files while the 'drinkDB_schema.mwb' is the target JSON file.

The pipeline leverages Infrastructure as Code (IaC), found within the 'drinks.ipynb' Jupyter notebook file.
The document outlines all of the steps taken to prepare and execute the pipeline. 
It begins with executing actions for ingesting data from the target API, progressing to present code for ingesting 2 CSV files.
Following, the rest of the code walks through the process of creating a connection to the in scope (Azure) data store and executing necesary actions and queries to fully execute the data pipeline.

# steps to deploy pipeline:
To deploy the pipeline, follow these steps in the given order:

STEP 1: Prep Dependencies & Extract Data
1a. Open the 'drinks.ipynb' Jupyter notebook file.
1b. Import all of the necessary dependencies (e.g., packages) to enable the creation and connection to the Azure data store as well as relevant Python operations.
    Also, the require parameters for creating a connection to the data store are set within the first code cell.
1c. Read in the 'category.csv' file and the 'ingredient.csv' file.
1d. Connect to the Drinks API to extract data in JSON format.

STEP 2: Data Cleanup & Transformation
2a. Identify columns with null values.
2b. Remove columns with null values.

STEP 3: Load Data
3a. Create connection engine utilizing sqlalchemy package. 
3b. Create tables in Azure ("Test") database.
3c. Load transformed data into MySQL tables.
3d. Add new column to MySQL table.

STEP 4: Output
4a. Execute search and catalog window process.
4b. Execute data joins + respective visuals.
4c. Close engine connection.

# monitoring the pipeline:
Given that the target data is not dependent on a schedule of any sort, it is defined as static data.
Therefore, no monitoring sytem will be implemented for the pipeline. 
