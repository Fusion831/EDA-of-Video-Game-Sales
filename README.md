# Foundational Data Cleaning & EDA: Video Game Sales

This repository contains a foundational project focused on the essential first steps of any data analysis workflow: **data cleaning and a structured exploratory data analysis (EDA)**. Using the popular Video Game Sales dataset from Kaggle, this project serves as a practical exercise in preparing raw data and using it to answer key business and market questions.

**View the full process in the Jupyter Notebook:** [`vgsales_analysis.ipynb`](./vgsales_analysis.ipynb)

---

## Table of Contents

- [Foundational Data Cleaning \& EDA: Video Game Sales](#foundational-data-cleaning--eda-video-game-sales)
  - [Table of Contents](#table-of-contents)
  - [Project Objective](#project-objective)
  - [Tech Stack](#tech-stack)
  - [The Data Cleaning Process](#the-data-cleaning-process)
  - [Key Questions Explored in the EDA](#key-questions-explored-in-the-eda)
    - [Market Composition Analysis](#market-composition-analysis)
      - [Performance and Success Analysis](#performance-and-success-analysis)
      - [Temporal and Regional Analysis](#temporal-and-regional-analysis)
  - [Conclusion](#conclusion)
  - [How to Run This Project](#how-to-run-this-project)

---

## Project Objective

The goal of this "warm-up" project was to execute a systematic and well-documented data pipeline. The focus was on mastering the core tasks of a data analyst:

1. **Data Ingestion and Inspection:** Loading a raw dataset and performing a thorough initial assessment.
2. **Problem Identification:** Quantifying missing values and identifying incorrect data types.
3. **Systematic Cleaning:** Applying a justified, step-by-step cleaning strategy using Pandas.
4. **Verification:** Confirming that all cleaning operations were successful.
5. **Question-Driven Exploration:** Performing structured data aggregations to answer a variety of questions about the video game market.

---

## Tech Stack

- **Language:** Python 3
- **Core Libraries:**
  - Pandas for data manipulation and analysis.
  - NumPy for numerical operations.
  - Matplotlib & Seaborn for visualization and verification.
- **Environment:** Jupyter Notebook

---

## The Data Cleaning Process

The primary focus of this project was the data cleaning phase. The following methodical steps were taken to prepare the data:

- **1. Initial Assessment:**
  - The `.info()` method revealed that the `Year_of_Release` and `Publisher` columns contained null values.
  - It also showed that `Year_of_Release` was incorrectly typed as a `float64`.

- **2. Handling Missing Values:**
  - **Justification:** The missing data constituted less than 2% of the total dataset. To maintain data integrity, the decision was made to drop the rows containing these nulls.
  - **Implementation:** The `df.dropna(subset=...)` method was used to remove the problematic rows.

- **3. Data Type Correction:**
  - **Justification:** With the null values removed, the `Year_of_Release` column could be safely and accurately represented as an integer.
  - **Implementation:** The `.astype('int')` method was used to convert the column to its correct `int64` data type.

- **4. Verification:**
  - The cleaning process was verified by running `.info()` and `.isnull().sum()` again, confirming that all missing values were handled and all data types were correct.

---

## Key Questions Explored in the EDA

After cleaning, the notebook proceeds with a structured exploratory data analysis designed to answer a variety of questions about the video game market. The analysis is broken down into several key areas:

### Market Composition Analysis

- What are the most frequently published game genres?
- Which gaming platforms have the largest libraries of titles?
- Who are the most prolific publishers by the number of games released?

#### Performance and Success Analysis

- Which game genres have generated the most revenue globally? How does this compare to their frequency of release?
- Who are the top-performing "titan" publishers in terms of total global sales?

#### Temporal and Regional Analysis

- How have global video game sales evolved from 1980 to the present? What were the industry's peak years?
- How do consumer preferences for top game genres differ across the major international markets of North America, Europe, and Japan?

---

## Conclusion

This project successfully demonstrates a reproducible and well-documented approach to data cleaning and foundational analysis. It serves as a strong exercise, resulting in a clean, reliable dataset (`vgsales_cleaned.csv`) that is now ready for more advanced visualization, feature engineering, or machine learning tasks. The initial EDA provides clear, data-driven answers to important questions about the video game industry's landscape.

---

## How to Run This Project

To replicate this analysis, please follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/Fusion831/EDA-of-Video-Game-Sales.git
    cd EDA-of-Video-Game-Sales
    ```

2. **Set up a virtual environment (recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install the required libraries:**

    ```bash
    pip install pandas numpy matplotlib seaborn jupyterlab
    ```

4. **Launch Jupyter:**

    ```bash
    jupyter lab
    ```

    This will open a new tab in your browser. Navigate to and open the `vgsales_analysis.ipynb` file to view the notebook.
