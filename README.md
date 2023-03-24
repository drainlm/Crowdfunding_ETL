# Crowdfunding_ETL

This mini project builds an Extract, Transform, Load Pipeline using Python and Pandas. The crowdfunding.xlsx and contacts.xlsx data is transformed and four csv files (category.csv, subcategory, campaign.csv, and contacts.csv) are created. An Entity-Relationship Model (ERD) was made to create a table schema in a Postgres database, to hold the four csv files in four tables.

## Required

* pandas
* numpy
* json
* datetime

#### Category and Subcategory DataFrames

The Crowdfunding data from crowdfunding.xlsx is extracted to create two DataFrames, category and subcategory. This is done by splitting the 'category & sub-category' column along the '/' to create two new columns. Lists for categories and subcategories are then created, an array for list comprehension is then made, and the category and subcategory DataFrames are then exported as csv files.

#### Create the Campaign DataFrame

The Crowdfunding data from crowdfunding.xlsx is then used to create the campaign DataFrame, which is then cleaned (columns renamed, goal and pledged columns are changed to floats, the datetime is formatted for launched_date and end_date, the category and subcategory arrays are added as columns, unwanted columns are dropped, and then campaign is exported as a csv file.

#### Create the Contacts DataFrame

The contact data from contacts.xlsx is extracted and then the rows are iterated through, converting each row into a dictionary and then creating a list for the contact_id, name, and email. This DataFrame is then saved. The name column is then split into first and last names, which each get their own columns, the combined name column is dropped, and the columns are rordered before the cleaned DataFrame is exported as a csv file.

#### Create the Crowdfunding Database

An ERD was then sketched of the tables using [QuickDBD](http://www.quickdatabasediagrams.com), which was then used to create a table schema for each of the four csv files. This was saved as crowdfunding_db_schema.sql before being used to create tables in the Postgres database, crowdfunding_db. Each csv file was imported and verified to run using a SELECT statement.

![1679617874132](image/README/1679617874132.png)
