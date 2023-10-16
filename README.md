# AppStore Apps Analysis

This GitHub repository contains SQL code for analyzing AppStore apps data and conducting basic Exploratory Data Analysis (EDA). The dataset consists of two tables: `AppleStore` and `appleStore_description`. The SQL code in this project performs various checks and analyses to gain insights from the data.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Checks](#data-checks)
  - [Matching Count](#matching-count)
  - [Missing Values](#missing-values)
- [Basic EDA](#basic-eda)
  - [Number of Apps per Genre](#number-of-apps-per-genre)
  - [App Ratings](#app-ratings)
- [Data Analysis](#data-analysis)
  - [Paid vs. Free Apps](#paid-vs-free-apps)
  - [Language Support vs. Ratings](#language-support-vs-ratings)
  - [Genres with Low Ratings](#genres-with-low-ratings)
  - [Description Length vs. Ratings](#description-length-vs-ratings)
  - [Top Rated Apps per Genre](#top-rated-apps-per-genre)

## Project Overview

This project aims to analyze AppStore apps data and derive valuable insights from it using SQL queries. The dataset includes information about various app attributes, such as app name, user ratings, genres, pricing, and more.

## Data Checks

### Matching Count

To ensure data integrity, we check whether the `AppleStore` and `appleStore_description` tables have matching counts of unique app IDs.

```sql
-- Check whether AppleStore.csv and appleStore_description have matching counts of unique app IDs
SELECT COUNT(DISTINCT id) AS UniqueAppIDs
FROM AppleStore

SELECT COUNT(DISTINCT id) AS UniqueAppIDs
FROM appleStore_description
```

### Missing Values

We identify and count missing values in essential columns of the `AppleStore` and `appleStore_description` tables.

```sql
-- Check for missing values in AppleStore table
SELECT COUNT(*) AS MissingValues
FROM AppleStore
WHERE track_name IS NULL OR user_rating IS NULL OR prime_genre IS NULL

-- Check for missing values in appleStore_description table
SELECT COUNT(*) AS MissingValues
FROM appleStore_description
WHERE app_desc IS NULL
```

## Basic EDA
