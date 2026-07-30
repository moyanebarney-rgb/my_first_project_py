# my_first_project_py

A beginner-friendly Python and SQL project that demonstrates core data analysis skills: creating a database, writing queries, and exporting results to CSV.

---

## 📌 What This Project Does

This project simulates a simple employee and department database. It demonstrates:

- Creating a SQLite database and tables
- Inserting sample data
- Writing and executing SQL queries
- Exporting query results to CSV files

---

## 📊 The Queries

This project includes **nine SQL queries** that build on each other:

| Query | Type | What It Does |
| :--- | :--- | :--- |
| **Query 1** | Basic Filter (`WHERE`) | Filters employees by department |
| **Query 2** | Table Join (`JOIN`) | Combines employee and department data |
| **Query 3** | Comparison Filter (`WHERE >`) | Finds employees earning above a threshold |
| **Query 4** | Aggregation (`GROUP BY` + `SUM`) | Calculates total salary per department |
| **Query 5** | Aggregation + Sorting (`AVG`, `COUNT`, `ORDER BY`) | Department stats: employee count, average salary, total salary |
| **Query 6** | Filtered Aggregation (`HAVING`) | Departments where average salary exceeds 70,000 |
| **Query 7** | Ranking (`ORDER BY DESC`) | Departments ranked by total salary (highest first) |
| **Query 8** | Subquery | Employees earning above their department's average salary |
| **Query 9** | Common Table Expression (`WITH` / CTE) | Department averages compared to overall company average |

---

## 📁 Files Generated

When you run the script, it generates the following CSV files:

| File | Description |
| :--- | :--- |
| `engineering_team.csv` | Employees in the Engineering department |
| `employees_with_budgets.csv` | Employees with their department budgets |
| `high_earners.csv` | Employees earning more than 70,000 |
| `department_salary_totals.csv` | Total salary per department |
| `department_stats.csv` | Department statistics (count, average salary, total salary) |
| `high_avg_departments.csv` | Departments where average salary > 70,000 |
| `ranked_departments.csv` | Departments ranked by total salary (highest first) |
| `above_dept_avg.csv` | Employees earning above their department's average salary |
| `dept_vs_overall_avg.csv` | Department averages compared to the overall company average |

---

## 🚀 How to Run It

1. Clone this repository:
   ```bash
   git clone https://github.com/moyanebarney-rgb/my_first_project_py.git| **Query 4** | Aggregation (`GROUP BY` + `SUM`) | Calculates total salary per department |
| **Query 5** | Aggregation + Sorting (`AVG`, `COUNT`, `ORDER BY`) | Department stats: employee count, average salary, total salary |
| **Query 6** | Filtered Aggregation (`HAVING`) | Departments where average salary exceeds 70,000 |
| **Query 7** | Ranking (`ORDER BY DESC`) | Departments ranked by total salary (highest first) |

---

## 📁 Files Generated

When you run the script, it generates the following CSV files:

| File | Description |
| :--- | :--- |
| `engineering_team.csv` | Employees in the Engineering department |
| `employees_with_budgets.csv` | Employees with their department budgets |
| `high_earners.csv` | Employees earning more than 70,000 |
| `department_salary_totals.csv` | Total salary per department |
| `department_stats.csv` | Department statistics (count, average salary, total salary) |
| `high_avg_departments.csv` | Departments where average salary > 70,000 |
| `ranked_departments.csv` | Departments ranked by total salary (highest first) |

---

## 🚀 How to Run It

1. Clone this repository:
   ```bash
   git clone https://github.com/moyanebarney-rgb/my_first_project_py.git| **Query 3** | Comparison Filter (`WHERE >`) | Finds employees earning above a threshold |
| **Query 4** | Aggregation (`GROUP BY` + `SUM`) | Calculates total salary per department |
| **Query 5** | Aggregation + Sorting (`AVG`, `COUNT`, `ORDER BY`) | Department stats: employee count, average salary, total salary |
| **Query 6** | Filtered Aggregation (`HAVING`) | Departments where average salary exceeds 70,000 |

---

## 📁 Files Generated

When you run the script, it generates the following CSV files:

