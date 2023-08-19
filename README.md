# Welcome to my data modelling project using dbt and BigQuery!

## Project Goal
The goal of project is to build hybrid data modelling using kimball and OBT method to create self-service data analysis for business.

## Source Data
The Northwind data, which can be found in data_source folder as csv format, is used and ingested into BigQuery as a data lake layer .

###Architecture Design
```seq
Data Sources (OLTP)->BQ Data Lake: Data Ingestion
Note left of Data Sources (OLTP): Data Sources: CSV format in this project
BQ Data Lake->Staging Layer: Load
Staging Layer->Dimensional Data Warehouse Layer: Transform
Dimensional Data Warehouse Layer->Reporting Layer (OBT):Transform
Reporting Layer (OBT)->BI Tools: Visualize
Note right of BI Tools: BI tools is not demonstrated in this project
```

### Running this project
To get up and running with this project:

1. Install dbt using [these instructions.](https://docs.getdbt.com/docs/core/installation)
2. Clone this repository.
3. Change into the ae_project directory from the command line:
	`$ cd ae_project`
4. Ensure your profile is setup correctly from the command line:
	`$ dbt debug`
6. Create a dataset called dl_northwind in Google BigQuery and load csv (found in source_data folder) files into this dataset
7. Run the models:
	`$ dbt run`
8. Test the output of the models:
	`$ dbt test`
9. Generate documentation for the project:
	`$ dbt docs generate`
10. View the documentation for the project:
	`$ dbt docs serve`


#### For more information on dbt:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Join the [dbt community](https://www.getdbt.com/community/)
