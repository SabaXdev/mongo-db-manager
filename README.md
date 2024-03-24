# Database Manager

This Python code provides a Database Manager class that allows interaction with a MongoDB database. The class facilitates various operations such as adding, deleting, updating, and querying data from MongoDB collections.

## Requirements
- Python 3.x
- pymongo library

## Installation
1. Install Python 3.x from https://www.python.org/.
2. Install the pymongo library using pip:


## Usage
1. Ensure that MongoDB is installed and running on your system.
2. Import the DatabaseManager class into your Python script.
3. Create an instance of the DatabaseManager class.
4. Use the provided methods to interact with the MongoDB database.

## Code Structure
The code consists of the following components:

1. **regions() Function**
- Reads data from a JSON file and returns a list of regions.

2. **DatabaseManager Class**
- Manages database operations such as adding, deleting, updating, and querying data from MongoDB collections.
- Initializes a connection to the MongoDB database using MongoClient.
- Provides methods for CRUD operations and other functionalities:
  - `create_table()`: Creates a table (collection) in the database.
  - `add_data()`: Adds data to a specified collection.
  - `get_existing_relations()`: Retrieves existing relations between student and advisor.
  - `delete_row()`: Deletes a row (document) from a collection based on the provided ID.
  - `load_data()`: Loads data from a specified collection.
  - `search()`: Performs a search operation on a collection based on specified criteria.
  - `update()`: Updates a document in a collection.
  - `check_bd()`: Checks if the database has any data.
  - `list_advisors_with_students_count()`: Lists advisors with the count of associated students.
  - `list_students_with_advisors_count()`: Lists students with the count of associated advisors.

## Example
```python
from your_module import DatabaseManager

# Create an instance of DatabaseManager
db_manager = DatabaseManager()

# Example usage
regions_list = regions()
print("Regions:", regions_list)

# Add data to a collection
db_manager.add_data("students", name="John", surname="Doe", age=25, student_id=1)

# Query data from a collection
students = db_manager.load_data("students")
for student in students:
 print(student)

# Perform a search operation
result = db_manager.search("students", name="John")
print("Search result:", list(result))

# Update a document
db_manager.update("students", name="Jane", surname="Doe", age=30, id=1)

# Delete a document
db_manager.delete_row("students", row_id=1)

# List students with the count of associated advisors
students_with_advisors = db_manager.list_students_with_advisors_count(order_by=-1)
print("Students with advisors count:", students_with_advisors)
