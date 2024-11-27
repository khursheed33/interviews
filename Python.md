# Python Topics/Questions for Interview

**L1 (Beginner)**

### 1. **Data Types:**
   - **What are the basic data types in Python?**
     - Integer (`int`), Float (`float`), String (`str`), Boolean (`bool`), List, Tuple, Dictionary, Set.
     - Example: 
       ```python
       x = 10        # int
       y = 3.14      # float
       name = "John" # str
       is_active = True # bool
       ```
   - **How can you differentiate between mutable and immutable types?**
     - **Mutable**: Can be changed after creation (e.g., lists).
     - **Immutable**: Cannot be changed after creation (e.g., strings, tuples).
     - Example:
       ```python
       a = [1, 2, 3] # List (mutable)
       a[0] = 5      # Changing list element
       name = "John" # String (immutable)
       ```

### 2. **Variables:**
   - **How do you declare and assign a variable in Python?**
     - Just write the variable name and assign a value.
     - Example:
       ```python
       age = 25
       ```
   - **Can a variable change its type in Python?**
     - Yes, Python variables can change types.
     - Example:
       ```python
       x = 10     # int
       x = "Ten"  # Now it's a str
       ```

### 3. **Control Flow (if, elif, else):**
   - **How does the `if` statement work in Python?**
     - It checks a condition and executes code if the condition is `True`.
     - Example:
       ```python
       if x > 10:
           print("Greater than 10")
       ```
   - **What is the difference between `if`, `elif`, and `else`?**
     - `if` checks the first condition, `elif` checks another if the first is false, `else` runs if none are true.
     - Example:
       ```python
       if x > 10:
           print("Greater")
       elif x == 10:
           print("Equal")
       else:
           print("Smaller")
       ```

### 4. **Loops (for, while):**
   - **What is the syntax of a `for` loop in Python?**
     - Loops over a sequence (like a list).
     - Example:
       ```python
       for i in range(5):
           print(i)
       ```
   - **How does the `while` loop differ from a `for` loop?**
     - `while` runs until a condition becomes `False`.
     - Example:
       ```python
       i = 0
       while i < 5:
           print(i)
           i += 1
       ```

### 5. **Functions:**
   - **How do you define a function in Python?**
     - Use `def` to define a function.
     - Example:
       ```python
       def greet(name):
           print(f"Hello, {name}")
       ```
   - **What is the purpose of a `return` statement?**
     - `return` sends back a value from a function.
     - Example:
       ```python
       def add(a, b):
           return a + b
       ```

### 6. **Input and Output:**
   - **How do you take user input in Python?**
     - Use `input()` to take user input as a string.
     - Example:
       ```python
       name = input("Enter your name: ")
       ```
   - **How can you print multiple variables in a single line?**
     - Use commas in the `print()` function.
     - Example:
       ```python
       print("Name:", name, "Age:", age)
       ```

### 7. **String Operations:**
   - **How do you concatenate strings in Python?**
     - Use `+` to join strings.
     - Example:
       ```python
       full_name = "John" + " " + "Doe"
       ```
   - **How do you access a character in a string by index?**
     - Use square brackets `[]`.
     - Example:
       ```python
       name = "John"
       first_letter = name[0]  # J
       ```

### 8. **Lists:**
   - **How do you create a list in Python?**
     - Use square brackets `[]`.
     - Example:
       ```python
       numbers = [1, 2, 3, 4]
       ```
   - **What are common list methods like `append()`, `remove()`, and `insert()`?**
     - `append()`: Adds an element to the end.
     - `remove()`: Removes an element.
     - `insert()`: Inserts an element at a specific position.
     - Example:
       ```python
       numbers.append(5)
       numbers.remove(2)
       numbers.insert(1, 10)
       ```

### 9. **Tuples:**
   - **How do you define a tuple?**
     - Use parentheses `()`.
     - Example:
       ```python
       coords = (10, 20)
       ```
   - **How do tuples differ from lists?**
     - Tuples are **immutable** (cannot be changed), while lists are mutable.
     - Example:
       ```python
       coords[0] = 30  # Error: Cannot modify tuple
       ```

### 10. **Dictionaries:**
   - **What is a dictionary in Python?**
     - A collection of key-value pairs.
     - Example:
       ```python
       person = {"name": "John", "age": 25}
       ```
   - **How do you add a new key-value pair to a dictionary?**
     - Example:
       ```python
       person["city"] = "New York"
       ```

### 11. **Sets:**
   - **What is a set in Python?**
     - A collection of unique elements.
     - Example:
       ```python
       numbers = {1, 2, 3, 4, 4}  # {1, 2, 3, 4}
       ```
   - **How do you remove duplicates from a list using sets?**
     - Convert the list to a set.
     - Example:
       ```python
       numbers = [1, 2, 2, 3]
       unique_numbers = list(set(numbers))
       ```

### 12. **Basic Exception Handling:**
   - **How do you handle exceptions using `try-except` blocks?**
     - `try` runs the code, `except` handles errors.
     - Example:
       ```python
       try:
           x = 10 / 0
       except ZeroDivisionError:
           print("Cannot divide by zero")
       ```

### 13. **File Handling:**
   - **How do you open a file in Python?**
     - Use the `open()` function.
     - Example:
       ```python
       file = open("data.txt", "r")
       ```
   - **What is the difference between read, write, and append modes?**
     - `r`: Read, `w`: Write (overwrite), `a`: Append.
     - Example:
       ```python
       file = open("data.txt", "w")  # Overwrites
       ```

### 14. **Basic Modules (math, random, os):**
   - **How do you import a module in Python?**
     - Use the `import` statement.
     - Example:
       ```python
       import math
       print(math.sqrt(16))
       ```
   - **What are some common functions from the `math` and `random` modules?**
     - `math`: `sqrt()`, `pow()`.
     - `random`: `random()`, `choice()`.
     - Example:
       ```python
       import random
       print(random.choice([1, 2, 3]))
       ```

### 15. **Comments and Docstrings:**
   - **How do you add comments in Python?**
     - Use the `#` symbol for single-line comments.
     - Example:
       ```python
       # This is a comment
       ```
   - **What is the purpose of docstrings in functions?**
     - Docstrings are used to document what a function does.
     - Example:
       ```python
       def greet():
           """This function greets the user."""
           print("Hello")
       ```

**L2 (Intermediate)**

### 1. **List Comprehensions:**
   - **How do you create a list comprehension?**
     - List comprehensions allow for concise creation of lists by iterating and applying a condition or transformation.
     - Example:
       ```python
       numbers = [x for x in range(5)]  # [0, 1, 2, 3, 4]
       even_numbers = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
       ```
   - **How do list comprehensions improve code efficiency?**
     - They are faster and more concise than regular `for` loops for creating lists, as they are optimized internally in Python.

### 2. **Lambda Functions:**
   - **What are lambda functions in Python?**
     - A **lambda function** is an anonymous, short function defined using the `lambda` keyword.
     - Example:
       ```python
       add = lambda x, y: x + y
       print(add(2, 3))  # 5
       ```
   - **How do lambda functions differ from regular functions?**
     - Lambda functions are single-line, anonymous functions, typically used for short, simple operations. Regular functions are defined with `def` and can have multiple statements.

### 3. **Map, Filter, Reduce:**
   - **How does the `map()` function work?**
     - `map()` applies a function to each item in a sequence.
     - Example:
       ```python
       numbers = [1, 2, 3]
       squared = list(map(lambda x: x ** 2, numbers))  # [1, 4, 9]
       ```
   - **How do `filter()` and `reduce()` work, and when would you use them?**
     - `filter()` filters items based on a condition, and `reduce()` (from `functools`) reduces a list to a single value.
     - Example:
       ```python
       evens = list(filter(lambda x: x % 2 == 0, range(10)))  # [0, 2, 4, 6, 8]
       from functools import reduce
       product = reduce(lambda x, y: x * y, [1, 2, 3, 4])  # 24
       ```

### 4. **Decorators:**
   - **What are decorators in Python?**
     - A **decorator** is a function that wraps another function to modify or extend its behavior.
   - **How do you create a simple decorator?**
     - Example:
       ```python
       def decorator(func):
           def wrapper():
               print("Before the function")
               func()
               print("After the function")
           return wrapper

       @decorator
       def say_hello():
           print("Hello!")
       
       say_hello()
       # Output:
       # Before the function
       # Hello!
       # After the function
       ```

### 5. **Generators:**
   - **What is a generator function in Python?**
     - A generator is a function that yields values one at a time, using the `yield` keyword.
     - Example:
       ```python
       def count_up_to(n):
           count = 1
           while count <= n:
               yield count
               count += 1

       gen = count_up_to(5)
       print(list(gen))  # [1, 2, 3, 4, 5]
       ```
   - **How does a generator differ from a normal function?**
     - Generators yield values lazily (one at a time), which makes them memory efficient for large datasets.

### 6. **List vs Tuple Performance:**
   - **Why are tuples faster than lists in Python?**
     - Tuples are immutable, meaning they require less memory and are faster to process since they don't need to support operations like insertion or deletion.
   - **When should you use a tuple over a list?**
     - Use a tuple when you want to ensure that the data remains unchanged.
     - Example:
       ```python
       coords = (10, 20)  # Use tuple for fixed values
       ```

