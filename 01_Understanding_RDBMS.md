## **Understanding RDBMS**

**RDBMS** stands for **Relational Database Management System**. It is a software system that is used to manage relational databases. A relational database organizes data into tables, which consist of rows and columns.

RDBMS provides a structured approach to store, retrieve, update, and manage data. It ensures data integrity, security, and efficient data manipulation. Some popular RDBMSs include Oracle Database, MySQL, Microsoft SQL Server, PostgreSQL, and SQLite.

Key features of an RDBMS include:

-  **Data Organization :** RDBMS organizes data into tables, where each table consists of rows (records) and columns (attributes). This tabular structure allows for easy data organization and retrieval.

-  **Data Integrity :** RDBMS enforces data integrity by supporting the concept of primary keys, which uniquely identify each row in a table. It also supports various constraints, such as unique constraints, foreign key constraints, and check constraints, to ensure data consistency and accuracy.

-  **Query Language :** RDBMS provides a structured query language (SQL) for querying and manipulating data. SQL allows users to retrieve, update, delete, and insert data into the database using simple and standardized commands.

-  **ACID Properties :** RDBMS ensures data consistency and reliability by adhering to the ACID (Atomicity, Consistency, Isolation, Durability) properties. ACID guarantees that database transactions are executed reliably and that data remains consistent even in the event of system failures or interruptions.

-  **Concurrent Access and Transaction Management :** RDBMS supports concurrent access to the database by multiple users or applications while ensuring data consistency. It manages transactions, which are sets of database operations that must be executed together as a single unit to maintain the integrity of the data.

-  **Security :** RDBMS provides mechanisms for securing the data stored in the database. It supports user authentication, access control, and data encryption to protect against unauthorized access and ensure data privacy.

---

While using RDBMS we need to follow normalization. Normalization is a set of rules or guidelines in relational database design that help eliminate redundancy and improve data integrity. The main objectives of normalization are to minimize data duplication, ensure data consistency, and enhance data efficiency. There are several normal forms defined in the normalization process, including:

-  **First Normal Form (1NF) :** 
    
    This rule states that each column in a table must hold atomic values, meaning that it should contain only indivisible and single-valued data. It prohibits storing multiple values in a single column or repeating groups of columns.

    Following are the key characteristics of 1NF:

    1. **Atomic Values :** 
        
        Each column in a table should hold atomic (indivisible) values. This means that a column should contain only a single value of the appropriate data type. It should not contain multiple values or composite data.

    2. **Unique Column Names :** 
        
        Each column in a table must have a unique name. This ensures that each attribute or piece of information is represented by a distinct column.

    3. **Orderless Rows :** 
    
        The order in which rows are stored in a table should not matter. The relational model treats tables as unordered sets of rows, and the order of rows should not affect data retrieval or manipulation.

    4. **Primary Key :** 
    
        Each table should have a primary key that uniquely identifies each row in the table. The primary key can consist of one or more columns. It ensures that each row has a unique identifier and provides a means for referencing and linking data between tables.

    5. **No Repeating Groups :** 
    
        A table should not contain repeating groups or arrays of values within a single row or column. Each column should contain only one value from the domain of that attribute. If there are multiple values, they should be stored in separate rows or tables.

    ---

    For example, we have a table called "Students" with the following columns: 
    -  StudentID (primary key)
    -  StudentName
    -  PhoneNumbers. 
    
    In this table, StudentID uniquely identifies each student, but the PhoneNumbers column contains multiple phone numbers for a single student, separated by commas.

    | StudentID | StudentName | PhoneNumbers |
    |-----------|-------------|--------------|
    | 1 | Ramesh | 795608, 325468 |
    | 2 | Suresh | 550932, 243509 |

    This table violates 1NF because the PhoneNumbers column contains multiple values (comma-separated phone numbers), and it does not have atomic values.

    To convert this table into 1NF, we need to ensure that each attribute holds atomic values. We can achieve this by separating the phone numbers into multiple rows, with each row containing only one phone number. Additionally, we'll remove the duplicate StudentID and StudentName entries.

    Here is the modified table in 1NF:

    | StudentID | StudentName | PhoneNumbers |
    |-----------|-------------|--------------|
    | 1 | Ramesh | 795608 |
    | 1 | Ramesh | 325468 |
    | 2 | Suresh | 243509 |
    | 2 | Suresh | 550932 |

    In the modified table, each phone number is placed in a separate row, ensuring atomicity. The StudentID and StudentName are repeated for each phone number associated with a student.

    ---

