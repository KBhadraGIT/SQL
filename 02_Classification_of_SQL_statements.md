## **Classification of SQL statements & Data types in SQL:**

---

1. **Data Manipulation Language (DML) Statements :**
    
    DML statements are used to retrieve, manipulate, and manage data within the database. This includes the following:
    -  SELECT: Retrieves data from one or more tables using queries and can include filtering, sorting, and aggregating data.
    -  INSERT: Inserts new records into a table to add data.
    -  UPDATE: Modifies existing records in a table to change data.
    -  DELETE: Removes records from a table to delete data.
    -  MERGE: Performs an INSERT, UPDATE, or DELETE operation based on a condition, combining multiple operations into a single statement.
    -  UPSERT: Updates a record if it exists or inserts a new record if it doesn't exist, handling both update and insert operations.

2. **Data Definition Language (DDL) Statements :**

    DDL statements are used to define, modify, and manage the structure of the database objects. This includes the following:
    -  CREATE: Creates a new database, table, view, index, stored procedure, or other database objects.
    -  ALTER: Modifies the structure of an existing database object, such as adding, modifying, or dropping columns or constraints.
    -  DROP: Deletes an existing database object, such as a table, view, or index.
    -  TRUNCATE: Removes all data from a table but keeps the table structure intact.
    -  COMMENT: Adds comments or annotations to database objects for documentation purposes.
    -  RENAME: Renames a database object, such as a table or column.

3. **Data Control Language (DCL) Statements :**

    DCL statements are used to control access and permissions to the database objects. This includes the following:
    -  GRANT: Grants specific privileges and permissions to users or user roles.
    -  REVOKE: Revokes previously granted privileges and permissions from users or user roles.

4. **Transaction Control Statements :**
    
    Transaction control statements are used to manage the transactional behavior of the database. This includes the following:
    -  COMMIT: Saves all the changes made within a transaction permanently to the database.
    -  ROLLBACK: Undoes all the changes made within a transaction, reverting the database to its previous state.
    -  SAVEPOINT: Sets a named point within a transaction to which the transaction can be rolled back.

5. **Data Query Language (DQL) Statements :**
    
    DQL statements are used to retrieve data from the database, similar to DML statements.  This includes the following:
    -  SELECT: Retrieves data from one or more tables using queries, including filtering, sorting, and aggregating data.
    -  Filtering with WHERE Clause
    -  Sorting with ORDER BY Clause
    -  Aggregation with GROUP BY Clause
    -  Joining Tables

---

In SQL the data types are broadly categorised into following sections:
1. Character String
2. Numeric
3. Date & time
4. Binary

### **Character String data types :**

1. CHAR:
    
    -  Description: Fixed-length character string.
    -  Syntax: CHAR(n), where 'n' specifies the fixed length.
    -  Example: CHAR(10) represents a character string of length 10.

2. VARCHAR:

    -  Description: Variable-length character string.
    -  Syntax: VARCHAR(n), where 'n' specifies the maximum length.
    -  Example: VARCHAR(255) represents a character string with a maximum length of 255 characters.

3. TEXT:

    -  Description: Variable-length character string for storing large amounts of text data.
    -  Syntax: TEXT.
    -  Example: TEXT can store large text values such as paragraphs, documents, or lengthy descriptions.

4. NCHAR:

    -  Description: Fixed-length character string that supports Unicode characters.
    -  Syntax: NCHAR(n), where 'n' specifies the fixed length.
    -  Example: NCHAR(10) represents a Unicode character string of length 10.

5. NVARCHAR:

    -  Description: Variable-length character string that supports Unicode characters.
    -  Syntax: NVARCHAR(n), where 'n' specifies the maximum length.
    -  Example: NVARCHAR(255) represents a Unicode character string with a maximum length of 255 characters.

6. CLOB:

    -  Description: Stores large character strings, typically used for storing very long text data.
    -  Syntax: CLOB.
    -  Example: CLOB is suitable for storing large amounts of text, such as books, articles, or other lengthy content.

7. ENUM:

    -  Description: Represents a set of predefined values.
    -  Syntax: ENUM('value1', 'value2', ...).
    -  Example: ENUM('Red', 'Green', 'Blue') represents a set of predefined color values.