### 7. **Shallow vs Deep Copy:**
   - **What is the difference between shallow and deep copy?**
     - **Shallow copy** copies the outer object but not the nested objects, whereas **deep copy** copies everything, including nested objects.
     - Example:
       ```python
       import copy
       a = [1, [2, 3]]
       b = copy.copy(a)  # Shallow copy
       c = copy.deepcopy(a)  # Deep copy
       ```
   - **How do you perform deep copy in Python?**
     - Use `copy.deepcopy()`.
     - Example:
       ```python
       d = copy.deepcopy(a)
       ```

### 8. **Global and Nonlocal Keywords:**
   - **What is the global keyword used for?**
     - `global` allows a variable defined inside a function to refer to a global variable.
     - Example:
       ```python
       x = 10
       def modify_global():
           global x
           x = 20
       modify_global()
       print(x)  # 20
       ```
   - **How does `nonlocal` affect variable scope?**
     - `nonlocal` allows you to modify variables in the nearest enclosing scope (but not global scope).
     - Example:
       ```python
       def outer():
           x = 10
           def inner():
               nonlocal x
               x = 20
           inner()
           print(x)  # 20
       outer()
       ```

### 9. **Classes and Objects:**
   - **How do you create a class in Python?**
     - Use the `class` keyword to define a class.
     - Example:
       ```python
       class Dog:
           def __init__(self, name):
               self.name = name
           def bark(self):
               print(f"{self.name} is barking!")
       
       dog = Dog("Buddy")
       dog.bark()  # Buddy is barking!
       ```
   - **What are instance methods and class methods?**
     - **Instance methods** operate on an instance of a class. **Class methods** use `@classmethod` and operate on the class itself.
     - Example:
       ```python
       class MyClass:
           def instance_method(self):
               print("Instance method")
           @classmethod
           def class_method(cls):
               print("Class method")
       ```

### 10. **Inheritance and Polymorphism:**
   - **How does inheritance work in Python?**
     - One class (child) inherits attributes and methods from another (parent) class.
     - Example:
       ```python
       class Animal:
           def speak(self):
               print("Animal sound")
       
       class Dog(Animal):
           def speak(self):
               print("Bark")
       
       dog = Dog()
       dog.speak()  # Bark
       ```
   - **What is polymorphism, and how is it implemented?**
     - Polymorphism allows different classes to have methods with the same name, but with different behaviors.
     - Example:
       ```python
       def make_sound(animal):
           animal.speak()

       make_sound(Dog())  # Bark
       ```

### 11. **Dunder Methods (Magic Methods):**
   - **What are dunder (double underscore) methods?**
     - Special methods surrounded by double underscores, like `__init__()`, `__str__()`, and `__len__()`, used for operator overloading and custom behaviors.
   - **How do `__str__()` and `__repr__()` differ?**
     - `__str__()` is for a readable representation (used by `print()`), while `__repr__()` is for an unambiguous representation (used by `repr()`).
     - Example:
       ```python
       class Person:
           def __str__(self):
               return "Person(name)"
           def __repr__(self):
               return "Person('name')"
       ```

### 12. **Iterators and Iterables:**
   - **What is the difference between an iterator and an iterable?**
     - An **iterable** is an object that can return an iterator (e.g., lists). An **iterator** is an object that yields values one at a time using `__next__()`.
   - **How do you create a custom iterator class?**
     - Example:
       ```python
       class Counter:
           def __init__(self, limit):
               self.limit = limit
               self.count = 0
           def __iter__(self):
               return self
           def __next__(self):
               if self.count >= self.limit:
                   raise StopIteration
               self.count += 1
               return self.count
       
       counter = Counter(5)
       for i in counter:
           print(i)  # 1, 2, 3, 4, 5
       ```

### 13. **Context Managers and with Statement:**
   - **What is a context manager in Python?**
     - A context manager handles setup and teardown tasks, ensuring resources like files are properly closed after use.
   - **How do you create a custom context manager using the `__enter__` and `__exit__` methods?**
     - Example:
       ```python
       class FileManager:
           def

 __enter__(self):
               self.file = open('file.txt', 'w')
               return self.file
           def __exit__(self, exc_type, exc_val, exc_tb):
               self.file.close()

       with FileManager() as f:
           f.write('Hello, World!')
       ```

### 14. **Regular Expressions (re module):**
   - **How do you use the re module to find patterns in strings?**
     - Use `re.search()`, `re.match()`, or `re.findall()` to find patterns.
   - **What are common regular expression patterns for searching?**
     - Example:
       ```python
       import re
       pattern = r"\d+"  # Matches one or more digits
       result = re.findall(pattern, "My number is 12345")  # ['12345']
       ```

### 15. **Handling JSON and CSV:**
   - **How do you read and write JSON files in Python?**
     - Use the `json` module.
     - Example:
       ```python
       import json
       data = {"name": "John", "age": 30}
       with open('data.json', 'w') as f:
           json.dump(data, f)
       
       with open('data.json', 'r') as f:
           loaded_data = json.load(f)
       ```
   - **How do you handle CSV data using the csv module?**
     - Example:
       ```python
       import csv
       with open('data.csv', 'w') as f:
           writer = csv.writer(f)
           writer.writerow(['Name', 'Age'])
           writer.writerow(['John', 30])
       
       with open('data.csv', 'r') as f:
           reader = csv.reader(f)
           for row in reader:
               print(row)
       ```   
**L3 (Advanced)**

---

### 1. **Metaclasses**:
   - **What are metaclasses in Python?**
     Metaclasses are classes of classes. They define how classes behave and allow modification of class creation.
   - **How do you create and use a metaclass?**
     Example:
     ```python
     class Meta(type):
         def __new__(cls, name, bases, dct):
             print(f"Creating class {name}")
             return super().__new__(cls, name, bases, dct)
     
     class MyClass(metaclass=Meta):
         pass
     ```
     Output: `Creating class MyClass`

---

### 2. **Descriptors**:
   - **What are descriptors in Python?**
     Descriptors are objects that control the behavior of attribute access (get, set, delete) in a class.
   - **How do you implement `__get__()`, `__set__()`, and `__delete__()` methods?**
     Example:
     ```python
     class Descriptor:
         def __get__(self, instance, owner):
             return instance._value
         
         def __set__(self, instance, value):
             instance._value = value
         
         def __delete__(self, instance):
             del instance._value
     
     class MyClass:
         attr = Descriptor()
     
     obj = MyClass()
     obj.attr = 10
     print(obj.attr)  # 10
     ```

---

### 3. **Abstract Base Classes (ABC module)**:
   - **What are Abstract Base Classes?**
     Abstract Base Classes (ABCs) provide a way to define abstract methods that must be implemented by subclasses.
   - **How do you use the abc module?**
     Example:
     ```python
     from abc import ABC, abstractmethod

     class Shape(ABC):
         @abstractmethod
         def area(self):
             pass
     
     class Circle(Shape):
         def area(self):
             return 3.14 * 5 * 5
     
     circle = Circle()
     print(circle.area())  # 78.5
     ```

---

### 4. **Threading and Concurrency**:
   - **How does threading work in Python?**
     Threading allows multiple threads to run concurrently, sharing the same memory space.
   - **What is the Global Interpreter Lock (GIL)?**
     GIL is a mutex that protects access to Python objects, ensuring that only one thread executes Python code at a time.
     Example:
     ```python
     import threading

     def task():
         print("Task running")
     
     thread = threading.Thread(target=task)
     thread.start()
     thread.join()
     ```

---

### 5. **Multiprocessing**:
   - **What is the difference between threading and multiprocessing?**
     Threading uses threads in the same memory space, while multiprocessing creates separate processes with isolated memory.
   - **How do you share data between processes?**
     Example:
     ```python
     from multiprocessing import Process, Value

     def task(num):
         num.value += 1

     num = Value('i', 0)
     p = Process(target=task, args=(num,))
     p.start()
     p.join()
     print(num.value)  # 1
     ```

---

### 6. **Asyncio and Asynchronous Programming**:
   - **How do you write asynchronous code using asyncio?**
     `async` and `await` are used to define asynchronous functions.
   - **Example**:
     ```python
     import asyncio

     async def say_hello():
         await asyncio.sleep(1)
         print("Hello")

     asyncio.run(say_hello())
     ```

---

### 7. **Memory Management**:
   - **How does Python handle memory management?**
     Python uses reference counting and garbage collection to manage memory automatically.
   - **Example:**
     ```python
     import gc
     print(gc.isenabled())  # True (Garbage collector is enabled)
     ```

---

### 8. **Cython and Performance Optimization**:
   - **What is Cython?**
     Cython is a superset of Python that compiles to C for performance improvements.
   - **Example:**
     ```bash
     # Write Python code, convert it to Cython, and compile
     cythonize -i my_module.pyx
     ```

---

### 9. **Coroutines and Event Loops**:
   - **What are coroutines?**
     Coroutines are special functions that can pause and resume during execution.
   - **Example:**
     ```python
     import asyncio

     async def my_coroutine():
         print("Start")
         await asyncio.sleep(1)
         print("End")

     asyncio.run(my_coroutine())
     ```

---

