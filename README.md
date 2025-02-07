# Concept-of-Indexing-in-RDBMS


Indexing in **Relational Database Management Systems (RDBMS)** is a technique used to improve the speed of data retrieval operations. It works by creating a separate data structure on one or more columns of a table, which allows for faster search and query execution. Without an index, the database must perform a **full table scan**, which is time-consuming for large datasets.

---

## **Concept of Indexing**

An index is similar to the index in a book, where you can quickly find a topic by looking at the page number instead of reading every page.

In RDBMS, an index is a structure that stores a mapping between values in the indexed column(s) and the physical location of rows in the table.

### **Example**
Consider a table `Students` with columns `id`, `name`, and `age`:

```sql
CREATE TABLE Students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```

If you frequently search for students by their `name`, you can create an index on the `name` column:

```sql
CREATE INDEX idx_name ON Students(name);
```

Now, the database will use the index to quickly find rows with a matching name, making the search operation faster.

---

## **Types of Indexing**

1. **Primary Index**  
   Automatically created on the primary key column.

2. **Unique Index**  
   Ensures that the indexed column contains only unique values.

3. **Clustered Index**  
   Physically sorts the table rows based on the indexed column. A table can have only one clustered index.

4. **Non-Clustered Index**  
   Creates a separate structure for the index without sorting the physical rows. A table can have multiple non-clustered indexes.

5. **Composite Index**  
   Created on two or more columns to speed up queries that involve those columns together.

---

## **Advantages of Indexing**

- 🔹 **Faster query execution** – Reduces the time required to retrieve records.  
- 🔹 **Efficient sorting** – Helps in sorting data quickly.  
- 🔹 **Optimized search operations** – Improves performance of `WHERE`, `JOIN`, `ORDER BY`, and `GROUP BY` clauses.

---

## **Disadvantages of Indexing**

- 🔸 **Additional storage** – Indexes take up extra disk space.  
- 🔸 **Slower write operations** – `INSERT`, `UPDATE`, and `DELETE` operations require more time as indexes need to be updated.  
- 🔸 **Maintenance overhead** – Indexes must be maintained to remain efficient.

---

## **When to Use Indexing**
- When the table contains a large amount of data.  
- For columns that are frequently used in queries with `SELECT`, `WHERE`, `ORDER BY`, or `JOIN` clauses.

---

### **Conclusion**
Indexing is a powerful tool for optimizing database performance. However, it should be used carefully to avoid unnecessary overhead, especially in tables with frequent updates.

---

### **Want to Learn More?**
Check out the official [MySQL Documentation on Indexing](https://dev.mysql.com/doc/refman/8.0/en/mysql-indexes.html).

---
