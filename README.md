# **Netflix Content Analysis: Understanding Content Distribution Trends**

## **Introduction**
Netflix has revolutionized the way people consume entertainment, offering a vast library of movies and TV shows across the globe. Aspiring to become a data analyst, I aim to dive deep into Netflix’s content distribution strategies to uncover critical insights about:

- Genre preferences across regions.
- Trends in content additions over the years.
- Differences in content characteristics between movies and TV shows.

This project will help identify patterns and trends that can be used to optimize Netflix's content creation, distribution, and marketing strategies. The first step in achieving these insights is ensuring the dataset is clean, consistent, and ready for analysis.

---

## **Part 1: Data Cleaning**

To ensure the dataset is free of errors and fully formatted for use in tools like **DB Browser SQLite** and **Power BI**, I performed an extensive data cleaning process. Below is a detailed explanation of all the steps taken:

### **1. Handling Missing Values**
Missing values were identified and replaced based on the context of each column:
- **`director`**: Replaced missing values with `Unknown`.
- **`cast`**: Replaced missing values with `Unknown`.
- **`country`**: Replaced missing values with `Unknown`.
- **`date_added`**: Replaced missing values with `Not Available`.
- **`rating`**: Replaced missing values with `Unrated`.
- **`duration`**:
  - For `Movies`, replaced blanks with `0 min`.
  - For `TV Shows`, replaced blanks with `Unknown`.

### **2. Standardizing Columns**
To ensure consistency, I standardized key columns:
- **`date_added`**:
  - Converted all valid dates to the `YYYY-MM-DD` format.
  - Retained `Not Available` for invalid or missing dates.
- **`duration`**:
  - Ensured consistent formatting:
    - Movies as `X min` (e.g., `90 min`).
    - TV Shows as `X Season(s)` (e.g., `2 Seasons`).
  - Replaced missing or invalid durations with context-appropriate values.

### **3. Text Cleaning**
Ensured the `title` and `description` columns are clean and free of unnecessary characters:
- Removed special characters (e.g., `#`, `%`, `&`).
- Stripped extra spaces and hidden characters.

### **4. Splitting and Normalizing Genres**
The `listed_in` column (genres) was split into separate lists for each entry to enable easier analysis and normalization:
- Example: `"Drama, Action"` → `['Drama', 'Action']`.

### **5. Removing Duplicates**
Duplicate rows were removed based on the unique `show_id` column to ensure every entry represents a unique Netflix title.

### **6. Validating and Cleaning Data Types**
Ensured data type integrity:
- **`release_year`**: Verified all values are integers and within the valid range (1900 to the current year).
- Checked and enforced proper data types for all other columns.

### **7. Adding Derived Columns**
To enhance the dataset for analysis, I created the following derived columns:
- **`Year Added`**: Extracted the year from the `date_added` column to analyze content additions over time.
- **`Content Length`**: Categorized durations into:
  - `Short` (<30 min)
  - `Medium` (30–90 min)
  - `Long` (>90 min)

### **8. Final Output**
The cleaned dataset was saved as **`netflix_cleaned.csv`**, ensuring:
- All missing, inconsistent, and erroneous values were addressed.
- The dataset is fully formatted for seamless import into tools like **DB Browser SQLite** and **Power BI**.

---

# Netflix Content Distribution Analysis: SQL Queries

## Introduction
In this section of the project, I explored Netflix's content distribution trends by writing SQL queries to analyze the cleaned dataset. My goal was to answer meaningful questions about the content, such as genre popularity, country contributions, and patterns in content additions. The insights gained here will help me uncover trends and provide recommendations for optimizing Netflix’s content strategy.

---

## SQL Queries and Objectives
Below is a summary of the SQL queries I created, along with the questions they address:

### **1. Total Content by Type**
- **Query Objective:** Determine the distribution of movies versus TV shows in Netflix's library.
- **Insight:** Helps understand Netflix's focus on different content types.

- <img width="433" alt="Screenshot 2024-12-25 at 9 07 33 PM" src="https://github.com/user-attachments/assets/5c1863a0-5550-4be9-8088-d14313f793a1" />