### 10. **Descriptors vs Properties**:
   - **How do descriptors differ from properties?**
     Descriptors manage attribute access at a class level, while properties are used to manage attribute access for specific attributes.
   - **Example:**
     ```python
     class MyClass:
         def __init__(self, x):
             self._x = x

         @property
         def x(self):
             return self._x
         
         @x.setter
         def x(self, value):
             self._x = value
     ```

---

### 11. **Mocking and Unit Testing (unittest, pytest)**:
   - **How do you mock objects in Python?**
     Mocking is done using the `unittest.mock` module.
   - **Example:**
     ```python
     from unittest.mock import Mock

     mock_obj = Mock()
     mock_obj.method.return_value = "Hello"
     print(mock_obj.method())  # Hello
     ```

---

### 12. **Creating Python Packages**:
   - **How do you structure and create a Python package?**
     A package contains an `__init__.py` file and other modules.
   - **Example:**
     ```
     my_package/
         __init__.py
         module1.py
         module2.py
     ```

---

### 13. **Decorating Classes**:
   - **How do you apply decorators to entire classes?**
     Example:
     ```python
     def decorator(cls):
         cls.new_method = lambda self: print("New method")
         return cls

     @decorator
     class MyClass:
         pass

     obj = MyClass()
     obj.new_method()  # New method
     ```

---

### 14. **Function Caching (functools.lru_cache)**:
   - **How does lru_cache work?**
     It caches the results of expensive function calls to avoid recomputation.
   - **Example:**
     ```python
     from functools import lru_cache

     @lru_cache(maxsize=32)
     def fib(n):
         if n < 2:
             return n
         return fib(n-1) + fib(n-2)

     print(fib(10))  # 55
     ```

---

### 15. **Type Hinting and Type Checking**:
   - **What are type hints?**
     Type hints indicate the expected data types of variables or function parameters.
   - **Example:**
     ```python
     def add(x: int, y: int) -> int:
         return x + y
     ```

   - **How do you enforce type checking?**
     Tools like `mypy` can be used for static type checking.
     ```bash
     mypy my_script.py
     ```

--- 

**--ORM--**

### 1. **What is ORM?**
   - **Object-Relational Mapping (ORM)** is a programming technique that allows developers to interact with relational databases using object-oriented programming (OOP). It maps database tables to classes and rows to instances of those classes.
   - **How is ORM used in web applications?**  
     In web applications, ORMs provide a way to interact with the database without writing raw SQL queries. Instead, developers work with Python objects, which makes code easier to understand and maintain.

   **Example**:
   ```python
   from sqlalchemy import create_engine, Column, Integer, String
   from sqlalchemy.ext.declarative import declarative_base
   from sqlalchemy.orm import sessionmaker

   Base = declarative_base()

   class User(Base):
       __tablename__ = 'users'
       id = Column(Integer, primary_key=True)
       name = Column(String)

   engine = create_engine('sqlite:///mydb.db')
   Base.metadata.create_all(engine)
   ```

---

### 2. **Popular ORM Libraries in Python**
   - **Popular Python ORM libraries**:
     - SQLAlchemy
     - Django ORM
     - Peewee
     - Tortoise ORM
   
   - **Django ORM vs SQLAlchemy**:
     - **Django ORM**: tightly integrated with Django, simple but less flexible.
     - **SQLAlchemy**: standalone ORM, more flexible, supports complex queries.

---

### 3. **ORM vs. Raw SQL**
   - **Advantages of ORM**:
     - Abstraction from SQL.
     - Easier to maintain and scale.
     - Protects from SQL injection attacks.
   - **When to prefer raw SQL**:
     - For performance optimization.
     - For complex queries not easily handled by ORM.

   **Example of raw SQL in SQLAlchemy**:
   ```python
   from sqlalchemy import text

   result = session.execute(text("SELECT * FROM users WHERE name = :name"), {"name": "John"})
   ```

---

### 4. **Models in ORM**
   - **What is a model?**  
     A model represents a table in a database and its attributes represent table columns.
   - **Defining a model**:
   ```python
   class Product(Base):
       __tablename__ = 'products'
       id = Column(Integer, primary_key=True)
       name = Column(String)
       price = Column(Integer)
   ```

---

### 5. **Relationships in ORM**
   - **One-to-Many**:
     ```python
     class Post(Base):
         __tablename__ = 'posts'
         id = Column(Integer, primary_key=True)
         user_id = Column(Integer, ForeignKey('users.id'))
     ```

   - **Many-to-Many**:
     ```python
     association_table = Table('association', Base.metadata,
         Column('user_id', Integer, ForeignKey('user.id')),
         Column('group_id', Integer, ForeignKey('group.id'))
     )
     ```

   - **One-to-One**:
     ```python
     class Profile(Base):
         user_id = Column(Integer, ForeignKey('users.id'), unique=True)
     ```

---

### 6. **Querying Data**
   - **CRUD operations**:
     - **Create**:
       ```python
       new_user = User(name="Alice")
       session.add(new_user)
       session.commit()
       ```
     - **Read**:
       ```python
       users = session.query(User).filter_by(name="Alice").all()
       ```
     - **Update**:
       ```python
       user = session.query(User).filter_by(id=1).first()
       user.name = "Bob"
       session.commit()
       ```
     - **Delete**:
       ```python
       session.delete(user)
       session.commit()
       ```

   - **Complex Queries**:
     - **Filtering**:
       ```python
       session.query(User).filter(User.age > 20).all()
       ```
     - **Ordering**:
       ```python
       session.query(User).order_by(User.name).all()
       ```
     - **Aggregation**:
       ```python
       session.query(func.count(User.id)).scalar()
       ```

---

### 7. **Migrations in ORM**
   - **What are migrations?**  
     Migrations track changes to database schemas and apply them incrementally.
   - **Creating and applying migrations** (Django example):
     ```bash
     python manage.py makemigrations
     python manage.py migrate
     ```

---

### 8. **Lazy vs. Eager Loading**
   - **Lazy Loading**: Loads related data only when accessed.  
     Example:
     ```python
     post = session.query(Post).first()
     post.comments  # Fetches comments only now
     ```

   - **Eager Loading**: Loads related data upfront to avoid multiple database queries.
     Example:
     ```python
     post = session.query(Post).options(joinedload(Post.comments)).first()
     ```

---

### 9. **Transactions in ORM**
   - **Handling transactions**:
     Example:
     ```python
     with session.begin():
         new_user = User(name="Alice")
         session.add(new_user)
     # Auto-committed if no errors
     ```

   - **Committing and rolling back**:
     Example:
     ```python
     try:
         session.commit()
     except:
         session.rollback()
         raise
     ```

---

### 10. **ORM Performance Optimization**
   - **Common issues**:
     - N+1 query problem.
     - Unnecessary data fetching.
   
   - **Mitigations**:
     - Use eager loading.
     - Use `selectinload` for batch loading.

---

### 11. **Using ORM with Multiple Databases**
   - **Configuring ORM with multiple databases** (Django example):
     ```python
     DATABASES = {
         'default': {...},
         'other': {...}
     }
     ```

   - **Challenges**: Maintaining consistency across databases.

---

### 12. **Database Schemas and ORM**
   - **Handling database schemas**: ORMs like Django and SQLAlchemy map the database schema to Python models.
   - **Modifying schemas**: ORM migrations allow altering schema without raw SQL.

---

### 13. **ORM in Unit Testing**
   - **Unit tests**:
     Example using `pytest`:
     ```python
     def test_create_user(session):
         new_user = User(name="Alice")
         session.add(new_user)
         session.commit()
         assert new_user in session
     ```

   - **Mocking ORM**: Mock database connections to speed up tests.

---

### 14. **ORMs and Transactions: Savepoints**
   - **Savepoints**: Intermediate points in a transaction.
   - **Example**:
     ```python
     session.begin_nested()  # Savepoint
     ```

---

### 15. **Custom Queries in ORM**
   - **Writing raw SQL queries**:
     ```python
     session.execute(text("SELECT * FROM users"))
     ```
   - **Benefit**: Flexibility for complex queries.

---

**--Miscellaneous--**

### 1. **Python Data Structures**

- **Lists**: Ordered, mutable, and allow duplicate elements.
  ```python
  my_list = [1, 2, 3, 3, 4]  # List allows duplicates
  ```
- **Sets**: Unordered, mutable, and do not allow duplicates.
  ```python
  my_set = {1, 2, 3, 3, 4}  # Set automatically removes duplicates
  ```
- **Dictionaries**: Unordered, mutable, and store key-value pairs.
  ```python
  my_dict = {"name": "Alice", "age": 25}
  ```

---

### 2. **List Slicing**

List slicing allows you to retrieve a subset of a list using a start and end index.

```python
my_list = [1, 2, 3, 4, 5, 6]
print(my_list[1:4])  # [2, 3, 4]
print(my_list[:3])   # [1, 2, 3]
print(my_list[::2])  # [1, 3, 5]
```

---

### 3. **String Formatting**

- **f-strings** (Python 3.6+):
  ```python
  name = "Alice"
  print(f"Hello, {name}")
  ```
- **str.format()**:
  ```python
  print("Hello, {}".format(name))
  ```
- **% operator**:
  ```python
  print("Hello, %s" % name)
  ```

