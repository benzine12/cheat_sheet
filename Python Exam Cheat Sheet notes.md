# Python Exam Cheat Sheet

## Basic Python Concepts

### Loops

- **For Loop**: Iterates over a sequence (like a list or string).

    ```python
    # Print numbers from 1 to 5
    for i in range(1, 6):
        print(i)
    ```

- **While Loop**: Repeats as long as a condition is true.

    ```python
    counter = 0
    while counter < 5:
        print(counter)
        counter += 1
    ```

### Functions

- **Defining Functions**: Use the `def` keyword.

    ```python
    def greet(name):
        return f"Hello, {name}!"
    ```

### Main Execution

- **`if __name__ == '__main__':`**: Ensures code runs only when the script is executed directly, not imported.

    ```python
    if __name__ == '__main__':
        main()
    ```

## Working with Files

### Reading and Writing Files

- **Reading and Writing Files**: Use `open()` for file operations.

    ```python
    # Writing to a file
    with open('example.txt', 'w') as file:
        file.write('Hello, World!')

    # Reading from a file
    with open('example.txt', 'r') as file:
        content = file.read()
        print(content)
    ```

- **Using "with" Statement**: Ensures files are properly closed after use.

## Data Management

### Enumerate

- **Enumerate**: Iterate over a list with an index.

    ```python
    fruits = ['apple', 'banana', 'orange']
    for index, fruit in enumerate(fruits):
        print(f"Index {index}: {fruit}")
    ```

### CSV Files

- **CSV Files**: Store tabular data in plain text. You can read and write CSV files using the `csv` module or `pandas`.

## Pandas Library

### Data Manipulation

- **Installing Pandas**: Install with pip.

    ```bash
    pip install pandas
    ```

- **Using Pandas**: For powerful data manipulation and analysis.

    ```python
    import pandas as pd

    # Creating a DataFrame
    data = {'Name': ['Alice', 'Bob', 'Charlie'],
            'Age': [25, 30, 35]}
    df = pd.DataFrame(data)
    print(df)

    # Reading from a CSV file
    df = pd.read_csv('data.csv')

    # Writing to a CSV file
    df.to_csv('output.csv', index=False)

    # Filtering data
    filtered_df = df[df['Age'] > 30]

    # Grouping and aggregating data
    grouped = df.groupby('Name').agg({'Age': 'mean'})
    ```

## Database Operations with SQLite

- **CRUD Operations**: Create, Read, Update, Delete operations with SQLite.

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

- **Try and Except**: Handle exceptions in code.

    ```python
    try:
        # Code that may raise an exception
    except ValueError:
        # Handle specific error
    except Exception as e:
        # Handle any other exceptions
        print(f"Unexpected error: {e}")
    ```

## Package Management

### Virtual Environments

- **Using Virtual Environments**: For project-specific library versions.

    ```bash
    # Install virtual environment
    pip install virtualenv

    # Create a virtual environment
    python3 -m virtualenv env

    # Activate the environment
    . env/bin/activate  # On Windows: env\Scripts\activate

    # Deactivate the environment
    deactivate
    ```

## SQL Operations

### SQLite

- **SQL Operations**: Use Primary Key, Foreign Key, Inner Join, and CRUD operations.

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

## Additional Python Concepts

### Modules and Packages

- **Using Modules**: Import and use built-in or third-party modules.

    ```python
    import math
    print(math.pi)
    ```

- **Creating Custom Modules**: Write your own modules for reusable code.

    ```python
    # mymodule.py
    def greet(name):
        return f"Hello, {name}!"

    # main.py
    import mymodule
    print(mymodule.greet("Alice"))
    ```

### Organizing Code

- **Using `main()`**: For better code structure.

    ```python
    def main():
        print("This is the main function")

    if __name__ == "__main__":
        main()
    ```

## Lesson Highlights

### Lesson 22.8.24

- **REST-API**: Interface for interacting with software methods (e.g., Windows or iOS).
- **TOKEN**: Unique identifier for API authentication and authorization.
- **TERMINAL - CLI**: Command Line Interface for interacting with the OS.
- **XMLHTTP**: API for making asynchronous HTTP requests in web apps.

### Lesson 27.8.24

- **Pylint**: Tool for assessing Python code quality.
- **Package Management**: Use of virtual environments and managing dependencies.

### Lesson 29.8.24

- **Primary Key and Foreign Key**: Used in database management to ensure data integrity.
- **SQL Aggregate Functions**: Functions like `COUNT` and `AVG` for summarizing data.
- **Inner Join**: SQL command to combine tables.

- **Virtual Environment and Requirements**: Use virtual environments for project-specific dependencies and requirements.txt for listing them.

```bash
# Create and activate virtual environment
python -m venv myenv
source myenv/bin/activate  # On Windows: myenv\Scripts\activate

# Create requirements.txt
pip freeze > requirements.txt

# Install from requirements.txt
pip install -r requirements.txt
```

## cntrl c + cntrl v this : 

### clear console : 

```
import os
def clearScreen():
    os.system('cls' if os.name == 'nt' else 'clear')
```

### enum and shit : 
```
from enum import Enum

class Selection(Enum):
    ADD = 1
    DELETE = 2
    SHOW = 3
    SEARCH = 4
    CLEAR = 5
    EDIT = 6
    EXIT = 7

def menu():
    for item in Selection:print(f'{item.value} - {item.name}')
    return   Selection(int( input("your selection: ")))
```

### start the program with this : 
```
if __name__ == '__main__':
    main()
```
