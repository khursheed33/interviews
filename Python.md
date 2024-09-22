# Python Topics/Questions for Interview

### **L1 (Beginner) Python Topics and Questions:**
1. **Data Types:**
   - What are the basic data types in Python?
   - How can you differentiate between mutable and immutable types?

2. **Variables:**
   - How do you declare and assign a variable in Python?
   - Can a variable change its type in Python?

3. **Control Flow (if, elif, else):**
   - How does the `if` statement work in Python?
   - What is the difference between `if`, `elif`, and `else`?

4. **Loops (for, while):**
   - What is the syntax of a `for` loop in Python?
   - How does the `while` loop differ from a `for` loop?

5. **Functions:**
   - How do you define a function in Python?
   - What is the purpose of a return statement?

6. **Input and Output:**
   - How do you take user input in Python?
   - How can you print multiple variables in a single line?

7. **String Operations:**
   - How do you concatenate strings in Python?
   - How do you access a character in a string by index?

8. **Lists:**
   - How do you create a list in Python?
   - What are common list methods like append, remove, and insert?

9. **Tuples:**
   - How do you define a tuple?
   - How do tuples differ from lists?

10. **Dictionaries:**
    - What is a dictionary in Python?
    - How do you add a new key-value pair to a dictionary?

11. **Sets:**
    - What is a set in Python?
    - How do you remove duplicates from a list using sets?

12. **Basic Exception Handling:**
    - How do you handle exceptions using try-except blocks?
    - What are some common exceptions in Python?

13. **File Handling:**
    - How do you open a file in Python?
    - What is the difference between read, write, and append modes?

14. **Basic Modules (math, random, os):**
    - How do you import a module in Python?
    - What are some common functions from the `math` and `random` modules?

15. **Comments and Docstrings:**
    - How do you add comments in Python?
    - What is the purpose of docstrings in functions?

---

### **L2 (Intermediate) Python Topics and Questions:**
1. **List Comprehensions:**
   - How do you create a list comprehension?
   - How do list comprehensions improve code efficiency?

2. **Lambda Functions:**
   - What are lambda functions in Python?
   - How do lambda functions differ from regular functions?

3. **Map, Filter, Reduce:**
   - How does the `map()` function work?
   - How do `filter()` and `reduce()` work, and when would you use them?

4. **Decorators:**
   - What are decorators in Python?
   - How do you create a simple decorator?

5. **Generators:**
   - What is a generator function in Python?
   - How does a generator differ from a normal function?

6. **List vs Tuple Performance:**
   - Why are tuples faster than lists in Python?
   - When should you use a tuple over a list?

7. **Shallow vs Deep Copy:**
   - What is the difference between shallow and deep copy?
   - How do you perform deep copy in Python?

8. **Global and Nonlocal Keywords:**
   - What is the `global` keyword used for?
   - How does `nonlocal` affect variable scope?

9. **Classes and Objects:**
   - How do you create a class in Python?
   - What are instance methods and class methods?

10. **Inheritance and Polymorphism:**
    - How does inheritance work in Python?
    - What is polymorphism, and how is it implemented?

11. **Dunder Methods (Magic Methods):**
    - What are dunder (double underscore) methods?
    - How do `__str__()` and `__repr__()` differ?

12. **Iterators and Iterables:**
    - What is the difference between an iterator and an iterable?
    - How do you create a custom iterator class?

13. **Context Managers and `with` Statement:**
    - What is a context manager in Python?
    - How do you create a custom context manager using the `__enter__` and `__exit__` methods?

14. **Regular Expressions (re module):**
    - How do you use the `re` module to find patterns in strings?
    - What are common regular expression patterns for searching?

15. **Handling JSON and CSV:**
    - How do you read and write JSON files in Python?
    - How do you handle CSV data using the `csv` module?

---

### **L3 (Advanced) Python Topics and Questions:**
1. **Metaclasses:**
   - What are metaclasses in Python?
   - How do you create and use a metaclass?

2. **Descriptors:**
   - What are descriptors in Python?
   - How do you implement `__get__()`, `__set__()`, and `__delete__()` methods?

3. **Abstract Base Classes (ABC module):**
   - What are Abstract Base Classes?
   - How do you use the `abc` module to enforce method implementation?

4. **Threading and Concurrency:**
   - How does threading work in Python?
   - What is the Global Interpreter Lock (GIL), and how does it affect concurrency?

5. **Multiprocessing:**
   - What is the difference between threading and multiprocessing?
   - How do you share data between processes in Python?

6. **Asyncio and Asynchronous Programming:**
   - How do you write asynchronous code using `asyncio`?
   - What is the difference between `async` and `await`?

7. **Memory Management:**
   - How does Python handle memory management and garbage collection?
   - What is reference counting?

8. **Cython and Performance Optimization:**
   - What is Cython, and how does it improve Python performance?
   - How can you profile and optimize code performance?

9. **Coroutines and Event Loops:**
   - What are coroutines in Python?
   - How does an event loop manage coroutines?

10. **Descriptors vs Properties:**
    - How do descriptors differ from properties in Python?
    - When would you use a descriptor over a property?