---

### 4. **Python's Built-in Functions**

Some commonly used built-in functions include:
- `len()`: Returns the length of a list, string, etc.
  ```python
  len([1, 2, 3])  # 3
  ```
- `sum()`: Returns the sum of all elements.
  ```python
  sum([1, 2, 3])  # 6
  ```
- `max()`: Returns the largest element.
  ```python
  max([1, 2, 3])  # 3
  ```

---

### 5. **Understanding Scope**

- **Local**: Variables defined inside a function.
  ```python
  def func():
      x = 10  # Local to func
  ```
- **Global**: Variables defined outside functions.
  ```python
  x = 10  # Global
  ```
- **Nonlocal**: Used to modify a variable in an enclosing function.
  ```python
  def outer():
      x = 10
      def inner():
          nonlocal x
          x = 20
  ```

---

### 6. **The `__init__.py` File**

The `__init__.py` file is used to mark a directory as a Python package, allowing the package's modules to be imported.

```bash
my_package/
    __init__.py
    module.py
```

---

### 7. **Error Handling Best Practices**

- Use specific exceptions rather than catching all exceptions.
- Avoid suppressing exceptions.
- Use `finally` for cleanup operations.

Example:
```python
try:
    result = 1 / 0
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("Cleanup")
```

---

### 8. **Python's GIL (Global Interpreter Lock)**

The **GIL** prevents multiple native threads from executing Python bytecodes simultaneously in the same process, affecting multithreading performance for CPU-bound tasks.

---

### 9. **Python Virtual Environments**

- **Creating a virtual environment**:
  ```bash
  python -m venv myenv
  ```
- **Activating it**:
  ```bash
  source myenv/bin/activate  # Linux/Mac
  myenv\Scripts\activate  # Windows
  ```

Virtual environments are useful for managing dependencies and avoiding version conflicts.

---

### 10. **Decorators with Arguments**

A decorator with arguments can be created by nesting functions.

```python
def repeat(n):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(n):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(3)
def greet():
    print("Hello!")

greet()
```

---

### 11. **Testing in Python (unittest and pytest)**

- **unittest** is built-in and follows a more traditional style.
- **pytest** is simpler, supports fixtures, and has better assertion introspection.

Example with `pytest`:
```python
def test_sum():
    assert sum([1, 2, 3]) == 6
```

---

### 12. **Functional Programming Concepts**

- **map**: Applies a function to all elements.
  ```python
  list(map(lambda x: x * 2, [1, 2, 3]))  # [2, 4, 6]
  ```
- **filter**: Filters elements based on a condition.
  ```python
  list(filter(lambda x: x > 2, [1, 2, 3]))  # [3]
  ```
- **reduce**: Reduces a list to a single value.
  ```python
  from functools import reduce
  reduce(lambda x, y: x + y, [1, 2, 3])  # 6
  ```

---

### 13. **Data Classes (Python 3.7+)**

Data classes reduce boilerplate code when creating classes with attributes.

```python
from dataclasses import dataclass

@dataclass
class User:
    name: str
    age: int

user = User(name="Alice", age=25)
print(user)
```

---

### 14. **Modules and Packages**

- **Module**: A single Python file.
  ```python
  # module.py
  def func():
      return "Hello"
  ```
- **Package**: A directory containing an `__init__.py` file and multiple modules.

---

### 15. **Python Memory Management**

- **Reference counting**: Each object keeps track of how many references point to it.
- **Garbage collection**: Python collects objects with circular references when they are no longer accessible.

---

### 16. **Python's `with` Statement**

The `with` statement simplifies resource management, such as opening and closing files automatically.

```python
with open('file.txt', 'r') as file:
    data = file.read()
```

---

### 17. **Method Resolution Order (MRO)**

MRO determines the order in which base classes are searched when a method is called. It's determined using the **C3 linearization** algorithm.

Example:
```python
class A: pass
class B(A): pass
class C(A): pass
class D(B, C): pass

print(D.mro())  # [D, B, C, A, object]
```

---

### 18. **The `super()` Function**

`super()` allows you to call methods from a parent class.

```python
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child(Parent):
    def greet(self):
        super().greet()
        print("Hello from Child")

child = Child()
child.greet()
```

---

### 19. **Context Managers**

You can implement a context manager by defining `__enter__()` and `__exit__()` methods.

```python
class MyContext:
    def __enter__(self):
        print("Entering context")
    
    def __exit__(self, exc_type, exc_value, traceback):
        print("Exiting context")

with MyContext():
    print("Inside context")
```

Alternatively, use the `contextlib` module:
```python
from contextlib import contextmanager

@contextmanager
def my_context():
    print("Entering")
    yield
    print("Exiting")

with my_context():
    print("Inside")
```

---

### 20. **Python Annotations**

Function annotations allow you to specify expected argument and return types.

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

print(greet("Alice"))
``` 

**--Comparisions--**

**REST API (Representational State Transfer Application Programming Interface)** is an architectural style for designing networked applications. It uses standard HTTP methods and is stateless, meaning that each request from a client to a server must contain all the information needed to understand and process that request.

**RESTful APIs** are APIs that adhere to the principles of REST. They typically follow a resource-based approach, allowing clients to interact with resources (data) using standard HTTP methods like GET, POST, PUT, and DELETE.

#### Key Principles of REST:
1. **Statelessness**: Each request must contain all necessary information; the server does not store session information.
2. **Client-Server Separation**: The client and server operate independently, allowing for easier development and scalability.
3. **Cacheability**: Responses must define themselves as cacheable or non-cacheable to improve performance.
4. **Uniform Interface**: A consistent method of interacting with resources, typically through URIs.

#### Example of a RESTful API Endpoint:
```http
GET /users/123
```
This endpoint retrieves the user with ID 123.

### Comparison with Non-REST APIs

| Feature                   | REST APIs                                  | Non-REST APIs                             |
|---------------------------|--------------------------------------------|------------------------------------------|
| **Architecture Style**    | Resource-oriented (CRUD)                   | Varies (SOAP, RPC, etc.)                 |
| **Statelessness**         | Yes                                        | Not necessarily                            |
| **HTTP Methods**          | Utilizes standard methods (GET, POST, etc.)| May use custom methods or protocols       |
| **Data Format**           | Typically JSON or XML                      | Varies (XML, JSON, Protocol Buffers, etc.)|
| **Caching**               | Supports caching                           | Caching mechanisms are implementation-specific |
| **Error Handling**        | Uses standard HTTP status codes           | Custom error codes or formats            |
| **Complexity**            | Generally simpler to understand            | May involve more complexity (e.g., WSDL) |

### FastAPI vs. Flask

| Feature                     | FastAPI                                 | Flask                                    |
|-----------------------------|-----------------------------------------|------------------------------------------|
| **Speed**                   | Very fast due to async capabilities    | Good, but not as fast as FastAPI        |
| **Asynchronous Support**    | Native support for async and await     | Requires extensions for async support    |
| **Data Validation**         | Automatic validation with Pydantic     | Manual validation required                |
| **Automatic Documentation** | Automatically generates OpenAPI docs   | Requires additional libraries for docs   |
| **Dependency Injection**    | Built-in support                        | Not built-in, requires extensions         |
| **Ease of Use**             | Intuitive, especially for API devs     | Simple, but may require more setup       |
| **Performance**             | High performance, suitable for high loads | Good performance, but less optimized     |

### Other Topics

#### 1. **WebSockets**
WebSockets provide a way to open a persistent connection between a client and a server for real-time communication. Unlike HTTP, which is request-response based, WebSockets allow for two-way communication.

**Example:**
```python
# FastAPI WebSocket example
from fastapi import FastAPI, WebSocket

app = FastAPI()

@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    while True:
        data = await websocket.receive_text()
        await websocket.send_text(f"Message text was: {data}")
```

#### 2. **GraphQL**
GraphQL is an alternative to REST for APIs, allowing clients to request only the data they need. It uses a single endpoint and allows for more flexible queries.

**Example:**
```graphql
query {
  user(id: "123") {
    name
    email
  }
}
```

#### 3. **API Rate Limiting**
Rate limiting is a technique to control the number of requests a user can make to an API in a given timeframe. This helps prevent abuse and ensures fair usage.

**Example in FastAPI:**
```python
from fastapi import FastAPI, Depends
from fastapi_limiter import FastAPILimiter, Limiter

limiter = Limiter(key="global")

app = FastAPI()

@app.on_event("startup")
async def startup():
    await FastAPILimiter.init(redis_client)

@app.get("/items/", dependencies=[Depends(limiter.limit("5/minute"))])
async def read_items():
    return [{"item": "Item 1"}, {"item": "Item 2"}]
```

#### 4. **API Authentication and Authorization**
Securing APIs is crucial. Common methods include:
- **Token-Based Authentication**: Using tokens (e.g., JWT) for stateless authentication.
- **OAuth2**: A protocol for authorization that allows third-party applications to access user data without sharing passwords.

#### 5. **Testing APIs**
Testing APIs ensures reliability and performance. Common tools and frameworks include:
- **Postman**: For manual API testing.
- **pytest**: For writing automated tests.
  
**Example using pytest:**
```python
def test_read_item(client):
    response = client.get("/items/1")
    assert response.status_code == 200
    assert response.json() == {"item": "Item 1"}
