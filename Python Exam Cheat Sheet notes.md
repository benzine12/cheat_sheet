# Python Exam Cheat Sheet

## Basic Python Concepts

- **for Loop**: Iterate over a sequence (list, string, etc.).

```python
# Print numbers from 1 to 5
for i in range(1, 6):
    print(i)
```

- **while Loop**: Execute as long as a condition is true.

```python
counter = 0
while counter < 5:
    print(counter)
    counter += 1
```

- **if __name__ == '__main__':** Ensures that the code block runs only if the script is executed directly, not imported.

```python
if __name__ == '__main__':
    main()
```

## Working with Functions

- **Defining Functions**: Use `def` keyword.

```python
def greet(name):
    return f"Hello, {name}!"
```

## Data Management

- **Enumerate**: Iterate over a list with index.

```python
fruits = ['apple', 'banana', 'orange']
for index, fruit in enumerate(fruits):
    print(f"Index {index}: {fruit}")
```

- **CSV Files**: Store tabular data in plain text.
- **Pandas Library**: Read and write data from various formats.

## Database Operations with SQLite

- **CRUD Operations**: Create, Read, Update, Delete.

```python
import sqlite3

# Connect to SQLite database
conn = sqlite3.connect('example.db')
cursor = conn.cursor()

# Create table
cursor.execute('''CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)''')

# Insert data
cursor.execute("INSERT INTO users (name, age) VALUES (?, ?)", ("Alice", 30))

# Fetch data
cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()

# Update data
cursor.execute("UPDATE users SET age = ? WHERE name = ?", (35, "Alice"))

# Delete data
cursor.execute("DELETE FROM users WHERE name = ?", ("Bob",))

# Commit changes and close connection
conn.commit()
conn.close()
```

## Error Handling

- **try and except**: Handle exceptions in code.

```python
try:
    # Code that may raise an exception
except ValueError:
    # Handle specific error
except Exception as e:
    # Handle any other exceptions
    print(f"Unexpected error: {e}")
```

## Lesson Highlights

### Lesson 22.8.24

- **REST-API**: Interface for interacting with software methods, such as Windows or iOS.
- **TOKEN**: Unique identifier for authentication and authorization in APIs.
- **TERMINAL - CLI**: Allows sending commands to the OS or other software.
- **XMLHTTP**: API enabling asynchronous HTTP requests in web apps.

### Lesson 27.8.24

- **Pylint**: Tool for rating code quality in Python.
- **Package Management**: Use of virtual environments and managing dependencies.
- **Virtual Environments**: Allow project-specific library versions.

```python
# Install virtual environment
pip install virtualenv

# Create a virtual environment
python3 -m virtualenv env

# Activate the environment
. env/bin/activate

# Deactivate the environment
deactivate
```

### Lesson 29.8.24

- **SQL Operations**: Primary Key, Foreign Key, Inner Join, and CRUD operations.
- **SQLite**: Built-in database in Python.

```python
import sqlite3

# Connect to the SQLite database
con = sqlite3.connect('tutorial.db')

# Create a cursor object to execute SQL commands
cursor = con.cursor()

# Execute a SQL query
res = cursor.execute('SELECT name FROM sqlite_master')

# Commit the changes
con.commit()
```

Here is some additional information from the specified lessons:

### Lesson 22.8.24

- **REST-API**: An interface for interacting with software methods, such as Windows or iOS.
- **TOKEN**: A unique identifier used for authentication and authorization in APIs. It allows secure access to protected resources without sharing login details with each request.
- **TERMINAL - CLI**: Allows sending commands to the OS or other software. You can open the terminal by pressing Control + J.
- **XMLHTTP**: An API enabling asynchronous HTTP requests in web apps without reloading the entire page.

### Lesson 27.8.24

- **Pylint**: A tool for rating code quality in Python.
- **Package Management**: Includes using virtual environments to manage library versions. For example, use `pip install virtualenv` to create a virtual environment.
- **Virtual Environments**: Allow project-specific library versions, ensuring compatibility. Commands include activating, deactivating, and installing dependencies.

### Lesson 29.8.24

- **Primary Key**: Ensures each row in a database table is unique.
- **Foreign Key**: A column linked to a primary key in another table, referencing data from that table.
- **SQL Aggregate Functions**: Return a single answer from a set of values, such as `count` and `average`.
- **Inner Join**: A command to combine tables for selecting data from multiple tables.

Here's how you can work with files and use Pandas in Python, along with examples:

## Working with Files in Python

- **Reading and Writing Files**: Python provides built-in functions to handle file operations such as reading from and writing to files.

```python
# Writing to a file
with open('example.txt', 'w') as file:
    file.write('Hello, World!')

# Reading from a file
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```

- **Using "with" Statement**: The `with` statement is used for resource management and ensures that the file is properly closed after its suite finishes, even if an exception is raised.

## Working with Pandas in Python

- **Installing Pandas**: You can install Pandas using pip.

```bash
pip install pandas
```

- **Using Pandas for Data Manipulation**: Pandas is a powerful library for data manipulation and analysis, especially for working with structured data.

```python
import pandas as pd

# Creating a DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [25, 30, 35]}
df = pd.DataFrame(data)

# Displaying the DataFrame
print(df)

# Reading from a CSV file
df = pd.read_csv('data.csv')

# Writing to a CSV file
df.to_csv('output.csv', index=False)
```

These examples demonstrate basic file operations and how to use Pandas to manipulate data and perform I/O operations with CSV files.