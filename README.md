# ETL_project
Extract Transform Load U.S. Occupations Project

Two data sources were Extracted:
1) Bureau of Labor Statistics Standard Occupation Classification (SOC), which was in xlsx file (https://www.bls.gov/soc/)
2) Occupational Information Network (ONET)from U.S. Department of Labor's Employment and Training Administration, which were two text files (https://www.onetcenter.org/database.html#individual-files)

For the data, I transformed the following procedures using Pandas in my Jupyter Notebook:
* created four smaller SOC dataframes from the larger/original SOC dataframe.
* dropped columns that I did not need from both data files.
* spilt text for onet-soc codes in the ed and skill dataframes.
* reset the index.
* reorder the columns to have the primary keys in the first columns.


In PgAdmin, I created tables for the dataframe data to load into. This involved:
* first creating a draft ERD Schema to see the attributes and relationships.
* creating tables based on the Schema and making sure about primary keys and foreign keys

Back in Jupyter Notebook, I prepared to load the dataframe into the Database. This involved:
* using sqlalchemy library to create an engine connection between pandas and postgres
* loading in order the dataframes into the appropriate tables (had to pay particular attention to loading the data with primary keys first and then the tables with the foreign keys, which are dependent on the primary keys).

There is a folder in this repository with screenshots of the data loaded into the Postgresql Database.



