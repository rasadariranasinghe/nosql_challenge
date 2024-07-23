# UK Food Standards Agency Database Analysis

## Overview

This project involves analyzing food hygiene ratings data from the UK Food Standards Agency. The data is used to evaluate various establishments across the United Kingdom. The aim is to help journalists and food critics at "Eat Safe, Love" magazine decide where to focus future articles.

## Project Structure

This project is divided into three main parts:

1. **Database and Jupyter Notebook Setup**
2. **Database Update**
3. **Exploratory Analysis**

## Part 1: Database and Jupyter Notebook Setup

### Objectives

- Import the provided data into MongoDB.
- Set up a Jupyter Notebook environment.
- Confirm successful data import and setup.

### Steps

1. **Import Data**: Use `mongoimport` to import the establishments data into a MongoDB database named `uk_food` and a collection named `establishments`.
2. **Library Imports**: Import necessary libraries (`PyMongo` and `Pretty Print`).
3. **Mongo Client Instance**: Create an instance of the Mongo Client.
4. **Database Confirmation**:
   - List databases to confirm the `uk_food` database.
   - List collections to confirm the `establishments` collection.
   - Display one document from the `establishments` collection using `find_one`.

## Part 2: Database Update

### Objectives

- Add a new restaurant to the database.
- Update specific fields in the database.
- Remove unwanted data from the database.

### Steps

1. **Add New Restaurant**: Insert a document for "Penang Flavours" restaurant.
2. **Update BusinessTypeID**:
   - Find the `BusinessTypeID` for "Restaurant/Cafe/Canteen".
   - Update the new restaurant with this `BusinessTypeID`.
3. **Remove Dover Establishments**:
   - Count documents with the Dover Local Authority.
   - Remove these documents.
   - Confirm removal by recounting documents.
4. **Data Type Conversion**:
   - Convert latitude and longitude to decimal numbers.
   - Convert `RatingValue` to integer numbers.

## Part 3: Exploratory Analysis

### Objectives

- Answer specific questions to help the magazine editors identify areas of interest.

### Questions and Approach

1. **Establishments with a Hygiene Score of 20**:
   - Count documents.
   - Display the first document.
   - Convert results to a Pandas DataFrame.
2. **Establishments in London with a RatingValue >= 4**:
   - Use `$regex` to match the Local Authority name.
   - Count documents.
   - Display the first document.
   - Convert results to a Pandas DataFrame.
3. **Top 5 Establishments with a RatingValue of 5, Sorted by Lowest Hygiene Score**:
   - Search within 0.01 degree on either side of the latitude and longitude.
   - Sort by hygiene score.
   - Limit results to 5.
4. **Number of Establishments with a Hygiene Score of 0 in Each Local Authority**:
   - Use the aggregation method.
   - Sort results from highest to lowest.
   - Print top ten Local Authority areas.

## Tools and Libraries Used

- **PyMongo**: For interacting with MongoDB.
- **Pretty Print (pprint)**: For formatting the output.
- **Pandas**: For data manipulation and analysis.
