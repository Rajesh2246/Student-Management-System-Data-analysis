# Student Management System - SQL Case Study

This repository provides a comprehensive **Student Management System** built using SQL. It includes database design, query examples, and advanced data analysis techniques for managing and analyzing student data. The project is ideal for those learning SQL or looking for practical database management examples.

---

## Overview

The **Student Management System** manages various aspects of student information, including personal details, academic scores, extracurricular activities, and overall performance. It covers:

- Designing efficient database tables.
- Writing and executing SQL queries for data manipulation.
- Advanced techniques for data analysis using SQL functions and operators.

---

## ER Diagram

The system is structured around an **Entity-Relationship (ER) Diagram** that defines the relationships between tables, including:

- **Student Data**: Stores demographic and academic details.
- **Student Scores**: Tracks subject-wise scores for each student.
- **Performance Metrics**: Contains data on study habits, extracurriculars, and grades.

---

## Features

1. **Comprehensive Database Design**:
   - Organized tables for different aspects of student management.
   - Normalized structure to ensure data consistency and avoid redundancy.

2. **SQL Query Examples**:
   - Aggregate Functions: `COUNT()`, `SUM()`, `AVG()` for data summarization.
   - Conditional Queries: Use of `CASE` expressions for grade categorization.
   - Joins: Combining tables using `INNER`, `LEFT`, and `RIGHT JOIN`.
   - Subqueries: Advanced filtering and nested data analysis.

3. **Data Analysis Tools**:
   - Rank students based on their scores using `DENSE_RANK()`.
   - Categorize scores into grades (A, B, C, etc.).
   - Analyze trends in student performance and attendance.

---

## Example Queries

Here are some sample queries included in the project:

1. **Second Highest GPA**:
   ```sql
   SELECT MAX(GPA) 
   FROM `students data` 
   WHERE GPA NOT IN (SELECT MAX(GPA) FROM `students data`);
   ```

2. **Grade Categorization**:
   ```sql
   SELECT Math_Score,
          CASE
              WHEN Math_Score >= 90 THEN 'A'
              WHEN Math_Score >= 80 THEN 'B'
              WHEN Math_Score >= 70 THEN 'C'
              WHEN Math_Score >= 60 THEN 'D'
              ELSE 'F'
          END AS Grade
   FROM `students score`
   ORDER BY Grade;
   ```

3. **Ranking Students**:
   ```sql
   SELECT first_name, history_score,
          DENSE_RANK() OVER (ORDER BY history_score DESC) AS Rank
   FROM `student-details`
   LIMIT 100;
   ```

4. **Join Example**:
   ```sql
   SELECT DISTINCT s.first_name, p.parental_level_of_education
   FROM studentsperformance s
   LEFT JOIN `student-details` p ON s.gender = p.gender
   ORDER BY s.first_name;
   ```

---

## How to Use

1. **Setup**:
   - Import the provided SQL scripts into your database management system (e.g., MySQL, PostgreSQL).
   - Ensure the database environment is correctly configured.

2. **Run Queries**:
   - Execute the SQL queries for data retrieval and analysis.
   - Modify the queries as needed for specific use cases.

3. **Analyze Data**:
   - Use the queries to gain insights into student performance, attendance patterns, and academic trends.

---

## Key Highlights

- **Performance Analysis**: Identify high-performing students and areas of improvement.
- **Customizable Queries**: Adaptable for different datasets or educational contexts.
- **Learning Resource**: An excellent guide for SQL learners and database practitioners.

---

## Conclusion

This case study showcases how SQL can be used to manage and analyze complex datasets. It highlights key database management practices and demonstrates how to leverage SQL for extracting actionable insights. Use this project as a resource for learning, teaching, or implementing database solutions.

---


