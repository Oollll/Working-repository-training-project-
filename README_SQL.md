# SQL

## Requirements

# Tasks: 


#### 1. Create a database.
```
sqlite3 test.db
```

#### a. Add 2 tables and fill with some values.
```
CREATE TABLE Employees (
    id INTEGER PRIMARY KEY,
    first_name TEXT,
    last_name TEXT,
    position TEXT,
    salary REAL
);

CREATE TABLE Tasks (
    id INTEGER PRIMARY KEY,
    employee_id INTEGER,
    task_name TEXT,
    status TEXT
);

INSERT INTO Employees (first_name, last_name, position, salary) VALUES ('John', 'Doe', 'Manager', 5000.00);
INSERT INTO Employees (first_name, last_name, position, salary) VALUES ('Jane', 'Smith', 'Developer', 4000.00);

INSERT INTO Tasks (employee_id, task_name, status) VALUES (1, 'Project A', 'Pending');
INSERT INTO Tasks (employee_id, task_name, status) VALUES (2, 'Project B', 'Completed');
```
#### 2. Use the SELECTS for getting data.
```
SELECT * FROM Tasks;
SELECT * FROM Employees;
```

#### 3. Make backup.
```
.exit
cp test.db backup_test.db
```

#### 4. Remove one table.
```
sqlite3 test.db
DROP TABLE Tasks;
```
#### 5. Restore the backup.

```
cp backup_test.db test.db
sqlite3 test.db
.tables
```
#### 6. Remove the one database.
```
.exit 
rm test.db
```