| File | Description |
| :--- | :--- |
| `engineering_team.csv` | Employees in the Engineering department |
| `employees_with_budgets.csv` | Employees with their department budgets |
| `high_earners.csv` | Employees earning more than 70,000 |
| `department_salary_totals.csv` | Total salary per department |
| `department_stats.csv` | Department statistics (count, average salary, total salary) |
| `high_avg_departments.csv` | Departments where average salary > 70,000 |

---

## 🚀 How to Run It

1. Clone this repository:
   ```bash
   git clone https://github.com/moyanebarney-rgb/my_first_project_py.git# 4. CREATE TABLE: departments
# ============================================
cursor.execute('''
CREATE TABLE IF NOT EXISTS departments (
    id INTEGER PRIMARY KEY,
    name TEXT,
    budget INTEGER
)
''')

# ============================================
# 5. INSERT SAMPLE DATA INTO departments
# ============================================
dept_data = [
    (1, 'Engineering', 500000),
    (2, 'Marketing', 300000),
    (3, 'Finance', 400000)
]
cursor.executemany('INSERT OR IGNORE INTO departments VALUES (?,?,?)', dept_data)
conn.commit()

# ============================================
# 6. QUERY 1: Basic Filter (WHERE)
# ============================================
query1 = "SELECT name, department FROM employees WHERE department = 'Engineering'"
cursor.execute(query1)
engineering_team = cursor.fetchall()

with open('engineering_team.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Name', 'Department'])
    writer.writerows(engineering_team)

print("Query 1 successful! Results saved to 'engineering_team.csv'")

# ============================================
# 7. QUERY 2: Join Two Tables (JOIN)
# ============================================
query2 = """
SELECT employees.name, employees.department, departments.budget
FROM employees
JOIN departments ON employees.department = departments.name
"""
cursor.execute(query2)
join_results = cursor.fetchall()

with open('employees_with_budgets.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Name', 'Department', 'Budget'])
    writer.writerows(join_results)

print("Query 2 successful! Results saved to 'employees_with_budgets.csv'")

# ============================================
# 8. QUERY 3: Filter with Comparison (WHERE >)
# ============================================
query3 = "SELECT name, department, salary FROM employees WHERE salary > 70000"
cursor.execute(query3)
high_earners = cursor.fetchall()

with open('high_earners.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Name', 'Department', 'Salary'])
    writer.writerows(high_earners)

print("Query 3 successful! Results saved to 'high_earners.csv'")

# ============================================
# 9. QUERY 4: Aggregation (GROUP BY + SUM)
# ============================================
query4 = """
SELECT department, SUM(salary) as total_salary
FROM employees
GROUP BY department
"""
cursor.execute(query4)
dept_salary = cursor.fetchall()

with open('department_salary_totals.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Department', 'Total Salary'])
    writer.writerows(dept_salary)

print("Query 4 successful! Results saved to 'department_salary_totals.csv'")

# ============================================
# 10. QUERY 5: Aggregation + Sorting (GROUP BY + AVG + COUNT + ORDER BY)
# ============================================
query5 = """
SELECT 
    department, 
    COUNT(*) as employee_count, 
    AVG(salary) as avg_salary,
    SUM(salary) as total_salary
FROM employees
GROUP BY department
ORDER BY avg_salary DESC
"""
cursor.execute(query5)
dept_stats = cursor.fetchall()

with open('department_stats.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Department', 'Employee Count', 'Average Salary', 'Total Salary'])
    writer.writerows(dept_stats)

print("Query 5 successful! Results saved to 'department_stats.csv'")

# ============================================
# 11. QUERY 6: Departments with average salary > 70,000 (HAVING)
# ============================================
query6 = """
SELECT 
    department, 
    COUNT(*) as employee_count, 
    AVG(salary) as avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 70000
"""
cursor.execute(query6)
high_avg_depts = cursor.fetchall()

with open('high_avg_departments.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['Department', 'Employee Count', 'Average Salary'])
    writer.writerows(high_avg_depts)

print("Query 6 successful! Results saved to 'high_avg_departments.csv'")

# ============================================
# 12. CLOSE CONNECTION
# ============================================
conn.close()

print("All queries executed successfully!")