8. JSON:

    -  Description: Stores JSON (JavaScript Object Notation) data.
    -  Syntax: JSON.
    -  Example: JSON can store structured JSON data, such as nested objects, arrays, and key-value pairs.

9. UUID:

    -  Description: Stores a universally unique identifier.
    -  Syntax: UUID.
    -  Example: UUID represents a 128-bit value that is unique across all devices and time.

10. XML:

    -  Description: Stores XML (eXtensible Markup Language) data.
    -  Syntax: XML.
    -  Example: XML can store XML documents, such as structured data with tags and hierarchical relationships.


### **Numeric data types :**

1. INTEGER (INT):

-  Description: Represents whole numbers without decimal points.
-  Syntax: INT.
-  Example: INT can store values like -2,147,483,648 to 2,147,483,647.

2. SMALLINT:

-  Description: Represents small whole numbers without decimal points.
-  Syntax: SMALLINT.
-  Example: SMALLINT can store values like -32,768 to 32,767.

3. BIGINT:

-  Description: Represents large whole numbers without decimal points.
-  Syntax: BIGINT.
-  Example: BIGINT can store values like -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.

4. DECIMAL or NUMERIC:

-  Description: Represents fixed-point numbers with a specified precision and scale.
-  Syntax: DECIMAL(p, s) or NUMERIC(p, s), where 'p' represents the precision (total number of digits) and 's' represents the scale (number of digits after the decimal point).
-  Example: DECIMAL(10, 2) can store values like -999,999,999.99 to 999,999,999.99.

5. FLOAT or REAL:

-  Description: Represents floating-point numbers with a binary precision.
-  Syntax: FLOAT or REAL.
-  Example: FLOAT can store values with a range and precision that depends on the specific database implementation.

6. DOUBLE or DOUBLE PRECISION:

-  Description: Represents double-precision floating-point numbers.
-  Syntax: DOUBLE or DOUBLE PRECISION.
-  Example: DOUBLE can store values with a range and precision that depends on the specific database implementation.

7. TINYINT:

    -  Description: Represents small whole numbers typically used for flags or boolean values.
    -  Syntax: TINYINT.
    -  Example: TINYINT can store values from 0 to 255.

8. BIT or BOOLEAN:

    -  Description: Represents a binary value, often used for boolean flags or logical values.
    -  Syntax: BIT or BOOLEAN.
    -  Example: BIT or BOOLEAN can store values of 0 or 1, representing false or true, respectively.

9. REAL:

    -  Description: Represents a floating-point number with a binary precision.
    -  Syntax: REAL.
    -  Example: REAL can store values with a range and precision that depends on the specific database implementation.

10. NUMERIC or DECIMAL:

    -  Description: Represents fixed-point numbers with a specified precision and scale.
    -  Syntax: NUMERIC(p, s) or DECIMAL(p, s), where 'p' represents the precision (total number of digits) and 's' represents the scale (number of digits after the decimal point).
    -  Example: NUMERIC(8, 2) can store values like -99,999.99 to 99,999.99.

11. MONEY:

    -  Description: Represents a monetary value with a fixed precision and scale.
    -  Syntax: MONEY.
    -  Example: MONEY can store currency values with a range and precision that depends on the specific database implementation.

12. SMALLMONEY:

    -  Description: Represents a small monetary value with a fixed precision and scale.
    -  Syntax: SMALLMONEY.
    -  Example: SMALLMONEY can store smaller currency values with a range and precision that depends on the specific database implementation.


### **Date & Time data types :**   

1. DATE:

    -  Description: Represents a date without a time component.
    -  Syntax: DATE.
    -  Example: '2023-07-03' represents July 3, 2023.

2. TIME:

    -  Description: Represents a time without a date component.
    -  Syntax: TIME.
    -  Example: '13:45:00' represents 1:45 PM.

3. DATETIME or TIMESTAMP:

    -  Description: Represents a combination of date and time.
    -  Syntax: DATETIME or TIMESTAMP.
    -  Example: '2023-07-03 13:45:00' represents July 3, 2023, at 1:45 PM.

4. YEAR:

    -  Description: Represents a year value.
    -  Syntax: YEAR.
    -  Example: 2023 represents the year 2023.