```

## Others ---

# Python Interview Preparation

This document is a comprehensive guide to help you prepare for a Python interview, focusing on web frameworks (FastAPI, Flask), security, authentication, testing, logging, and related concepts.

## Table of Contents

1. [FastAPI](#fastapi)
   - Introduction
   - Creating a Simple FastAPI Application
   - Request Handling
   - Dependency Injection
   - Path Parameters and Query Parameters
   - Background Tasks
   - Middlewares
2. [Flask](#flask)
   - Introduction
   - Creating a Simple Flask Application
   - Request Handling
   - Flask Blueprints
   - Flask Extensions
   - URL Building
   - Contexts and Thread Safety
3. [FastAPI vs Flask](#fastapi-vs-flask)
   - Performance
   - Flexibility
   - Ease of Use
   - Community Support
4. [Security](#security)
   - Introduction to Security in Web Applications
   - HTTPS and SSL/TLS
   - Cross-Site Scripting (XSS)
   - Cross-Site Request Forgery (CSRF)
   - SQL Injection
5. [Authentication](#authentication)
   - Introduction to Authentication
   - Token-Based Authentication (JWT)
   - OAuth2
   - OpenID Connect
6. [Models](#models)
   - Introduction to Models in Web Applications
   - Pydantic Models in FastAPI
   - SQLAlchemy Models in Flask
7. [Blueprints in Flask](#blueprints-in-flask)
   - Introduction to Blueprints
   - Creating and Registering Blueprints
   - Using Blueprints for Modular Applications
8. [OAuth2](#oauth2)
   - What is OAuth2?
   - OAuth2 Authorization Code Flow
   - Implementing OAuth2 in FastAPI
   - Using OAuth2 in Flask
9. [Azure AD Auth](#azure-ad-auth)
   - Introduction to Azure Active Directory (AD)
   - Implementing Azure AD Authentication in FastAPI
   - Using Azure AD with Flask
10. [OpenID](#openid)
    - What is OpenID Connect?
    - OpenID vs OAuth2
    - Integrating OpenID with FastAPI
    - Using OpenID in Flask
11. [Testing](#testing)
    - Introduction to Testing in Python
    - Unit Testing
    - Integration Testing
    - Testing FastAPI Applications
    - Testing Flask Applications
12. [Logging](#logging)
    - Introduction to Logging in Python
    - Configuring Logging
    - Logging in FastAPI
    - Logging in Flask

---

## FastAPI

### Introduction

FastAPI is a modern, fast (high-performance) web framework for building APIs with Python 3.7+ based on standard Python type hints. FastAPI was created by Sebastián Ramírez and has quickly gained popularity due to its ease of use and performance.

**Key Features:**
- Fast to code: Allows for fast development of applications.
- High performance: FastAPI is one of the fastest Python frameworks, only slower than Starlette and Uvicorn.
- Based on standard Python type hints: Enables automatic generation of interactive API documentation.

### Creating a Simple FastAPI Application

To create a FastAPI application, you'll need to install FastAPI and an ASGI server, such as Uvicorn.

```bash
pip install fastapi uvicorn
```

Next, create a simple application:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="0.0.0.0", port=8000)
```

Run the application:

```bash
uvicorn main:app --reload
```

Navigate to `http://127.0.0.1:8000` to see the response `{"Hello": "World"}`.

### Request Handling

FastAPI handles different types of requests such as GET, POST, PUT, DELETE, etc. You can define the request method using decorators.

```python
from fastapi import FastAPI

app = FastAPI()

@app.post("/items/")
def create_item(name: str, price: float):
    return {"name": name, "price": price}
```

### Dependency Injection

FastAPI has a powerful dependency injection system that simplifies the management of dependencies in your application.

```python
from fastapi import Depends, FastAPI

app = FastAPI()

def common_parameters(q: str = None):
    return {"q": q}

@app.get("/items/")
def read_items(commons: dict = Depends(common_parameters)):
    return commons
```

### Path Parameters and Query Parameters

FastAPI allows you to define path parameters and query parameters effortlessly.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

### Background Tasks

FastAPI provides background tasks that can run code in the background while the client receives the response.

```python
from fastapi import BackgroundTasks, FastAPI

app = FastAPI()

def write_log(message: str):
    with open("log.txt", mode="a") as log:
        log.write(message)

@app.post("/send-notification/")
async def send_notification(background_tasks: BackgroundTasks, email: str, message=""):
    background_tasks.add_task(write_log, f"notified {email}")
    return {"message": "Notification sent"}
```

### Middlewares

FastAPI supports middlewares to process requests and responses globally before they reach the endpoints or after they leave them.

```python
from fastapi import FastAPI
from starlette.middleware.base import BaseHTTPMiddleware

app = FastAPI()

class CustomMiddleware(BaseHTTPMiddleware):
    async def dispatch(self, request, call_next):
        response = await call_next(request)
        response.headers["Custom-Header"] = "Custom-Value"
        return response

app.add_middleware(CustomMiddleware)
```

---

## Flask

### Introduction

Flask is a micro web framework written in Python. It is known for its simplicity, flexibility, and fine-grained control. Flask is widely used in web development and is considered a micro-framework because it doesn’t include many built-in features like database management, form validation, or authentication.

**Key Features:**
- Lightweight: Minimalistic and easy to get started.
- Extensible: Easily extendable with numerous extensions.
- Simple: Easy to understand and learn.

### Creating a Simple Flask Application

To create a Flask application, you first need to install Flask:

```bash
pip install flask
```

Next, create a simple Flask application:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "Hello, World!"

if __name__ == "__main__":
    app.run(debug=True)
```

Run the application:

```bash
python app.py
```

Navigate to `http://127.0.0.1:5000` to see the response "Hello, World!".

### Request Handling

In Flask, requests can be handled by defining routes with corresponding request methods (GET, POST, PUT, DELETE, etc.).

```python
from flask import Flask, request

app = Flask(__name__)

@app.route('/post', methods=['POST'])
def post_request():
    data = request.get_json()
    return {"message": "Data received", "data": data}
```

### Flask Blueprints

Blueprints in Flask allow you to organize your application into modules, making it easier to manage.

```python
from flask import Blueprint

bp = Blueprint('main', __name__)

@bp.route('/')
def index():
    return "This is the main blueprint"

# In your main app
from flask import Flask
from your_blueprint_module import bp as main_bp

app = Flask(__name__)
app.register_blueprint(main_bp)
```

### Flask Extensions

Flask can be extended using various third-party extensions, such as Flask-SQLAlchemy for database integration, Flask-WTF for form handling, and more.

---

## FastAPI vs Flask

### Performance

- **FastAPI:** FastAPI is designed for speed. It uses asynchronous programming and is built on Starlette, which provides high performance.
- **Flask:** Flask is synchronous and not as fast as FastAPI. For most web applications, Flask’s performance is adequate, but for high-load APIs, FastAPI is preferable.

### Flexibility

- **FastAPI:** FastAPI is more opinionated and encourages using type hints and Pydantic for data validation.
- **Flask:** Flask is highly flexible and allows you to structure your project in almost any way you like, with fewer constraints.

### Ease of Use

- **FastAPI:** FastAPI’s use of Python type hints can make it easier for developers to catch errors early and understand the data flow in the application.
- **Flask:** Flask is simpler and has less overhead, making it easy to get started quickly.

### Community Support

- **FastAPI:** FastAPI’s community is growing rapidly, and it’s becoming the go-to framework for building APIs.
- **Flask:** Flask has a large, established community and a wide range of extensions available.

---

## Security

### Introduction to Security in Web Applications

Security is a crucial aspect of web development. Implementing security best practices protects your application from various threats such as unauthorized access, data breaches, and attacks.

### HTTPS and SSL/TLS

- **HTTPS:** Ensure that your application uses HTTPS instead of HTTP to encrypt the data transmitted between the client and the

 server.
- **SSL/TLS:** SSL (Secure Socket Layer) and its successor TLS (Transport Layer Security) are protocols that encrypt communications. Make sure your application is properly configured with SSL/TLS.

### Cross-Site Scripting (XSS)

- **XSS:** XSS attacks occur when an attacker injects malicious scripts into web pages viewed by other users. To prevent XSS:
  - Sanitize user input.
  - Use security headers like `Content-Security-Policy`.

### Cross-Site Request Forgery (CSRF)

- **CSRF:** CSRF attacks trick a user into performing actions they didn’t intend. To protect against CSRF:
  - Use anti-CSRF tokens.
  - Implement SameSite cookie attributes.

### SQL Injection

- **SQL Injection:** SQL injection attacks allow attackers to execute arbitrary SQL commands on the database. Prevent SQL injection by:
  - Using parameterized queries or prepared statements.
  - Avoiding dynamic SQL queries.

---

## Authentication

### Introduction to Authentication

Authentication is the process of verifying the identity of a user. Common authentication methods include:
- **Username and password**
- **Token-based authentication**
- **OAuth2**
- **OpenID Connect**

### Token-Based Authentication (JWT)

- **JWT:** JSON Web Tokens (JWT) are a popular method for implementing stateless authentication. A JWT contains encoded data, including a signature that verifies its authenticity.
- **Usage:** Once a user is authenticated, a JWT is issued, and the client stores it. On subsequent requests, the client sends the JWT, which the server verifies before granting access.

