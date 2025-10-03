# Movie Recommendation Project – Data Visualization Guide

This repository contains a step-by-step guide for creating four key visualizations using movie data in Tableau. These visualizations are designed for a Data Analyst workflow to explore and analyze movies by rating, genre, and release year.

---

## **Project Overview**

The project focuses on preparing a cleaned movie dataset and creating meaningful visualizations to answer the following questions:

1. Which movies have the highest ratings?
2. What are the top-rated movies by specific genres?
3. How do average ratings vary across genres?
4. How has the number of movies released changed over time?

---

## **Dataset Preparation (SQL)**

Before visualizing in Tableau, the dataset was cleaned and processed using SQL:

* NULL values in `runtime`, `vote_average`, and `popularity` columns were filled with average values.
* `release_date` was converted to `release_year` for better aggregation.
* `genres` column was cleaned to remove unnecessary characters and formatted for analysis.
* A new table `movies_clean` was created containing:

  * `title`
  * `genres`
  * `release_year`
  * `rating` (`vote_average`)
  * `popularity`
  * `runtime`

These steps ensure the dataset is ready for Tableau visualizations.

---

## **Movie Data Visualization Guide**

### **Chart 1: Top 10 Movies by Rating**

**Purpose:** Identify the ten best-rated movies.

**Steps:**

1. Start a **New Sheet** in Tableau.
2. Drag the **title** field to the **Rows** shelf.
3. Drag the **rating** field to the **Columns** shelf (automatically aggregated).
4. Click the **sort icon** to sort bars in **descending order**.
5. Apply a **Top 10 filter** on the `title` field by **Average of Rating**.

---

### **Chart 2: Top 10 Movies by Genre**

**Purpose:** Identify the top-rated movies for a specific genre.

**Steps:**

1. Duplicate the sheet from Chart 1.
2. Rename it to **Top 10 Movies by Genre**.
3. Drag **genres** to the **Filters** shelf.
4. Select the desired genre (e.g., Comedy).
5. The existing Top 10 filter will now only apply to movies in that genre.

---

### **Chart 3: Average Rating by Genre**

**Purpose:** Compare average ratings across different genres.

**Steps:**

1. Start a **New Sheet**.
2. Drag **Genres** to the **Rows** shelf.
3. Drag **Rating** to the **Columns** shelf.
4. Change the measure to **Average** for `Rating`.
5. Open the **Show Me** panel and select **Packed Bubbles**.
6. Ensure Tableau assigns:

   * **Size Card:** `AVG(Rating)`
   * **Color Card:** `Genres`
7. Drag **Genres** to the **Label** card.
8. (Optional) Drag `AVG(Rating)` to the **Label** card for additional info.

---

### **Chart 4: Movies Released per Year**

**Purpose:** Visualize the trend of movie releases over time.

**Steps:**

1. Start a **New Sheet**.
2. Drag **release_year** to the **Columns** shelf.
3. Drag **title** to the **Rows** shelf.
4. Change the measure to **Count**.
5. Tableau may automatically create a **line chart**; if not, change the Marks type to **Line**.

---

## **Conclusion**

These four visualizations provide a comprehensive view of movie performance, genre popularity, and release trends. The dataset preparation in SQL ensures accurate and clean data for Tableau analysis.

---

