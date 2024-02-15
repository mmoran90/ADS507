# Data pipeline objective: 
To ingest data for alcoholic and non-alcoholic beverages via an Extract, Transform, and Load (ETL) approach that will generate a final SQL dataset.
The final dataset will then be used to support a searchable catalog for users.

# Data for the data pipeline originate from the following sources:
- Drinks API: https://www.thecocktaildb.com/
    # Data:
    - Glass
    - Drink a
    - Drink b
    - Drink c
    - Drink d
- Comma Seperated Values (CSV) files
    # Data:
    - Category
    - Ingredients

## Repositoy content overview:
To illustrate the structure of the target data pipeline, reference the 'Datapipeline.pfd' file.
In it, one can visually denote each of the Extract, Transform, and Load components of the pipeline. 

Supporting data is present in this repository, both as CSV files and a JSON file.
The 'category.csv' file and 'ingredients' file are the 2 target CSV files while the 'drinkDB_schema.mwb' is the target JSON file.

The pipeline leverages Infrastructure as Code (IaC), found within the 'drinks.ipynb' Jupyter notebook file.
The document outlines all of the steps taken to prepare and execute the pipeline. 
It begins with executing actions for ingesting data from the target API, progressing to present code for ingesting 2 CSV files.
Following, the rest of the code walks through the process of creating a connection to the in scope (Azure) data store and executing necesary actions and queries to fully execute the data pipeline.

# steps to deploy pipeline
To begin the deployment of the pipeline, open the 'drinks.ipynb' Jupyter notebook file and execute each code cell in presented order.
First, the code will ensure that the necessary libraries and packages are downloaded to create a connection to the Azure data store.
Also, the require parameters for creating a connection to the data store are set within the first code cell.
The subsequent code cell then creates the connection engine utilizing the sqlalchemy package. 
Next, the following code cells connect to the Drinks API noted above and extract data in a JSON format.
Similarly, the following code cells thereafter ingets the 2 target CSV files.

Following these code executions, the next code cells allow user to:

1. trigger the input process in which they submit a value (e.g., ingredient = 'vodka').
2. trigger the query execution and results process.

# monitoring the pipeline
...TBD...
