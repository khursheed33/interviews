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

---

# Answers ---------------------------------------


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