### **2. Top 10 Most Common Genres**
- **Query Objective:** Identify the most popular genres across Netflix's content catalog.
- **Insight:** Reveals the genres that dominate Netflix’s library, helping to analyze user preferences.

- <img width="477" alt="Screenshot 2024-12-25 at 9 08 09 PM" src="https://github.com/user-attachments/assets/fc212000-68d9-469b-b61e-e903e06c6a14" />


### **3. Top 10 Countries Producing Content**
- **Query Objective:** Find out which countries contribute the most content to Netflix.
- **Insight:** Highlights the geographic diversity of Netflix’s offerings and regional strengths.

- <img width="425" alt="Screenshot 2024-12-25 at 9 08 39 PM" src="https://github.com/user-attachments/assets/7d5e2f99-3ad4-4bd1-9238-ecc69ad27901" />


### **4. Content Added Over Time**
- **Query Objective:** Analyze trends in content additions over the years.
- **Insight:** Shows how Netflix has expanded its library, providing insights into growth trends.

- <img width="375" alt="Screenshot 2024-12-25 at 9 09 25 PM" src="https://github.com/user-attachments/assets/6ac5e863-3c39-45e4-90fd-69c0990c2e57" />


### **5. Content Added by Genre and Type**
- **Query Objective:** Examine the distribution of content by genre and type (movies vs TV shows).
- **Insight:** Offers a combined view of genre popularity and its alignment with content types.

- <img width="459" alt="Screenshot 2024-12-25 at 9 10 07 PM" src="https://github.com/user-attachments/assets/beec18d2-2136-410b-9af4-dc66babb12b2" />


### **6. Average Duration of Movies**
- **Query Objective:** Calculate the average runtime of Netflix’s movies.
- **Insight:** Useful for identifying content trends related to length.

- <img width="692" alt="Screenshot 2024-12-25 at 9 10 50 PM" src="https://github.com/user-attachments/assets/548bd9dc-f210-4f45-ae35-86317742ae03" />


### **7. TV Shows with Most Seasons**
- **Query Objective:** Find the TV shows with the highest number of seasons.
- **Insight:** Highlights long-running shows and their impact on audience retention.

- <img width="556" alt="Screenshot 2024-12-25 at 9 11 15 PM" src="https://github.com/user-attachments/assets/d679e4b3-e69b-4db1-878f-b22486e9dab0" />


### **8. Most Frequently Appearing Directors**
- **Query Objective:** Identify the directors with the most titles in Netflix’s catalog.
- **Insight:** Helps recognize key contributors to Netflix’s content.

- <img width="416" alt="Screenshot 2024-12-25 at 9 11 44 PM" src="https://github.com/user-attachments/assets/924bdf31-c595-49c6-b748-42fb0f06b5d4" />


### **9. Number of Titles by Rating**
- **Query Objective:** Count the titles available for each rating category.
- **Insight:** Provides a breakdown of Netflix’s offerings by age-appropriateness.

- <img width="373" alt="Screenshot 2024-12-25 at 9 12 19 PM" src="https://github.com/user-attachments/assets/e0bbf3d4-962c-4a2f-9f4e-8464e1618f37" />


### **10. Most Common Cast Members**
- **Query Objective:** Determine which cast members appear most frequently in Netflix titles.
- **Insight:** Highlights popular actors and their prominence in the catalog.

- <img width="494" alt="Screenshot 2024-12-25 at 9 13 32 PM" src="https://github.com/user-attachments/assets/152d2ce1-1d1a-412c-ab47-b17732a15fd2" />


---

## Summary of Findings
These queries provide a comprehensive view of Netflix’s content strategy, covering content types, genres, countries, and contributors. The insights gained will support the next stage of the project, where I’ll visualize these trends in Power BI to present actionable insights.

---

## Next Steps
With these queries completed, I will:
1. Import the query results into Power BI for visualization.
2. Explore additional insights by combining data dimensions, such as country, genre, and ratings.
3. Formulate recommendations for Netflix based on the trends observed.

---

## Feedback and Suggestions
If you have feedback or ideas for additional queries, feel free to share them. I’m always open to improving this project and exploring new directions!
