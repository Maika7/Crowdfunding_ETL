# Project 2 - Crowdfunding ETL

## Assignment Details
For the ETL mini project, you will practice building an ETL pipeline using Python, Pandas, and either Python dictionary methods or regular expressions to extract and transform the data. After you transform the data, you'll create four CSV files and use the CSV file data to create an ERD and a table schema. Finally, you’ll upload the CSV file data into a Postgres database.

## Instructions

The instructions for this mini project are divided into the following subsections:

* Create the Category and Subcategory DataFrames
* Create the Campaign DataFrame
* Create the Contacts DataFrame
* Create the Crowdfunding Database

## Create the Category and Subcategory DataFrames

1. Extract and transform the `crowdfunding.xlsx` Excel data to create a category DataFrame that has the following columns:
    * A "category_id" column that has entries going sequentially from "cat1" to "cat*n*", where *n* is the number of unique categories
    * A "category" column that contains only the category titles
2. Export the category DataFrame as `category.csv` and save it to your GitHub repository.
3. Extract and transform the `crowdfunding.xlsx` Excel data to create a subcategory DataFrame that has the following columns:
    * A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcat*n*", where *n* is the number of unique subcategories
    * A "subcategory" column that contains only the subcategory titles
4. Export the subcategory DataFrame as `subcategory.csv` and save it to your GitHub repository.

## Create the Campaign DataFrame

1. Extract and transform the `crowdfunding.xlsx` Excel data to create a campaign DataFrame has the following columns:
    * The "cf_id" column
    * The "contact_id" column
    * The "company_name" column
    * The "blurb" column, renamed to "description"
    * The "goal" column, converted to the `float` data type
    * The "pledged" column, converted to the `float` data type
    * The "outcome" column
    * The "backers_count" column
    * The "country" column
    * The "currency" column
    * The "launched_at" column, renamed to "launched_date" and with the UTC times converted to the `datetime` format
    * The "deadline" column, renamed to "end_date" and with the UTC times converted to the `datetime` format
    * The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
    * The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame
2. Export the campaign DataFrame as `campaign.csv` and save it to your GitHub repository.

## Create the Contacts DataFrame

1. Use Python dictionary methods for extracting and transforming the data from the `contacts.xlsx` Excel data.
2. Complete the following steps:
    * Import the `contacts.xlsx` file into a DataFrame.
    * Iterate through the DataFrame, converting each row to a dictionary.
    * Iterate through each dictionary, doing the following:
      * Extract the dictionary values from the keys by using a Python list comprehension.
      * Add the values for each row to a new list.
    * Create a new DataFrame that contains the extracted data.
    * Split each "name" column value into a first and last name, and place each in a new column.
    * Clean and export the DataFrame as `contacts.csv` and save it to your GitHub repository.

## Create the Crowdfunding Database

1. Inspect the four CSV files, and then sketch an ERD of the tables by using [QuickDBD](http://www.quickdatabasediagrams.com).
2. Use the information from the ERD to create a table schema for each CSV file.
    **Note:** Remember to specify the data types, primary keys, foreign keys, and other constraints.
3. Save the database schema as a Postgres file named `crowdfunding_db_schema.sql`, and save it to your GitHub repository.
4. Create a new Postgres database, named `crowdfunding_db`.
5. Using the database schema, create the tables in the correct order to handle the foreign keys.
6. Verify the table creation by running a `SELECT` statement for each table.
7. Import each CSV file into its corresponding SQL table.
8. Verify that each table has the correct data by running a `SELECT` statement for each.

## Source Code Location

* All of the files are located in the root directory
* ETL_Mini_Project_Final_Code.ipynb - Combined code from Jimmy and Emeka
* crowdfunding_db_schema.sql - Database schema
* crowdfunding_erd.png - ERD sketch of the tables
