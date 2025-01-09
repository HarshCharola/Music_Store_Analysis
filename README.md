# Music Store Analysis

A project to explore and analyze a music store database using SQL queries. This repository contains a comprehensive set of SQL scripts for extracting meaningful insights and answering specific business questions related to customers, invoices, tracks, and more.

---

## Overview

This project uses a relational database schema to analyze a music store's operations, including:

- **Customer Behavior**: Identifying the best customers and their preferences.
- **Sales Insights**: Understanding country-wise and genre-wise sales trends.
- **Track Analysis**: Exploring popular tracks and their characteristics.
- **Employee Details**: Finding information about employees and their roles.

## Project Files

1. **`music_store_queries.sql`**: Contains all SQL queries to analyze the music store database.
2. **Schema Diagram**: A visual representation of the database structure (see below).

## Database Schema

![Database Schema](https://github.com/HarshCharola/Music_Store_Analysis/blob/main/schema_diagram.png)

The database contains the following tables:

- **Album**: Stores information about albums.
- **Artist**: Contains artist details.
- **Customer**: Information about customers.
- **Employee**: Employee details, including roles and hierarchy.
- **Genre**: Music genre classification.
- **Invoice**: Sales invoices.
- **Invoice Line**: Details of each item sold in an invoice.
- **Media Type**: Information about media formats.
- **Playlist**: User-created playlists.
- **Playlist Track**: Tracks included in playlists.
- **Track**: Details of music tracks.

## Features

- **Country-Wise Analysis**: Find countries with the highest sales and customer spending.
- **Customer Insights**: Identify the best customers and their preferred music genres.
- **Track Insights**: Analyze tracks longer than the average and explore genre popularity.
- **Employee Analysis**: Retrieve details about employees based on their job titles and hierarchy.

---

## Queries Highlights

1. **Senior Most Employee Based on Job Title**:
   ```sql
   SELECT title, last_name, first_name 
   FROM employee
   ORDER BY levels DESC
   LIMIT 1;
   ```

2. **Countries with the Most Invoices**:
   ```sql
   SELECT COUNT(*) AS c, billing_country 
   FROM invoice
   GROUP BY billing_country
   ORDER BY c DESC;
   ```

3. **Tracks Longer than Average Song Length**:
   ```sql
   SELECT name, milliseconds
   FROM track
   WHERE milliseconds > (
       SELECT AVG(milliseconds) AS avg_track_length
       FROM track
   )
   ORDER BY milliseconds DESC;
   ```


---