### OAuth2

- **OAuth2:** OAuth2 is an authorization framework that allows third-party applications to access user data without exposing credentials.
- **Usage:** OAuth2 is commonly used to allow users to log in to an application using credentials from another service (e.g., Google, Facebook).

### OpenID Connect

- **OpenID Connect:** OpenID Connect is an identity layer built on top of OAuth2 that provides authentication in addition to authorization.
- **Usage:** OpenID Connect is used to authenticate users and obtain basic profile information.

## Models

### Introduction to Models in Web Applications

Models are an essential part of web applications, representing the data and business logic of the application. Models are used to interact with the database, validate data, and define the structure of the data.

### Pydantic Models in FastAPI

In FastAPI, Pydantic models are used to define data schemas. Pydantic models provide data validation and serialization, ensuring that the data conforms to the expected structure.

```python
from pydantic import BaseModel

class Item(BaseModel):
    name: str
    description: str = None
    price: float
    tax: float = None
```

You can use these models to validate the request body:

```python
from fastapi import FastAPI

app = FastAPI()

@app.post("/items/")
def create_item(item: Item):
    return item
```

### SQLAlchemy Models in Flask

In Flask, SQLAlchemy is commonly used as an ORM (Object-Relational Mapping) to interact with the database. SQLAlchemy models define the structure of the database tables and provide an interface to query the database.

```python
from flask_sqlalchemy import SQLAlchemy

db = SQLAlchemy()

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(80), unique=True, nullable=False)
    email = db.Column(db.String(120), unique=True, nullable=False)
```

You can then use these models to perform database operations:

```python
new_user = User(username="john", email="john@example.com")
db.session.add(new_user)
db.session.commit()
```

---

## Blueprints in Flask

### Introduction to Blueprints

Blueprints are a feature in Flask that allows you to organize your application into modular components. This is especially useful for large applications, where different parts of the application can be separated into different modules or packages.

### Creating and Registering Blueprints

To create a blueprint:

```python
from flask import Blueprint

bp = Blueprint('main', __name__)

@bp.route('/')
def index():
    return "This is the main blueprint"
```

To register the blueprint in the main application:

```python
from flask import Flask
from your_blueprint_module import bp as main_bp

app = Flask(__name__)
app.register_blueprint(main_bp)
```

### Using Blueprints for Modular Applications

Blueprints allow you to create modular applications by grouping routes, templates, and static files. For example, you can have a blueprint for the authentication module, another for the admin module, and so on.

---

## OAuth2

### What is OAuth2?

OAuth2 is an authorization framework that enables third-party applications to access a user’s data without exposing the user’s credentials. It provides a secure way for users to grant access to their data without sharing their username and password.

### OAuth2 Authorization Code Flow

The OAuth2 Authorization Code Flow is the most commonly used flow. It involves the following steps:

1. The client directs the user to the authorization server's authorization endpoint.
2. The user logs in and authorizes the client.
3. The authorization server redirects the user back to the client with an authorization code.
4. The client exchanges the authorization code for an access token at the authorization server's token endpoint.
5. The client uses the access token to access the user's data from the resource server.

### Implementing OAuth2 in FastAPI

FastAPI has built-in support for OAuth2. You can implement OAuth2 using the `OAuth2PasswordBearer` class.

```python
from fastapi import FastAPI, Depends, HTTPException
from fastapi.security import OAuth2PasswordBearer

app = FastAPI()

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

@app.get("/users/me")
def read_users_me(token: str = Depends(oauth2_scheme)):
    return {"token": token}
```

### Using OAuth2 in Flask

In Flask, you can use the `authlib` or `flask-oauthlib` library to implement OAuth2.

```python
from flask import Flask, redirect, url_for
from authlib.integrations.flask_client import OAuth

app = Flask(__name__)
app.config['SECRET_KEY'] = 'secret'
oauth = OAuth(app)

github = oauth.register(
    name='github',
    client_id='GITHUB_CLIENT_ID',
    client_secret='GITHUB_CLIENT_SECRET',
    authorize_url='https://github.com/login/oauth/authorize',
    authorize_params=None,
    access_token_url='https://github.com/login/oauth/access_token',
    access_token_params=None,
    client_kwargs={'scope': 'user:email'},
)

@app.route('/login')
def login():
    return github.authorize_redirect(url_for('authorize', _external=True))

@app.route('/authorize')
def authorize():
    token = github.authorize_access_token()
    resp = github.get('user')
    user_info = resp.json()
    return user_info
```

---

## Azure AD Auth

### Introduction to Azure Active Directory (AD)

Azure Active Directory (AD) is Microsoft’s cloud-based identity and access management service. It provides secure access to Azure services, Microsoft 365, and other third-party applications.

### Implementing Azure AD Authentication in FastAPI

To integrate Azure AD authentication in a FastAPI application, you can use libraries like `msal` or `fastapi-azure-auth`. Here’s a basic example using `msal`:

```python
from fastapi import FastAPI, Depends, HTTPException
from msal import ConfidentialClientApplication

app = FastAPI()

app_config = {
    "client_id": "YOUR_CLIENT_ID",
    "authority": "https://login.microsoftonline.com/YOUR_TENANT_ID",
    "client_secret": "YOUR_CLIENT_SECRET",
}

cca = ConfidentialClientApplication(
    app_config["client_id"],
    authority=app_config["authority"],
    client_credential=app_config["client_secret"],
)

def get_access_token():
    # Obtain token
    result = cca.acquire_token_for_client(scopes=["https://graph.microsoft.com/.default"])
    if "access_token" in result:
        return result["access_token"]
    else:
        raise HTTPException(status_code=401, detail="Token acquisition failed")

@app.get("/users/")
def read_users(token: str = Depends(get_access_token)):
    return {"token": token}
```

### Using Azure AD with Flask

To implement Azure AD in Flask, you can use the `msal` library as well:

```python
from flask import Flask, redirect, url_for, session
from msal import ConfidentialClientApplication

app = Flask(__name__)
app.secret_key = 'super_secret_key'

app_config = {
    "client_id": "YOUR_CLIENT_ID",
    "authority": "https://login.microsoftonline.com/YOUR_TENANT_ID",
    "client_secret": "YOUR_CLIENT_SECRET",
}

cca = ConfidentialClientApplication(
    app_config["client_id"],
    authority=app_config["authority"],
    client_credential=app_config["client_secret"],
)

@app.route('/login')
def login():
    token = cca.acquire_token_for_client(scopes=["https://graph.microsoft.com/.default"])
    session["token"] = token["access_token"]
    return redirect(url_for("index"))

@app.route('/')
def index():
    token = session.get("token")
    if not token:
        return redirect(url_for("login"))
    return f"Token: {token}"
```

---

## OpenID

### What is OpenID Connect?

OpenID Connect is an identity layer on top of the OAuth2 protocol. It allows clients to verify the identity of the user and obtain basic profile information.

### OpenID vs OAuth2

- **OAuth2:** Primarily used for authorization. OAuth2 allows third-party applications to access user data without sharing credentials.
- **OpenID Connect:** Built on OAuth2, but focuses on authentication. OpenID Connect verifies user identity and allows for single sign-on (SSO) capabilities.

### Integrating OpenID with FastAPI

FastAPI supports OpenID Connect through its OAuth2 system. You can implement OpenID Connect in a similar way to OAuth2.

```python
from fastapi import FastAPI, Depends
from fastapi.security import OAuth2AuthorizationCodeBearer

app = FastAPI()

oauth2_scheme = OAuth2AuthorizationCodeBearer(
    authorizationUrl="https://your-openid-provider.com/auth",
    tokenUrl="https://your-openid-provider.com/token",
)

@app.get("/users/me")
def read_users_me(token: str = Depends(oauth2_scheme)):
    return {"token": token}
```

### Using OpenID in Flask

You can integrate OpenID Connect in Flask using libraries like `authlib`.

```python
from flask import Flask, redirect, url_for
from authlib.integrations.flask_client import OAuth

app = Flask(__name__)
app.secret_key = 'super_secret_key'

oauth = OAuth(app)
oidc = oauth.register(
    name='oidc',
    client_id='YOUR_CLIENT_ID',
    client_secret='YOUR_CLIENT_SECRET',
    authorize_url='https://your-openid-provider.com/auth',
    authorize_params=None,
    access_token_url='https://your-openid-provider.com/token',
    access_token_params=None,
    client_kwargs={'scope': 'openid profile email'},
)

@app.route('/login')
def login():
    return oidc.authorize_redirect(url_for('authorize', _external=True))

@app.route('/authorize')
def authorize():
    token = oidc.authorize_access_token()
    user_info = oidc.parse_id_token(token)
    return user_info
```

---

## Testing

### Introduction to Testing in Python

Testing is a crucial part of software development that ensures your application behaves as expected. Python provides several tools and frameworks for testing.

### Unit Testing

Unit testing involves testing individual components or functions of your application to ensure they work correctly in isolation. Python’s built-in

 `unittest` module is commonly used for unit testing.