-  **Second Normal Form (2NF) :** 

    In addition to meeting 1NF, this rule states that each non-key column in a table should depend on the entire primary key, rather than just a part of it. It eliminates partial dependencies by separating data into multiple related tables.

    Following are the key characteristics of 2NF:

    1. **Meet the requirements of 1NF :**
        
        Before achieving 2NF, the table must already satisfy the conditions of First Normal Form, which include atomic values, unique column names, orderless rows, and a primary key.

    2. **Remove Partial Dependencies :** 
    
        2NF eliminates partial dependencies, which occur when a non-key attribute depends on only a portion of the primary key rather than the entire key.

    To achieve 2NF, the table must be decomposed into multiple tables, where each new table represents a subset of the original data with a unique primary key. The process involves identifying partial dependencies and separating them into separate tables.

    ---

    For example, we have a table called "Orders" with the following columns: 
    -  OrderID (primary key)
    -  ProductID (primary key)
    -  ProductName
    -  Quantity. 
    
    Here, the primary key is a composite key consisting of OrderID and ProductID.

    In this case, if ProductName depends on the ProductID alone and not on the entire primary key (OrderID and ProductID), it indicates a partial dependency. To achieve 2NF, we need to decompose the table into two separate tables:

    -  Table 1: Orders (OrderID, ProductID, Quantity)
    -  Table 2: Products (ProductID, ProductName)

    By separating the attributes into different tables, we ensure that ProductName depends on the entire primary key in the Products table, avoiding partial dependencies.

    ---

-  **Third Normal Form (3NF) :** 

    In addition to meeting 2NF, this rule states that each non-key column in a table should depend only on the primary key and not on any other non-key columns. It eliminates transitive dependencies by further splitting tables based on the dependencies of the data.

    The key characteristics of 3NF are as follows:

    1. **Meet the requirements of 1NF and 2NF :** 
    
        Before achieving 3NF, the table must already satisfy the conditions of First Normal Form (atomic values, unique column names, orderless rows, and a primary key) and Second Normal Form (eliminating partial dependencies).

    2. **Remove Transitive Dependencies :** 
    
        3NF eliminates transitive dependencies, which occur when a non-key attribute depends on another non-key attribute rather than directly on the primary key.

    To achieve 3NF, the table must be further decomposed, and the non-key attributes that depend on other non-key attributes should be placed in separate tables.

    ---

    For example, we have a table called "Employees" with the following columns: 
    -  EmployeeID (primary key)
    -  DepartmentID (foreign key)
    -  DepartmentName
    -  ManagerName. 
    
    Here, EmployeeID is the primary key, and DepartmentID is the foreign key referencing the Department table.

    In this case, if DepartmentName depends only on DepartmentID, and ManagerName depends on DepartmentName, it indicates a transitive dependency. To achieve 3NF, we need to decompose the table into three separate tables:

    - Table 1: Employees (EmployeeID, DepartmentID)
    - Table 2: Departments (DepartmentID, DepartmentName)
    - Table 3: Managers (DepartmentID, ManagerName)

    By separating the attributes into different tables, we ensure that each non-key attribute depends only on the primary key and not on other non-key attributes. This eliminates redundancy and maintains data integrity.

    ---