11. **Mocking and Unit Testing (unittest, pytest):**
    - How do you mock objects in Python?
    - How do you create test cases using `unittest` or `pytest`?

12. **Creating Python Packages:**
    - How do you structure and create a Python package?
    - What is the role of `__init__.py`?

13. **Decorating Classes:**
    - How do you apply decorators to entire classes?
    - What is the difference between decorating a class and a method?

14. **Function Caching (functools.lru_cache):**
    - How does `lru_cache` from the `functools` module work?
    - How does caching improve performance in recursive functions?

15. **Type Hinting and Type Checking:**
    - What are type hints, and how do you use them?
    - How do you enforce type checking in Python using `mypy`?

## ORM -- 

### **1. What is ORM?**
   - Explain Object-Relational Mapping (ORM) and how it is used in web applications.
   - How does ORM bridge the gap between object-oriented programming and relational databases?

### **2. Popular ORM Libraries in Python**
   - Name some popular Python ORM libraries.
   - What are the differences between Django ORM and SQLAlchemy?

### **3. ORM vs. Raw SQL**
   - What are the advantages of using ORM over writing raw SQL queries?
   - When would you prefer raw SQL over an ORM?

### **4. Models in ORM**
   - What is a model in the context of ORM?
   - How do you define a model for a table using ORM?

### **5. Relationships in ORM**
   - How do you define one-to-many, many-to-many, and one-to-one relationships using ORM?
   - Can you give an example of a foreign key relationship in an ORM model?

### **6. Querying Data**
   - How do you perform basic CRUD operations (Create, Read, Update, Delete) using ORM?
   - How do you write complex queries like filtering, ordering, and aggregation using ORM?

### **7. Migrations in ORM**
   - What are migrations in ORM, and why are they important?
   - How do you create and apply database migrations using ORM?

### **8. Lazy vs. Eager Loading**
   - What is the difference between lazy loading and eager loading in ORM?
   - How does each approach impact performance when querying related data?

### **9. Transactions in ORM**
   - How do you handle database transactions in ORM?
   - What is the purpose of committing and rolling back transactions in ORM?

### **10. ORM Performance Optimization**
   - What are some common performance issues with ORM, and how can they be mitigated?
   - How can you optimize query performance when using ORM?

### **11. Using ORM with Multiple Databases**
   - How do you configure ORM to work with multiple databases in a single application?
   - What challenges arise when working with multiple databases using ORM?

### **12. Database Schemas and ORM**
   - How does ORM handle database schemas?
   - Can you modify an existing database schema using ORM, and how?

### **13. ORM in Unit Testing**
   - How do you write unit tests for code that interacts with ORM models?
   - What is the role of mocking in testing ORM-related functionality?

### **14. ORMs and Transactions: Savepoints**
   - What are savepoints in the context of database transactions with ORM?
   - How can savepoints be useful in long-running transactions or error handling?

### **15. Custom Queries in ORM**
   - How can you write raw SQL queries using ORM when necessary?
   - What is the benefit of using custom queries in conjunction with ORM, and how do you execute them?

## Additional --

### 1. **Python Data Structures**
   - Explain the differences between lists, sets, and dictionaries in Python.

### 2. **List Slicing**
   - How does list slicing work in Python? Provide examples.

### 3. **String Formatting**
   - What are the different ways to format strings in Python? Explain f-strings, `str.format()`, and the `%` operator.

### 4. **Python's Built-in Functions**
   - What are some commonly used built-in functions in Python? Provide examples of their usage.

### 5. **Understanding Scope**
   - What is variable scope in Python? Explain local, global, and nonlocal scopes with examples.

### 6. **The `__init__.py` File**
   - What is the purpose of the `__init__.py` file in a Python package?

### 7. **Error Handling Best Practices**
   - What are best practices for error handling in Python?

### 8. **Python's GIL (Global Interpreter Lock)**
   - What is the Global Interpreter Lock (GIL), and how does it affect multithreading in Python?

### 9. **Python Virtual Environments**
   - How do you create and manage virtual environments in Python? Why are they useful?

### 10. **Decorators with Arguments**
   - How do you create a decorator that accepts arguments? Provide an example.

### 11. **Testing in Python (unittest and pytest)**
   - What are the differences between `unittest` and `pytest` for writing tests in Python?

### 12. **Functional Programming Concepts**
   - What is functional programming, and how does Python support it? Mention concepts like map, filter, and reduce.

### 13. **Data Classes (Python 3.7+)**
   - What are data classes in Python, and how do you use them?

### 14. **Modules and Packages**
   - What is the difference between a module and a package in Python?

### 15. **Python Memory Management**
   - How does memory management work in Python? Discuss reference counting and garbage collection.

### 16. **Python's `with` Statement**
   - What is the purpose of the `with` statement, and how does it simplify resource management?

### 17. **Method Resolution Order (MRO)**
   - What is the Method Resolution Order (MRO) in Python, and how is it determined?

### 18. **The `super()` Function**
   - What is the `super()` function, and how is it used in inheritance?

### 19. **Context Managers**
   - How do you implement a context manager using a class and the `contextlib` module?

### 20. **Python Annotations**
   - What are function annotations in Python, and how can they be used to document types?
