## 🎬 Movie Recommendation System – Data Cleaning & Visualization Project

### 📁 Overview

This project demonstrates the complete data cleaning, transformation, and visualization workflow for a movies dataset.
The dataset is loaded into MySQL, cleaned using SQL commands, and analyzed visually using Tableau.

---

## ⚙️ Steps Performed

### 1. Database & Table Setup

```sql
CREATE DATABASE Movies_db;
USE Movies_db;
CREATE TABLE Movies (...);
```

Created Movies table with columns like movie_id, title, genres, release_date, vote_average, popularity, and runtime.
Loaded CSV data using the LOAD DATA LOCAL INFILE command.

---

### 2. Data Cleaning (SQL)

Performed multiple cleaning steps to make the dataset suitable for analysis:

| Task                    | Description                                                                    |
| ----------------------- | ------------------------------------------------------------------------------ |
| NULL handling           | Filled NULLs in runtime, rating, and popularity with average values.           |
| Removed invalid records | Deleted rows where release_date was NULL.                                      |
| Genre formatting        | Removed JSON-like text ([{"id":...}]) and cleaned it to show only genre names. |
| Added new column        | Extracted release_year from release_date for easier analysis.                  |
| Final clean table       | Created movies_clean for visualization and analysis.                           |

---

### 3. Analysis Queries (SQL)

Key analytical queries:

1. Top 10 Movies by Rating

```sql
SELECT title, rating
FROM movies_clean
ORDER BY rating DESC
LIMIT 10;
```

2. Top 10 Movies by Genre (e.g., Comedy)

```sql
SELECT title, rating
FROM movies_clean
WHERE genres LIKE '%Comedy%'
ORDER BY rating DESC
LIMIT 10;
```

3. Average Rating by Genre

```sql
SELECT genres, ROUND(AVG(rating), 2) AS avg_rating
FROM movies_clean
GROUP BY genres
ORDER BY avg_rating DESC;
```

4. Movies Released per Year

```sql
SELECT release_year, COUNT(*) AS movies_count
FROM movies_clean
GROUP BY release_year
ORDER BY release_year;
```

---

## 📊 Tableau Visualizations

### Chart 1: Top 10 Movies by Rating

Rows: Title
Columns: Rating
Chart Type: Horizontal Bar Chart
Sort: Descending

### Chart 2: Movies Released per Year

Columns: Release Year
Rows: COUNT(Title)
Chart Type: Line Chart

### Chart 3: Average Rating per Genre

Rows: Genre
Columns: AVG(Rating)
Chart Type: Packed Bubbles Chart

### Chart 4: Top 10 Movies by Genre (Comedy)

Rows: Title
Columns: Rating
Filter: Genre = "Comedy"
Chart Type: Bar Chart

---

## 📈 Insights Derived

Identified top-rated movies overall and by genre.
Visualized trends in movie production over the years.
Compared average audience ratings across genres.
Analyzed popularity vs. rating patterns through visual exploration.

---

## 🧠 Tools Used

SQL (MySQL Workbench) – For data cleaning and preparation.
Tableau Public/Desktop – For visualization and storytelling.
Excel/CSV – For initial dataset source.

---

## 📬 Author

Aditi Srivastava
3rd Year | Information Science & Engineering | Dayananda Sagar College of Engineering, Bengaluru
Data Science Intern | Tableau | SQL | Python | Excel