```python
import unittest

def add(a, b):
    return a + b

class TestMathFunctions(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
        self.assertEqual(add(-1, 1), 0)

if __name__ == '__main__':
    unittest.main()
```

### Testing FastAPI with `pytest`

FastAPI integrates seamlessly with `pytest`, a powerful testing framework. You can test FastAPI endpoints using the `TestClient`.

```python
from fastapi import FastAPI
from fastapi.testclient import TestClient

app = FastAPI()

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}

client = TestClient(app)

def test_read_item():
    response = client.get("/items/42?q=test")
    assert response.status_code == 200
    assert response.json() == {"item_id": 42, "q": "test"}
```

### Testing Flask with `pytest`

Flask can also be tested with `pytest`. Flask’s test client can be used to simulate requests to the application.

```python
from flask import Flask

app = Flask(__name__)

@app.route("/items/<int:item_id>")
def read_item(item_id):
    return {"item_id": item_id}

def test_read_item():
    with app.test_client() as client:
        response = client.get("/items/42")
        assert response.status_code == 200
        assert response.json == {"item_id": 42}
```

Continuing from where we left off:

---

## Models

### Introduction to Models in Web Applications

Models are an essential part of web applications, representing the data and business logic of the application. Models are used to interact with the database, validate data, and define the structure of the data.

### Pydantic Models in FastAPI

In FastAPI, Pydantic models are used to define data schemas. Pydantic models provide data validation and serialization, ensuring that the data conforms to the expected structure.

```python
from pydantic import BaseModel

class Item(BaseModel):
    name: str
    description: str = None
    price: float
    tax: float = None
```

You can use these models to validate the request body:

```python
from fastapi import FastAPI

app = FastAPI()

@app.post("/items/")
def create_item(item: Item):
    return item
```

### SQLAlchemy Models in Flask

In Flask, SQLAlchemy is commonly used as an ORM (Object-Relational Mapping) to interact with the database. SQLAlchemy models define the structure of the database tables and provide an interface to query the database.

```python
from flask_sqlalchemy import SQLAlchemy

db = SQLAlchemy()

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(80), unique=True, nullable=False)
    email = db.Column(db.String(120), unique=True, nullable=False)
```

You can then use these models to perform database operations:

```python
new_user = User(username="john", email="john@example.com")
db.session.add(new_user)
db.session.commit()
```

---

## Blueprints in Flask

### Introduction to Blueprints

Blueprints are a feature in Flask that allows you to organize your application into modular components. This is especially useful for large applications, where different parts of the application can be separated into different modules or packages.

### Creating and Registering Blueprints

To create a blueprint:

```python
from flask import Blueprint

bp = Blueprint('main', __name__)

@bp.route('/')
def index():
    return "This is the main blueprint"
```

To register the blueprint in the main application:

```python
from flask import Flask
from your_blueprint_module import bp as main_bp

app = Flask(__name__)
app.register_blueprint(main_bp)
```

### Using Blueprints for Modular Applications

Blueprints allow you to create modular applications by grouping routes, templates, and static files. For example, you can have a blueprint for the authentication module, another for the admin module, and so on.

---

## OAuth2

### What is OAuth2?

OAuth2 is an authorization framework that enables third-party applications to access a user’s data without exposing the user’s credentials. It provides a secure way for users to grant access to their data without sharing their username and password.

### OAuth2 Authorization Code Flow

The OAuth2 Authorization Code Flow is the most commonly used flow. It involves the following steps:

1. The client directs the user to the authorization server's authorization endpoint.
2. The user logs in and authorizes the client.
3. The authorization server redirects the user back to the client with an authorization code.
4. The client exchanges the authorization code for an access token at the authorization server's token endpoint.
5. The client uses the access token to access the user's data from the resource server.

### Implementing OAuth2 in FastAPI

FastAPI has built-in support for OAuth2. You can implement OAuth2 using the `OAuth2PasswordBearer` class.

```python
from fastapi import FastAPI, Depends, HTTPException
from fastapi.security import OAuth2PasswordBearer

app = FastAPI()

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

@app.get("/users/me")
def read_users_me(token: str = Depends(oauth2_scheme)):
    return {"token": token}
```

### Using OAuth2 in Flask

In Flask, you can use the `authlib` or `flask-oauthlib` library to implement OAuth2.

```python
from flask import Flask, redirect, url_for
from authlib.integrations.flask_client import OAuth

app = Flask(__name__)
app.config['SECRET_KEY'] = 'secret'
oauth = OAuth(app)

github = oauth.register(
    name='github',
    client_id='GITHUB_CLIENT_ID',
    client_secret='GITHUB_CLIENT_SECRET',
    authorize_url='https://github.com/login/oauth/authorize',
    authorize_params=None,
    access_token_url='https://github.com/login/oauth/access_token',
    access_token_params=None,
    client_kwargs={'scope': 'user:email'},
)

@app.route('/login')
def login():
    return github.authorize_redirect(url_for('authorize', _external=True))

@app.route('/authorize')
def authorize():
    token = github.authorize_access_token()
    resp = github.get('user')
    user_info = resp.json()
    return user_info
```

---

## Azure AD Auth

### Introduction to Azure Active Directory (AD)

Azure Active Directory (AD) is Microsoft’s cloud-based identity and access management service. It provides secure access to Azure services, Microsoft 365, and other third-party applications.

### Implementing Azure AD Authentication in FastAPI

To integrate Azure AD authentication in a FastAPI application, you can use libraries like `msal` or `fastapi-azure-auth`. Here’s a basic example using `msal`:

```python
from fastapi import FastAPI, Depends, HTTPException
from msal import ConfidentialClientApplication

app = FastAPI()

app_config = {
    "client_id": "YOUR_CLIENT_ID",
    "authority": "https://login.microsoftonline.com/YOUR_TENANT_ID",
    "client_secret": "YOUR_CLIENT_SECRET",
}

cca = ConfidentialClientApplication(
    app_config["client_id"],
    authority=app_config["authority"],
    client_credential=app_config["client_secret"],
)

def get_access_token():
    # Obtain token
    result = cca.acquire_token_for_client(scopes=["https://graph.microsoft.com/.default"])
    if "access_token" in result:
        return result["access_token"]
    else:
        raise HTTPException(status_code=401, detail="Token acquisition failed")

@app.get("/users/")
def read_users(token: str = Depends(get_access_token)):
    return {"token": token}
```

### Using Azure AD with Flask

To implement Azure AD in Flask, you can use the `msal` library as well:

```python
from flask import Flask, redirect, url_for, session
from msal import ConfidentialClientApplication

app = Flask(__name__)
app.secret_key = 'super_secret_key'

app_config = {
    "client_id": "YOUR_CLIENT_ID",
    "authority": "https://login.microsoftonline.com/YOUR_TENANT_ID",
    "client_secret": "YOUR_CLIENT_SECRET",
}

cca = ConfidentialClientApplication(
    app_config["client_id"],
    authority=app_config["authority"],
    client_credential=app_config["client_secret"],
)

@app.route('/login')
def login():
    token = cca.acquire_token_for_client(scopes=["https://graph.microsoft.com/.default"])
    session["token"] = token["access_token"]
    return redirect(url_for("index"))

@app.route('/')
def index():
    token = session.get("token")
    if not token:
        return redirect(url_for("login"))
    return f"Token: {token}"
```

---

## OpenID

### What is OpenID Connect?

OpenID Connect is an identity layer on top of the OAuth2 protocol. It allows clients to verify the identity of the user and obtain basic profile information.

### OpenID vs OAuth2

- **OAuth2:** Primarily used for authorization. OAuth2 allows third-party applications to access user data without sharing credentials.
- **OpenID Connect:** Built on OAuth2, but focuses on authentication. OpenID Connect verifies user identity and allows for single sign-on (SSO) capabilities.

### Integrating OpenID with FastAPI

FastAPI supports OpenID Connect through its OAuth2 system. You can implement OpenID Connect in a similar way to OAuth2.

```python
from fastapi import FastAPI, Depends
from fastapi.security import OAuth2AuthorizationCodeBearer

app = FastAPI()

oauth2_scheme = OAuth2AuthorizationCodeBearer(
    authorizationUrl="https://your-openid-provider.com/auth",
    tokenUrl="https://your-openid-provider.com/token",
)

@app.get("/users/me")
def read_users_me(token: str = Depends(oauth2_scheme)):
    return {"token": token}
```

### Using OpenID in Flask

You can integrate OpenID Connect in Flask using libraries like `authlib`.

```python
from flask import Flask, redirect, url_for
from authlib.integrations.flask_client import OAuth

app = Flask(__name__)
app.secret_key = 'super_secret_key'

oauth = OAuth(app)
oidc = oauth.register(
    name='oidc',
    client_id='YOUR_CLIENT_ID',
    client_secret='YOUR_CLIENT_SECRET',
    authorize_url='https://your-openid-provider.com/auth',
    authorize_params=None,
    access_token_url='https://your-openid-provider.com/token',
    access_token_params=None,
    client_kwargs={'scope': 'openid profile email'},
)

@app.route('/login')
def login():
    return oidc.authorize_redirect(url_for('authorize', _external=True))

@app.route('/authorize')
def authorize():
    token = oidc.authorize_access_token()
    user_info = oidc.parse_id_token(token)
    return user_info
```

