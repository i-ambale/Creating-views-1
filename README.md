# 📘 README: Creating Views in SQL with Chinook.db
## 🧠 Project Title
Creating Lookup, Join, and Aggregating Views in SQLite Using Chinook.db

## 📝 Description
This notebook is a practical introduction to creating and managing **SQL views** using the `Chinook.db` sample database. It covers the creation of **lookup**, **join**, and **aggregate views**, as well as how to safely **drop** views.

You’ll learn how views can simplify queries, encapsulate logic, and improve code reuse in real-world data analysis.

## 🎯 Learning Objectives
By the end of this exercise, you will be able to:

✅ Create **lookup views** to isolate reference data
✅ Create **join views** that combine multiple related tables
✅ Create **aggregating views** using functions like `COUNT()`, `SUM()`, and `AVG()`
✅ Safely **drop views** to avoid conflicts during development

## 🧩 Requirements
- Python 3.8+

- Jupyter Notebook or any Python IDE (e.g., VS Code)

- The Chinook.db SQLite database file (available [here](https://www.sqlitetutorial.net/sqlite-sample-database/)

**Required Python Libraries**
```
pip install sqlalchemy pandas sqlite3
```

## 🧱 Project Structure
```
.
├── views_exercise_1.ipynb      # Jupyter notebook with SQL view examples
├── README.md                   # Project guide and documentation
├── chinook.db                  # SQLite database file (must be downloaded separately)
└── sql/                        # Optional: contains raw .sql scripts
```

## 🔧 How to Use
1. Download the `chinook.db` file and place it in your project folder.

2. Open the `views_exercise_1.ipynb` notebook.

3. Run each cell step-by-step to:

    - Create different types of views
    
    - Query the views
    
    - Drop views as needed

💡 This notebook uses the following SQLite connection string:
```
sqlite:///chinook.db
```

## 🧪 Sample Exercises
✅ **1. Create a Lookup View**
```
CREATE VIEW Genre_Lookup_View AS
SELECT GenreId, Name
FROM genres;
```
✅ **2. Create a Join View**
```
CREATE VIEW Customer_Invoice_View AS
SELECT c.FirstName, c.LastName, i.InvoiceDate, i.Total
FROM customers c
JOIN invoices i ON c.CustomerId = i.CustomerId;
```
✅ **3. Create an Aggregating View**
```
CREATE VIEW Customer_per_Country_View AS
SELECT Country, COUNT(CustomerId) AS Customer_Count
FROM customers
GROUP BY Country;
```
🧹 **4. Drop a View**
```
DROP VIEW IF EXISTS Customer_per_Country_View;
```

## 📚 Learning Benefits
- Improves query reuse by encapsulating logic into named views

- Helps modularize complex joins and aggregations

- Enhances security and clarity in SQL reporting and BI workflows

## 📧 Contact
**Author**: Ibrahim Ambale
📍 Nairobi, Kenya
🔗 LinkedIn: [Ibrahim Ambale](https://linkedin.com/in/ibrahim-ambale/)

