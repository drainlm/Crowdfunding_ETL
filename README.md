# Crowdfunding_ETL

This script builds an Extract, Transform, Load Pipeline using Python and Pandas. The crowdfunding.xlsx and contacts.xlsx data is transformed and four csv files (category.csv, subcategory, campaign.csv, and contacts.csv) are created.

## Required

* pandas
* numpy
* json

#### Category and Subcategory DataFrames

The Crowdfunding data from crowdfunding.xlsx is extracted to create two DataFrames, category and subcategory. This is done by splitting the 'category & sub-category' column along the '/' to create two new columns. Lists for categories and subcategories are then created, an array for list comprehension is then made, and the category and subcategory DataFrames are then exported as csv files.

#### Create the Campaign DataFrame

The Crowdfunding data from crowdfunding.xlsx is then used to create the campaign DataFrame, which is then cleaned (columns renamed, goal and pledged columns are changed to floats, the datetime is formatted for launched_date and end_date, the category and subcategory arrays are added as columns, unwanted columns are dropped, and then campaign is exported as a csv file.

#### Create the Contacts DataFrame

The contact data from contacts.xlsx is extracted and then the rows are iterated through, converting each row into a dictionary and then creating a list for the contact_id, name, and email. This DataFrame is then saved. The name column is then split into first and last names, which each get their own columns, the combined name column is dropped, and the columns are rordered before the cleaned DataFrame is exported as a csv file. 

#### Create the Crowdfunding Database

1. Inspect the four CSV files, and then sketch an ERD of the tables by using [QuickDBD](http://www.quickdatabasediagrams.com)

* Use the information from the ERD to create a table schema for each CSV file.
  **Note:** Remember to specify the data types, primary keys, foreign keys, and other constraints.
* Save the database schema as a Postgres file named `crowdfunding_db_schema.sql`, and save it to your GitHub repository.
* Create a new Postgres database, named `crowdfunding_db`.
* Using the database schema, create the tables in the correct order to handle the foreign keys.
* Verify the table creation by running a `SELECT` statement for each table.
* Import each CSV file into its corresponding SQL table.
* Verify that each table has the correct data by running a `SELECT` statement for each.