-  **Boyce-Codd Normal Form (BCNF), also known as 3.5NF :** 

    This rule is an extension of 3NF and states that every determinant (column whose value determines other column values) in a table should be a candidate key. BCNF ensures that there are no non-trivial dependencies between candidate keys.

    Folllowing are the key characteristics of BCNF:

    -  **Meet the requirements of 1NF, 2NF, and 3NF :** 
    
        Before achieving BCNF, the table must already satisfy the conditions of First Normal Form (atomic values, unique column names, orderless rows, and a primary key), Second Normal Form (eliminating partial dependencies), and Third Normal Form (eliminating transitive dependencies).

    -  **Remove Non-Trivial Dependencies :** 
    
        BCNF eliminates non-trivial dependencies, which occur when a non-key attribute depends on another non-key attribute. It ensures that every determinant (attribute that determines other attribute values) is a candidate key.

    To achieve BCNF, the table must be decomposed into multiple tables. Each new table represents a subset of the original data with a unique primary key and only those attributes that are functionally dependent on that key.

    BCNF is stricter than 3NF because it does not allow any non-trivial dependencies on non-key attributes. If a table has any such dependencies, it needs to be further decomposed until all dependencies are satisfied.

    ---

    For example, we have a table called "Employees" with the following columns: 
    -  EmployeeID (primary key)
    -  DepartmentID (primary key)
    -  DepartmentName
    -  ManagerID. 
    
    Here, EmployeeID and DepartmentID together form the composite primary key.

    However, we discover that DepartmentName depends solely on DepartmentID and not on EmployeeID. This indicates a non-trivial dependency, which violates BCNF. To rectify this, we need to decompose the table into multiple tables.

    We can decompose the table into three separate tables as follows:
    -  Table 1: Employees (EmployeeID, ManagerID)
    -  Table 2: Departments (DepartmentID, DepartmentName)
    -  Table 3: EmployeeDepartments (EmployeeID, DepartmentID)

    In this decomposition, the Employees table contains EmployeeID and ManagerID attributes, where EmployeeID serves as the primary key. The Departments table contains DepartmentID and DepartmentName, with DepartmentID as the primary key. Lastly, the EmployeeDepartments table establishes the many-to-many relationship between employees and departments by storing the EmployeeID and DepartmentID. Both EmployeeID and DepartmentID together form the primary key of the EmployeeDepartments table.

    By decomposing the original table into these three tables, we adhere to BCNF.

    ---

-  **Fourth Normal Form (4NF) :** 

    This rule deals with multi-valued dependencies. It states that a table should not contain any independent multi-valued facts. If such facts exist, they should be moved to a separate table.

    Following are the key characteristics of 4NF:

    - **Meet the requirements of 1NF, 2NF, and 3NF :** 
    
        Before achieving 4NF, the table must already satisfy the conditions of First Normal Form (atomic values, unique column names, orderless rows, and a primary key), Second Normal Form (eliminating partial dependencies), and Third Normal Form (eliminating transitive dependencies).

    - **Remove Multi-Valued Dependencies :** 
    
        4NF eliminates multi-valued dependencies, which occur when a non-key attribute depends on a combination of other non-key attributes.

    To achieve 4NF, the table must be decomposed into multiple tables. Each new table represents a subset of the original data with a unique primary key, and the multi-valued dependencies are resolved.

    ---

    For example, we have a table called "Employees" with the following columns: 
    -  EmployeeID (primary key)
    -  ProjectID (primary key)
    -  EmployeeName
    -  ProjectName
    -  Responsibilities. 
    
    Here, EmployeeID and ProjectID together form the composite primary key.

    However, we discover that Responsibilities depend solely on the combination of EmployeeID and ProjectID, indicating a multi-valued dependency. This violates 4NF as non-key attribute Responsibilities depends on a combination of other non-key attributes.

    To rectify this, we need to decompose the table into multiple tables:
    -  Table 1: Employees (EmployeeID, EmployeeName)
    -  Table 2: Projects (ProjectID, ProjectName)
    -  Table 3: EmployeeProjects (EmployeeID, ProjectID)
    -  Table 4: Responsibilities (EmployeeID, ProjectID, Responsibility)

    In this decomposition, the Employees table contains EmployeeID and EmployeeName attributes, with EmployeeID serving as the primary key. The Projects table contains ProjectID and ProjectName, with ProjectID as the primary key. The EmployeeProjects table establishes the many-to-many relationship between employees and projects by storing the EmployeeID and ProjectID. Both EmployeeID and ProjectID together form the primary key of the EmployeeProjects table. Lastly, the Responsibilities table captures the responsibilities of each employee on each project by storing the EmployeeID, ProjectID, and Responsibility.

    By decomposing the original table into these four tables, we adhere to 4NF. The multi-valued dependency is resolved, as the Responsibilities are now stored in a separate table that depends only on the combination of EmployeeID and ProjectID.

    ---