---

## Testing

### Introduction to Testing in Python

Testing is a crucial part of software development that ensures your application behaves as expected. Python provides several tools and frameworks for testing.

### Unit Testing

Unit testing involves testing individual components or functions of your application to ensure they work correctly in isolation. Python’s built-in

 `unittest` module is commonly used for unit testing.

```python
import unittest

def add(a, b):
    return a + b

class TestMathFunctions(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
        self.assertEqual(add(-1, 1), 0)

if __name__ == '__main__':
    unittest.main()
```

### Testing FastAPI with `pytest`

FastAPI integrates seamlessly with `pytest`, a powerful testing framework. You can test FastAPI endpoints using the `TestClient`.

```python
from fastapi import FastAPI
from fastapi.testclient import TestClient

app = FastAPI()

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}

client = TestClient(app)

def test_read_item():
    response = client.get("/items/42?q=test")
    assert response.status_code == 200
    assert response.json() == {"item_id": 42, "q": "test"}
```

### Testing Flask with `pytest`

Flask can also be tested with `pytest`. Flask’s test client can be used to simulate requests to the application.

```python
from flask import Flask

app = Flask(__name__)

@app.route("/items/<int:item_id>")
def read_item(item_id):
    return {"item_id": item_id}

def test_read_item():
    with app.test_client() as client:
        response = client.get("/items/42")
        assert response.status_code == 200
        assert response.json == {"item_id": 42}
```

## Logging

### Introduction to Logging

Logging is the process of recording information about your application's execution. It helps in monitoring and debugging by providing insights into what’s happening in the application at runtime.

### Python's Built-in Logging Module

Python provides a built-in `logging` module that is flexible and easy to use. The basic concept involves creating loggers, handlers, and formatters.

```python
import logging

# Create a logger
logger = logging.getLogger(__name__)
logger.setLevel(logging.DEBUG)

# Create a console handler and set its level to debug
ch = logging.StreamHandler()
ch.setLevel(logging.DEBUG)

# Create a formatter and set it for the handler
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
ch.setFormatter(formatter)

# Add the handler to the logger
logger.addHandler(ch)

# Log some messages
logger.debug('Debug message')
logger.info('Info message')
logger.warning('Warning message')
logger.error('Error message')
logger.critical('Critical message')
```

### Logging in FastAPI

FastAPI integrates well with Python’s `logging` module. You can configure logging at the application level:

```python
import logging
from fastapi import FastAPI

app = FastAPI()

# Configure logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

@app.get("/")
def read_root():
    logger.info("Root endpoint accessed")
    return {"message": "Hello World"}
```

### Logging in Flask

Flask also allows you to configure logging using the `logging` module. You can set up logging in your Flask application as follows:

```python
import logging
from flask import Flask

app = Flask(__name__)

# Configure logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

@app.route("/")
def home():
    logger.info("Home route accessed")
    return "Hello, Flask!"

if __name__ == "__main__":
    app.run()
```

### Logging Levels

Python’s `logging` module supports different logging levels:

- **DEBUG:** Detailed information, typically of interest only when diagnosing problems.
- **INFO:** Confirmation that things are working as expected.
- **WARNING:** An indication that something unexpected happened, but the software is still working as expected.
- **ERROR:** A more serious problem, the software has not been able to perform some function.
- **CRITICAL:** A serious error, indicating that the program itself may be unable to continue running.

### Rotating Logs

For long-running applications, logs can grow large, and it is useful to rotate them to manage disk space. You can use `logging.handlers.RotatingFileHandler` for this purpose:

```python
import logging
from logging.handlers import RotatingFileHandler

# Set up rotating file handler
handler = RotatingFileHandler("app.log", maxBytes=2000, backupCount=5)
handler.setLevel(logging.INFO)

# Configure logging
logging.basicConfig(handlers=[handler], level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("This is a test log message.")
```

---

## Caching

### Introduction to Caching

Caching is a technique used to store frequently accessed data in a temporary storage location (cache) to improve the performance of an application. By caching, you reduce the need to repeatedly retrieve or compute data, thus speeding up the application.

### Using Redis for Caching

Redis is a popular in-memory data structure store used as a cache. It is often used with Flask and FastAPI for caching purposes.

#### Setting Up Redis Cache with Flask

```python
from flask import Flask
import redis

app = Flask(__name__)

# Connect to Redis
cache = redis.Redis(host='localhost', port=6379)

@app.route("/<name>")
def hello(name):
    # Check if the result is in the cache
    if cache.exists(name):
        return cache.get(name).decode('utf-8')
    
    # If not in cache, compute the result
    greeting = f"Hello, {name}!"
    
    # Store the result in the cache
    cache.set(name, greeting)
    
    return greeting
```

#### Setting Up Redis Cache with FastAPI

```python
from fastapi import FastAPI
import redis

app = FastAPI()

# Connect to Redis
cache = redis.Redis(host='localhost', port=6379)

@app.get("/{name}")
def read_item(name: str):
    # Check if the result is in the cache
    if cache.exists(name):
        return {"message": cache.get(name).decode('utf-8')}
    
    # If not in cache, compute the result
    greeting = f"Hello, {name}!"
    
    # Store the result in the cache
    cache.set(name, greeting)
    
    return {"message": greeting}
```

### Using Flask-Caching

`Flask-Caching` is an extension that integrates caching mechanisms into Flask.

```python
from flask import Flask
from flask_caching import Cache

app = Flask(__name__)

# Configure cache
cache = Cache(app, config={'CACHE_TYPE': 'SimpleCache'})

@app.route("/<name>")
@cache.cached(timeout=60)
def hello(name):
    return f"Hello, {name}!"
```

### Using CacheTools in FastAPI

`CacheTools` is a simple caching library that can be used with FastAPI.

```python
from fastapi import FastAPI
from cachetools import cached, TTLCache

app = FastAPI()

# Create a cache with a time-to-live of 60 seconds
cache = TTLCache(maxsize=100, ttl=60)

@cached(cache)
@app.get("/{name}")
def read_item(name: str):
    return {"message": f"Hello, {name}!"}
```

---

## Dependency Injection

### Introduction to Dependency Injection

Dependency Injection (DI) is a design pattern used to manage dependencies in an application. DI allows for greater flexibility and modularity, making it easier to test and maintain your code.

### Dependency Injection in FastAPI

FastAPI has built-in support for dependency injection. You can define dependencies that will be injected into your route handlers.

```python
from fastapi import FastAPI, Depends

app = FastAPI()

def get_db():
    db = {"db": "MyDatabase"}
    try:
        yield db
    finally:
        pass  # Close the database connection here

@app.get("/")
def read_root(db: dict = Depends(get_db)):
    return {"message": f"Connected to {db['db']}"}
```

### Dependency Injection in Flask

Flask doesn't have built-in DI support, but you can implement it using Python's standard capabilities or third-party libraries like `Flask-Injection`.

```python
from flask import Flask, request

app = Flask(__name__)

def inject_user():
    return {"user": "admin"}

@app.before_request
def before_request():
    request.user = inject_user()

@app.route("/")
def home():
    return f"Hello, {request.user['user']}!"
```

---

## WebSockets

### Introduction to WebSockets

WebSockets provide a full-duplex communication channel over a single, long-lived connection. They are ideal for real-time applications like chat applications, live updates, and notifications.

### WebSockets in FastAPI

FastAPI supports WebSockets natively. You can create WebSocket routes to handle real-time communication.

```python
from fastapi import FastAPI, WebSocket

app = FastAPI()

@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    while True:
        data = await websocket.receive_text()
        await websocket.send_text(f"Message text was: {data}")
```

### WebSockets in Flask

To use WebSockets with Flask, you can use the `flask-socketio` extension.

```python
from flask import Flask, render_template
from flask_socketio import SocketIO, send

app = Flask(__name__)
app.config['SECRET_KEY'] = 'secret!'
socketio = SocketIO(app)

@socketio.on('message')
def handle_message(message):
    send(f"Message received: {message}")

if __name__ == "__main__":
    socketio.run(app)
```

---

## Background Tasks

### Background Tasks in FastAPI

FastAPI allows you to define background tasks that can run after returning a response to the client.

```python
from fastapi import FastAPI, BackgroundTasks

app = FastAPI()

def write_log(message: str):
    with open("log.txt", "a") as log_file:
        log_file.write(message + "\n")

@app.post("/send-message/")
def send_message(message: str, background_tasks: BackgroundTasks):
    background_tasks.add_task(write_log, message)
    return {"message": "Message sent"}
```

### Background Jobs in Flask

In Flask, you can handle background tasks using Celery, a distributed task queue.

```python
from flask import Flask
from celery import Celery

app = Flask(__name__)

# Configure Celery
app.config['CELERY_BROKER_URL'] = 'redis://localhost:6379/0'
app.config['CELERY_RESULT_BACKEND'] = 'redis://localhost:6379/0'
celery = Celery(app.name, broker=app.config['CELERY_BROKER_URL'])
celery.conf.update(app.config)

@celery.task
def background_task(message):
    with open("log.txt", "a") as log_file:
        log_file.write(message + "\n")

@app.route("/send-message/<message>")
def send_message(message):
    background_task.delay(message)
    return {"message": "Message sent"}
```