5. DATETIME2:

    -  Description: Represents a combination of date and time with fractional seconds and a higher precision than DATETIME or TIMESTAMP.
    -  Syntax: DATETIME2(p), where 'p' specifies the fractional seconds precision.
    -  Example: '2023-07-03 13:45:00.1234567' represents July 3, 2023, at 1:45 PM with fractional seconds precision.

6. SMALLDATETIME:

    -  Description: Represents a combination of date and time with a lower precision than DATETIME or TIMESTAMP.
    -  Syntax: SMALLDATETIME.
    -  Example: '2023-07-03 13:45:00' represents July 3, 2023, at 1:45 PM.

7. TIMESTAMP WITH TIME ZONE:

    -  Description: Represents a combination of date and time, including the time zone information.
    -  Syntax: TIMESTAMP WITH TIME ZONE.
    -  Example: '2023-07-03 13:45:00 +03:00' represents July 3, 2023, at 1:45 PM in the time zone with an offset of +03:00.

8. TIME WITH TIME ZONE:

    -  Description: Represents a time value, including the time zone information.
    -  Syntax: TIME WITH TIME ZONE.
    -  Example: '13:45:00 +03:00' represents 1:45 PM in the time zone with an offset of +03:00.

9. TIMESTAMP WITH LOCAL TIME ZONE:

    -  Description: Represents a combination of date and time, adjusted to the local time zone of the system.
    -  Syntax: TIMESTAMP WITH LOCAL TIME ZONE.
    -  Example: '2023-07-03 13:45:00' represents July 3, 2023, at 1:45 PM in the local time zone.

10. INTERVAL:

    -  Description: Represents a duration or time span.
    -  Syntax: INTERVAL.
    -  Example: '3 days 5 hours' represents a duration of 3 days and 5 hours.

11. YEAR TO MONTH:

    -  Description: Represents a duration in terms of years and months.
    -  Syntax: YEAR TO MONTH.
    -  Example: '3-5' represents a duration of 3 years and 5 months.

12. DAY TO SECOND:

    -  Description: Represents a duration in terms of days, hours, minutes, and seconds.
    -  Syntax: DAY TO SECOND.
    -  Example: '3 05:30:15' represents a duration of 3 days, 5 hours, 30 minutes, and 15 seconds.


### **Binary data types :** 

1. BINARY:

    -  Description: Fixed-length binary data.
    -  Syntax: BINARY(n), where 'n' specifies the fixed length.
    -  Example: BINARY(10) represents binary data of length 10.

2. VARBINARY(MAX):

    -  Description: Variable-length binary data with a maximum size defined by the database system.
    -  Syntax: VARBINARY(MAX).
    -  Example: VARBINARY(MAX) can store variable-length binary data of large sizes, such as images or documents.

3. BIT:

    -  Description: Represents a single bit value (0 or 1).
    -  Syntax: BIT.
    -  Example: BIT can store a single bit value representing true or false.

4. IMAGE:

    -  Description: Stores binary data of variable length.
    -  Syntax: IMAGE.
    -  Example: IMAGE can store binary data of any size, such as images or multimedia files.

5. RAW:

    -  Description: Represents a fixed-length binary data type used in some database systems.
    -  Syntax: RAW(n), where 'n' specifies the fixed length.
    -  Example: RAW(16) represents a binary data type with a fixed length of 16 bytes.

The BLOB data types (BLOB, TINYBLOB, MEDIUMBLOB, LONGBLOB) are specifically designed to handle large binary objects, providing efficient storage for binary data of different sizes.

6. BINARY LARGE OBJECT (BLOB):

    -  Description: Stores large binary data objects.
    -  Syntax: BLOB.
    -  Example: BLOB is suitable for storing large binary data objects, such as images, videos, or other binary files.

7. TINYBLOB:

    -  Description: Stores small binary objects.
    -  Syntax: TINYBLOB.
    -  Example: TINYBLOB can store small binary data, such as small images or short binary documents.

8. MEDIUMBLOB:

    -  Description: Stores medium-sized binary objects.
    -  Syntax: MEDIUMBLOB.
    -  Example: MEDIUMBLOB can store medium-sized binary data, such as images or documents of moderate length.

9. LONGBLOB:

    -  Description: Stores extremely large binary objects.
    -  Syntax: LONGBLOB.
    -  Example: LONGBLOB is suitable for storing very large binary data, such as high-resolution images or lengthy binary documents.