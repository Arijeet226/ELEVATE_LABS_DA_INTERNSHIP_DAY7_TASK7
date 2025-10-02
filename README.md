# ELEVATE_LABS_DA_INTERNSHIP_DAY7_TASK7
TASK 7: Get Basic Sales Summary from a Tiny SQLite Database using Python,Objective: Use SQL inside Python to pull simple sales info (like total quantity sold, total revenue), and display it using basic print statements and a simple bar chart.

Created a small SQLite database file (sales_data.db) with just one sales table

Connected to SQLite
conn = sqlite3.connect("sales_data.db") cursor = conn.cursor()

Create table (if it doesn't exist)
cursor.execute(""" CREATE TABLE IF NOT EXISTS sales ( id INTEGER PRIMARY KEY, product TEXT, quantity INTEGER, price REAL ) """)

Insert sample data with 10+ unique products
sales_data = [ ("Apple", 10, 5.0), ("Banana", 15, 7.5), ("Coconut", 8, 12.0), ("Dragon fruit", 20, 10.0), ("Egg", 5, 4.0), ("Fish", 18, 15.0), ("Grapes", 12, 6.5), ("Hotdog", 25, 8.0), ("Icecream", 30, 9.5), ("Jelly", 22, 11.0), ("Apple", 5, 5.0), ("Banana", 10, 7.5), ("Coconut", 12, 12.0), ("Dragon fruit", 8, 10.0), ("Egg", 14, 4.0) ]
