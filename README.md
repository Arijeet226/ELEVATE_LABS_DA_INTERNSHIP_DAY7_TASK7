# ELEVATE_LABS_DA_INTERNSHIP_DAY7_TASK7
TASK 7: Get Basic Sales Summary from a Tiny SQLite Database using Python,Objective: Use SQL inside Python to pull simple sales info (like total quantity sold, total revenue), and display it using basic print statements and a simple bar chart.

Created a small SQLite database file (sales_data.db) with just one sales table

### Tools Used
SQLite (sqlite3) – Lightweight database built into Python

pandas – Data manipulation and analysis library

matplotlib – Plotting and visualization library

Jupyter Notebook – Interactive coding and documentation environment

Connected to SQLite
conn = sqlite3.connect("sales_data.db") cursor = conn.cursor()

Create table (if it doesn't exist)
cursor.execute(""" CREATE TABLE IF NOT EXISTS sales ( id INTEGER PRIMARY KEY, product TEXT, quantity INTEGER, price REAL ) """)

Insert sample data
sales_data = [ ("Apple", 10, 5.0), ("Banana", 15, 7.5), ("Coconut", 8, 12.0), ("Dragon fruit", 20, 10.0), ("Egg", 5, 4.0), ("Fish", 18, 15.0), ("Grapes", 12, 6.5), ("Hotdog", 25, 8.0), ("Icecream", 30, 9.5), ("Jelly", 22, 11.0), ("Apple", 5, 5.0), ("Banana", 10, 7.5), ("Coconut", 12, 12.0), ("Dragon fruit", 8, 10.0), ("Egg", 14, 4.0) ]

cursor.executemany("INSERT INTO sales (product, quantity, price) VALUES (?, ?, ?)", sales_data)

Save changes and close connection
conn.commit() conn.close()

print("Database updated Successfully!")

# QUERY 1
## Q-Total quantity and revenue per product
```sql
SELECT product, SUM(quantity) AS total_qty, SUM(quantity * price) AS revenue
FROM sales
GROUP BY product
```
![](https://github.com/Arijeet226/ELEVATE_LABS_DA_INTERNSHIP_DAY7_TASK7/blob/6f69658181160f8ae2f40896266659a535b824e9/revenue_by_product_barchart.png)
# QUERY 2
## Q-Total quantity sold per product
```sql
SELECT product, SUM(quantity) AS total_qty
FROM sales
GROUP BY product
```
![](https://github.com/Arijeet226/ELEVATE_LABS_DA_INTERNSHIP_DAY7_TASK7/blob/6f69658181160f8ae2f40896266659a535b824e9/sold_quantity_per_product_piechart.png)

Exporting Data to CSV
df.to_csv("updated_sales_summary.csv", index=False) print("CSV file saved: updated_sales_summary.csv")

Task Done:-
Identified the highest revenue-generating product 
Visualized revenue & quantity trends per product 
Stored processed data for future analysis (updated_sales_summary.csv
