# **Netflix Content Analysis: Understanding Content Distribution Trends**

## **Introduction**
Netflix has revolutionized the way people consume entertainment, offering a vast library of movies and TV shows across the globe. As a data analyst, I aim to dive deep into Netflix’s content distribution strategies to uncover critical insights about:

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

## **Next Steps**
With the dataset cleaned and formatted, the next steps in this project will include:
1. **Data Exploration and Visualization**:
   - Import the dataset into **Power BI** for interactive visualizations.
   - Analyze trends in content distribution across regions, genres, and time.
2. **Insights and Recommendations**:
   - Provide actionable insights for improving content production and marketing strategies.

---

## **Feedback and Suggestions**
If you have any suggestions or feedback, feel free to create an issue or reach out. This project is a work in progress, and collaboration is always welcome!