-  **Fifth Normal Form (5NF) :**

    Fifth Normal Form deals with the elimination of join dependencies, specifically the case of multi-valued dependencies that cannot be handled by 4NF. 5NF states that a database is in 5NF if and only if every join dependency in the database is implied by the candidate keys.

    Following are the key characteristic of 5NF is as follows:

    1. **Meet the requirements of 1NF, 2NF, 3NF, and 4NF :** 
    
        Before achieving 5NF, the table must already satisfy the conditions of First Normal Form (atomic values, unique column names, orderless rows, and a primary key), Second Normal Form (eliminating partial dependencies), Third Normal Form (eliminating transitive dependencies), and Fourth Normal Form (eliminating multi-valued dependencies).

    2. **Remove Join Dependencies :** 
    
        5NF eliminates join dependencies, which occur when a table can be decomposed into multiple tables in various ways, leading to redundancies and anomalies during join operations.

    To achieve 5NF, the table must be further decomposed to remove any join dependencies. This involves identifying sets of attributes that are functionally dependent on specific sets of attributes and decomposing the table accordingly.

    ---

    For example, we have a table called "Projects" with the following columns: 
    -  ProjectID (primary key)
    -  ProjectName, DepartmentID
    -  DepartmentName
    -  ManagerID. 
    
    Here, ProjectID is the primary key.

    In this case, if ProjectName, DepartmentID, and DepartmentName depend on ProjectID, and ManagerID depends on both DepartmentID and ProjectID, it indicates a join dependency. To achieve 5NF, we need to decompose the table into following multiple tables:
    -  Table 1: Projects (ProjectID, ProjectName)
    -  Table 2: Departments (DepartmentID, DepartmentName)
    -  Table 3: ProjectDepartments (ProjectID, DepartmentID)
    -  Table 4: ProjectManagers (ProjectID, DepartmentID, ManagerID)

    In this decomposition, the Projects table contains ProjectID and ProjectName attributes, with ProjectID as the primary key. The Departments table contains DepartmentID and DepartmentName, with DepartmentID as the primary key. The ProjectDepartments table establishes the many-to-many relationship between projects and departments by storing the ProjectID and DepartmentID. Both ProjectID and DepartmentID together form the primary key of the ProjectDepartments table. Lastly, the ProjectManagers table captures the relationship between projects, departments, and managers by storing the ProjectID, DepartmentID, and ManagerID.

    ---

    5NF, minimizes data anomalies, improves data organization, and optimizes the database for join operations.

-  **Domain-Key Normal Form (DK/NF) :**

    Domain-Key Normal Form addresses the issue of multiple overlapping candidate keys in a table. It requires that every non-trivial functional dependency on a table is a dependency on a candidate key and the domain of that dependency.

    Following are the key characteristics of DK/NF are as follows:

    1. **Meet the requirements of 1NF, 2NF, 3NF, and 4NF :** 
    
        Before achieving DK/NF, the table must already satisfy the conditions of First Normal Form (atomic values, unique column names, orderless rows, and a primary key), Second Normal Form (eliminating partial dependencies), Third Normal Form (eliminating transitive dependencies), and Fourth Normal Form (eliminating multi-valued dependencies).

    2. **Remove Composite Keys :** 
        
        DK/NF eliminates dependencies on composite keys, ensuring that non-key attributes are functionally dependent only on the candidate keys of the table.

    To achieve DK/NF, the table must be further decomposed to remove any dependencies on composite keys. This involves identifying functional dependencies and decomposing the table accordingly.

    ---

    For example, we have a table called "Students" with the following columns: 
    -  StudentID (primary key)
    -  CourseID (primary key)
    -  CourseName
    -  StudentName. 
    
    Here, StudentID and CourseID together form the composite primary key.

    In this case, if CourseName depends solely on CourseID and not on StudentID, and StudentName depends solely on StudentID, it indicates a dependency on composite keys. To achieve DK/NF, we need to decompose the table into following multiple tables:
    -  Table 1: Courses (CourseID, CourseName)
    -  Table 2: Students (StudentID, StudentName)
    -  Table 3: Enrollments (StudentID, CourseID)

    In this decomposition, the Courses table contains CourseID and CourseName attributes, with CourseID as the primary key. The Students table contains StudentID and StudentName attributes, with StudentID as the primary key. The Enrollments table establishes the many-to-many relationship between students and courses by storing the StudentID and CourseID. Both StudentID and CourseID together form the primary key of the Enrollments table.

    ---
