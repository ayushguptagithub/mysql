Here’s a comprehensive set of **MySQL queries** demonstrating how to create a database and perform all CRUD (Create, Read, Update, Delete) operations.

---

### 1. **Create a Database**
```sql
-- Create a new database
CREATE DATABASE my_database;

-- Use the created database
USE my_database;
```

---

### 2. **Create a Table**
```sql
-- Create a table named 'users'
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,  -- Auto-increment ID
    name VARCHAR(100) NOT NULL,         -- Name cannot be null
    email VARCHAR(100) UNIQUE NOT NULL, -- Unique email
    age INT,                            -- Optional age field
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- Auto-filled timestamp
);
```

---

### 3. **Insert Data (CREATE Operation)**
```sql
-- Insert a single record into the 'users' table
INSERT INTO users (name, email, age)
VALUES ('Alice', 'alice@example.com', 25);

-- Insert multiple records
INSERT INTO users (name, email, age)
VALUES 
    ('Bob', 'bob@example.com', 30),
    ('Charlie', 'charlie@example.com', 22);
```

---

### 4. **Read Data (READ Operation)**

#### Select All Records
```sql
-- Select all records from the 'users' table
SELECT * FROM users;
```

#### Select Specific Columns
```sql
-- Select only the 'name' and 'email' columns
SELECT name, email FROM users;
```

#### Use WHERE Clause
```sql
-- Select users older than 25
SELECT * FROM users WHERE age > 25;
```

#### Use Aggregate Functions
```sql
-- Count total users
SELECT COUNT(*) AS total_users FROM users;

-- Find the average age
SELECT AVG(age) AS average_age FROM users;
```

---

### 5. **Update Data (UPDATE Operation)**
```sql
-- Update a user's age where the name is 'Alice'
UPDATE users
SET age = 26
WHERE name = 'Alice';

-- Update multiple fields
UPDATE users
SET age = 35, email = 'updatedbob@example.com'
WHERE name = 'Bob';
```

---

### 6. **Delete Data (DELETE Operation)**
```sql
-- Delete a user where the name is 'Charlie'
DELETE FROM users
WHERE name = 'Charlie';

-- Delete all records (use cautiously)
DELETE FROM users;
```

---

### 7. **Advanced Queries**

#### Using LIKE for Pattern Matching
```sql
-- Select users whose email ends with '@example.com'
SELECT * FROM users WHERE email LIKE '%@example.com';
```

#### Sorting Data
```sql
-- Select all users and sort by age in ascending order
SELECT * FROM users ORDER BY age ASC;

-- Sort by age in descending order
SELECT * FROM users ORDER BY age DESC;
```

#### Limiting Results
```sql
-- Select only the first 2 records
SELECT * FROM users LIMIT 2;
```

---

### 8. **Drop Table or Database**

#### Drop Table
```sql
-- Delete the 'users' table
DROP TABLE users;
```

#### Drop Database
```sql
-- Delete the 'my_database' database
DROP DATABASE my_database;
```

---

### Complete Example Workflow

1. **Create Database**:
   ```sql
   CREATE DATABASE my_database;
   USE my_database;
   ```

2. **Create Table**:
   ```sql
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(100) NOT NULL,
       email VARCHAR(100) UNIQUE NOT NULL,
       age INT,
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

3. **Insert Data**:
   ```sql
   INSERT INTO users (name, email, age)
   VALUES ('Alice', 'alice@example.com', 25), ('Bob', 'bob@example.com', 30);
   ```

4. **Read Data**:
   ```sql
   SELECT * FROM users;
   ```

5. **Update Data**:
   ```sql
   UPDATE users SET age = 28 WHERE name = 'Alice';
   ```

6. **Delete Data**:
   ```sql
   DELETE FROM users WHERE name = 'Bob';
   ```

---

### Notes

- Always use the **`WHERE`** clause in `UPDATE` and `DELETE` statements to avoid unintentional changes to all rows.
- Use `SHOW DATABASES;` and `SHOW TABLES;` to list all databases and tables.
- Use `DESCRIBE table_name;` to view the structure of a table.

This workflow covers the essentials of CRUD operations in MySQL.