# 90-Day Backend Engineering Roadmap

## Core Assumptions

- **Starting Knowledge:** Basic Python syntax (variables, loops, functions, lists, dictionaries)
- **Daily Commitment:** 120 minutes (2 hours) consistently
- **Internet:** Limited bandwidth — prioritize text docs over HD videos
- **Tools Required:** VS Code, Git, Python 3.11+, PostgreSQL (local or Docker)
- **End Goal:** Portfolio-ready backend engineer with 3 production-grade projects

---

## 13-Week Overview

| Week | Theme | Milestone |
|------|-------|-----------|
| 1-2 | Python 3 & OOP Foundations | CLI Task Manager |
| 3-4 | FastAPI Fundamentals | CRUD API with PostgreSQL |
| 5-6 | Database Layer & ORM | Multi-entity Relational API |
| 7-8 | Modular Architecture | Auth-Protected Modular App |
| 9 | Event-Driven Design | Redis Message Queue System |
| 10-11 | LLM API Integration | AI Chatbot Backend |
| 12-13 | Deployment & Capstone | Production AI Service |


## WEEK 1-2: Python 3 & OOP Foundations

**Weekly Objective:** Master modern Python syntax, type hints, OOP principles, and build a CLI task manager that uses classes, file persistence, and exception handling. By Week 2, you'll have a working project demonstrating object-oriented design.

---

### **Day 1: Python 3 Modern Syntax & Virtual Environments**

**Prerequisites:** Basic Python knowledge (variables, loops, functions)

**Where to Learn:**
1. [Python 3.11 Official Tutorial](https://docs.python.org/3/tutorial/) — Sections 1-4
2. [Real Python: Virtual Environments](https://realpython.com/python-virtual-environments-a-primer/)
3. [freeCodeCamp: Python for Beginners](https://www.youtube.com/watch?v=rfscVS0vtbw) — First 60 minutes

**120-Minute Breakdown:**
- 0-30m: Read Python 3.11 syntax differences (match/case, improved error messages, type hints)
- 30-50m: Set up virtual environment (`python -m venv venv`), activate it, install packages
- 50-90m: Practice: Create a project folder, initialize venv, install `requests` and `rich` libraries
- 90-110m: Write a script that uses f-strings, type hints (`def greet(name: str) -> str`), and walrus operator
- 110-120m: Document setup steps in README.md

**Daily Exercise:**
Create `backend_journey/day01/` folder. Write `setup_check.py` that:
1. Prints Python version
2. Imports `requests` and `rich`
3. Uses type hints for a function that calculates factorial
4. Saves output to `output.txt` using file handling

**Deliverable:**
- GitHub repo initialized with `.gitignore` (Python template)
- `day01/setup_check.py` with type hints
- `README.md` documenting your setup

**Why It Matters:**
Every backend job expects virtual environments, type hints (for code clarity), and modern Python syntax. Recruiters check for clean project structure immediately.

**If Behind:**
Watch [Corey Schafer's Python Virtual Environments](https://www.youtube.com/watch?v=Kg1Yvry_Ydk) (10 minutes), then just complete the script without advanced features.

---

### **Day 2: Modules, Packages & Project Structure**

**Prerequisites:** Day 1 complete

**Where to Learn:**
1. [Python Modules Documentation](https://docs.python.org/3/tutorial/modules.html)
2. [Real Python: Python Modules and Packages](https://realpython.com/python-modules-packages/)
3. [ArjanCodes: Python Project Structure](https://www.youtube.com/watch?v=QA0uHX-7Zmo)

**120-Minute Breakdown:**
- 0-25m: Read about `__init__.py`, relative imports, and package structure
- 25-50m: Watch ArjanCodes video on project organization
- 50-90m: Create a multi-module calculator project (`utils/math_ops.py`, `utils/string_ops.py`, `main.py`)
- 90-110m: Practice importing across modules, use `if __name__ == "__main__":`
- 110-120m: Write docstrings for each module

**Daily Exercise:**
In `day02/calculator/`:
1. Create `utils/` package with `math_ops.py` (add, subtract, multiply) and `validators.py` (check numeric input)
2. Create `main.py` that imports from `utils` and performs calculations
3. Add `__init__.py` to make `utils` a proper package

**Deliverable:**
- `day02/calculator/` with proper package structure
- All modules documented with docstrings
- `main.py` demonstrates cross-module imports

**Why It Matters:**
Backend codebases have hundreds of files. Understanding imports and package structure separates amateurs from professionals.

**If Behind:**
Skip the video. Just create two Python files and import one into the other using `from file1 import function`.

---

### **Day 3: Classes & Objects Fundamentals**

**Prerequisites:** Day 1-2 complete

**Where to Learn:**
1. [Python Classes Tutorial](https://docs.python.org/3/tutorial/classes.html)
2. [Real Python: OOP in Python](https://realpython.com/python3-object-oriented-programming/)
3. [Corey Schafer: OOP Playlist](https://www.youtube.com/watch?v=ZDa-Z5JzLYM) — First video

**120-Minute Breakdown:**
- 0-35m: Read about classes, `__init__`, instance variables, methods
- 35-60m: Watch Corey Schafer's OOP intro
- 60-100m: Build a `BankAccount` class with deposit, withdraw, check_balance methods
- 100-115m: Create multiple instances and test operations
- 115-120m: Push to GitHub

**Daily Exercise:**
Create `day03/bank_system.py`:
1. `BankAccount` class with `__init__(self, owner: str, balance: float)`
2. Methods: `deposit(amount)`, `withdraw(amount)`, `get_balance()`
3. Add validation (can't withdraw more than balance)
4. Create 3 account instances and demonstrate operations

**Deliverable:**
- `bank_system.py` with complete class implementation
- Test output showing deposits/withdrawals
- Git commit with message "Day 3: Bank Account OOP"

**Why It Matters:**
Backend systems model real-world entities as classes — users, products, orders. OOP is fundamental to every framework including FastAPI and Django.

**If Behind:**
Just create a simple `Person` class with name and age. Add a method that prints a greeting.

---

### **Day 4: Inheritance & Composition**

**Prerequisites:** Day 3 complete

**Where to Learn:**
1. [Python Inheritance Docs](https://docs.python.org/3/tutorial/classes.html#inheritance)
2. [Real Python: Inheritance and Composition](https://realpython.com/inheritance-composition-python/)
3. [ArjanCodes: Composition vs Inheritance](https://www.youtube.com/watch?v=0mcP8ZpUR38)

**120-Minute Breakdown:**
- 0-30m: Read about inheritance (`class Child(Parent)`), `super()`, method overriding
- 30-55m: Learn composition (has-a vs is-a relationships)
- 55-95m: Extend Day 3's `BankAccount` to create `SavingsAccount` and `CheckingAccount` subclasses
- 95-115m: Add composition example (Account "has-a" Transaction history)
- 115-120m: Document design decisions

**Daily Exercise:**
Enhance `day04/bank_system_v2.py`:
1. `SavingsAccount(BankAccount)` with interest calculation
2. `CheckingAccount(BankAccount)` with overdraft limit
3. `TransactionHistory` class (composition) that stores all transactions
4. Demonstrate inheritance and composition working together

**Deliverable:**
- Extended bank system with inheritance hierarchy
- Composition example with transaction tracking
- Comments explaining when to use each pattern

**Why It Matters:**
Real APIs have layered models (BaseUser → Admin, Customer). Understanding inheritance prevents code duplication in production.

**If Behind:**
Just create one subclass (e.g., `PremiumAccount`) that adds a single new method.

---

### **Day 5: Dataclasses & Type Hints**

**Prerequisites:** Day 1-4 complete

**Where to Learn:**
1. [Python Dataclasses Documentation](https://docs.python.org/3/library/dataclasses.html)
2. [Real Python: Python Data Classes](https://realpython.com/python-data-classes/)
3. [mCoding: Python Type Hints](https://www.youtube.com/watch?v=QORvB-_mbZ0)

**120-Minute Breakdown:**
- 0-25m: Read about `@dataclass` decorator and auto-generated methods
- 25-50m: Learn type hints (`list[str]`, `dict[str, int]`, `Optional[str]`)
- 50-90m: Rewrite Day 4's classes using dataclasses
- 90-110m: Add type hints to all functions and methods
- 110-120m: Run `mypy` static type checker (install via pip)

**Daily Exercise:**
Create `day05/typed_models.py`:
1. Convert `BankAccount` to a dataclass with type hints
2. Add `Transaction` dataclass with fields: `id`, `amount`, `type`, `timestamp`
3. Create `AccountManager` with typed methods: `create_account(owner: str) -> BankAccount`
4. Validate with `mypy typed_models.py`

**Deliverable:**
- All classes converted to dataclasses
- Complete type annotations
- `mypy` passing without errors

**Why It Matters:**
Pydantic (FastAPI's validation library) is built on dataclasses and type hints. Modern Python backends require strong typing for API contracts.

**If Behind:**
Just add `@dataclass` to one class and type hints to two functions.

---

### **Day 6: Exception Handling & Logging**

**Prerequisites:** Day 1-5 complete

**Where to Learn:**
1. [Python Exceptions Documentation](https://docs.python.org/3/tutorial/errors.html)
2. [Real Python: Python Exceptions](https://realpython.com/python-exceptions/)
3. [Real Python: Logging in Python](https://realpython.com/python-logging/)

**120-Minute Breakdown:**
- 0-30m: Read about try/except/finally, custom exceptions, exception hierarchy
- 30-55m: Learn logging module (DEBUG, INFO, WARNING, ERROR, CRITICAL)
- 55-95m: Add exception handling to bank system (InsufficientFundsError, InvalidAmountError)
- 95-115m: Replace print statements with logging
- 115-120m: Configure logging to file

**Daily Exercise:**
Enhance `day06/bank_with_errors.py`:
1. Create custom exceptions: `InsufficientFundsError`, `NegativeAmountError`
2. Wrap withdraw/deposit in try/except blocks
3. Add logging for all operations (INFO for success, ERROR for failures)
4. Configure logger to write to `bank.log`

**Deliverable:**
- Exception-safe bank system
- Logging to both console and file
- Demonstrate error handling with test cases

**Why It Matters:**
Production backends never crash silently. Exception handling and logging are mandatory for debugging live systems.

**If Behind:**
Just add one try/except block around withdraw and one logger.info() statement.

---

### **Day 7: File Handling & JSON Persistence**

**Prerequisites:** Day 1-6 complete

**Where to Learn:**
1. [Python File I/O Documentation](https://docs.python.org/3/tutorial/inputoutput.html)
2. [Real Python: Reading and Writing Files](https://realpython.com/read-write-files-python/)
3. [Real Python: Working with JSON](https://realpython.com/python-json/)

**120-Minute Breakdown:**
- 0-25m: Read about context managers (`with open()`), file modes (r, w, a)
- 25-50m: Learn JSON serialization/deserialization
- 50-90m: Add save/load functionality to bank system using JSON
- 90-110m: Handle file not found and JSON decode errors
- 110-120m: Test persistence across program runs

**Daily Exercise:**
Create `day07/persistent_bank.py`:
1. Add `save_to_file(filename: str)` method that serializes accounts to JSON
2. Add `load_from_file(filename: str)` class method that recreates accounts
3. Modify dataclasses to be JSON-serializable (convert datetime to string)
4. Demonstrate saving, closing program, and loading data back

**Deliverable:**
- Bank system with JSON persistence
- Error handling for file operations
- Test showing data survives program restart

**Why It Matters:**
Before databases, file-based storage is essential. Understanding serialization prepares you for API request/response handling.

**If Behind:**
Just write one function that saves a dictionary to JSON and another that reads it back.

---

### **Day 8-9: CLI Task Manager Project (Part 1)**

**Prerequisites:** Week 1 complete

**Where to Learn:**
1. [Click Documentation](https://click.palletsprojects.com/) — CLI framework
2. [Real Python: Building CLI Applications](https://realpython.com/command-line-interfaces-python-argparse/)
3. Review Days 1-7 concepts

**120-Minute Breakdown (Each Day):**
- Day 8: 0-30m: Design task manager (tasks have id, title, status, created_at)
- Day 8: 30-90m: Build Task dataclass, TaskManager class with add/list/complete methods
- Day 8: 90-120m: Implement JSON persistence
- Day 9: 0-60m: Add CLI using `argparse` or `click` (commands: add, list, complete, delete)
- Day 9: 60-110m: Add filtering (show only pending/completed), sorting by date
- Day 9: 110-120m: Polish error messages and logging

**Daily Exercise:**
Build `day08-09/task_manager/`:
1. `models.py`: Task dataclass with proper types
2. `manager.py`: TaskManager class with CRUD operations
3. `storage.py`: JSON save/load with error handling
4. `cli.py`: Command-line interface
5. `main.py`: Entry point

**Deliverable:**
- Fully functional CLI task manager
- Commands: `python main.py add "task name"`, `list`, `complete 1`, `delete 2`
- All data persists to `tasks.json`
- Comprehensive README with usage examples

**Why It Matters:**
This project combines all Week 1 concepts. CLI tools are common in DevOps and backend tooling. Shows you can build end-to-end features.

**If Behind:**
Build simpler version without CLI — just functions called directly in `main.py`.

---

### **Day 10-11: Advanced OOP Patterns**

**Prerequisites:** Days 1-9 complete

**Where to Learn:**
1. [Python Magic Methods](https://rszalski.github.io/magicmethods/)
2. [Real Python: Operator Overloading](https://realpython.com/operator-function-overloading/)
3. [ArjanCodes: Design Patterns Playlist](https://www.youtube.com/watch?v=tDxRdc8r3iY) — Strategy Pattern

**120-Minute Breakdown (Each Day):**
- Day 10: 0-40m: Learn `__str__`, `__repr__`, `__eq__`, `__lt__` (comparison operators)
- Day 10: 40-90m: Implement magic methods for Task class (sorting, equality)
- Day 10: 90-120m: Add `__len__` and `__getitem__` to TaskManager (make it iterable)
- Day 11: 0-50m: Learn Strategy pattern (different task sorting strategies)
- Day 11: 50-100m: Implement SortByDate, SortByPriority strategies
- Day 11: 100-120m: Refactor TaskManager to use strategy pattern

**Daily Exercise:**
Enhance `day10-11/task_manager_v2/`:
1. Add magic methods to Task for rich comparison and string representation
2. Make TaskManager support `for task in manager` iteration
3. Create sorting strategies: `DateSorter`, `PrioritySorter` (add priority field to Task)
4. TaskManager accepts sorter in constructor

**Deliverable:**
- Task class with all comparison operators
- Iterable TaskManager
- Pluggable sorting strategies
- Demo showing different sort orders

**Why It Matters:**
Magic methods make your classes feel like built-in Python types. Design patterns like Strategy are used in FastAPI dependency injection and middleware.

**If Behind:**
Just implement `__str__` and `__repr__` for Task. Skip the Strategy pattern.

---

### **Day 12-14: Week 2 Integration & Polish**

**Prerequisites:** Days 1-11 complete

**120-Minute Breakdown (Each Day):**
- Day 12: Add priority levels (HIGH, MEDIUM, LOW) using Enum
- Day 12: Implement filtering by priority and status
- Day 12: Add tags/categories to tasks
- Day 13: Create `export_to_csv()` function
- Day 13: Add task statistics (total, completed percentage, overdue)
- Day 13: Improve CLI with colored output (use `rich` library)
- Day 14: Write comprehensive README
- Day 14: Clean up code, add docstrings everywhere
- Day 14: Create demo video/GIF for portfolio

**Daily Exercise:**
Final polish `day12-14/task_manager_final/`:
1. Add Enum for priority, categories
2. Implement export functionality
3. Add statistics dashboard command
4. Rich formatting for terminal output
5. Complete documentation

**Deliverable:**
- Production-quality task manager
- Professional README with screenshots
- All code documented
- GitHub release (v1.0.0)

**Weekly Deliverables Checklist (Week 1-2):**
- ✅ Virtual environment setup documented
- ✅ Multi-module package structure
- ✅ OOP principles demonstrated (inheritance, composition, dataclasses)
- ✅ Exception handling and logging throughout
- ✅ JSON persistence implemented
- ✅ CLI application with multiple commands
- ✅ Design patterns applied (Strategy)
- ✅ Professional GitHub repository with README

**Why It Matters:**
This project goes on your portfolio. It shows OOP mastery, clean code, and ability to build complete features — exactly what entry-level jobs require.

**If Behind:**
Focus on core features only (add, list, complete). Skip export and statistics.

---

# WEEK 3-4: FastAPI Fundamentals

**Weekly Objective:** Master REST API development with FastAPI, including routing, request/response models with Pydantic 2.0, dependency injection, async programming, and OpenAPI documentation. Build a complete CRUD API with PostgreSQL integration.

---

### **Day 15: HTTP Basics & FastAPI Setup**

**Prerequisites:** Python OOP knowledge from Weeks 1-2

**Where to Learn:**
1. [FastAPI Official Tutorial](https://fastapi.tiangolo.com/tutorial/) — First Steps
2. [HTTP Methods Explained](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
3. [freeCodeCamp: APIs for Beginners](https://www.youtube.com/watch?v=GZvSYJDk-us) — First 30 minutes

**120-Minute Breakdown:**
- 0-30m: Learn HTTP methods (GET, POST, PUT, DELETE), status codes (200, 201, 404, 500)
- 30-55m: Install FastAPI and Uvicorn (`pip install fastapi uvicorn[standard]`)
- 55-95m: Create first FastAPI app with basic routes
- 95-115m: Test with browser and Postman
- 115-120m: Explore auto-generated docs at `/docs`

**Daily Exercise:**
Create `day15/first_api/`:
1. `main.py` with FastAPI instance
2. Routes: `GET /` (hello world), `GET /items/{item_id}` (path parameter), `GET /search` (query parameter)
3. Run with `uvicorn main:app --reload`
4. Test all routes in Postman, screenshot `/docs` page

**Deliverable:**
- Working FastAPI server
- 3+ routes demonstrating path and query parameters
- Screenshots of interactive docs
- Git commit "Day 15: First FastAPI app"

**Why It Matters:**
FastAPI is the fastest-growing Python web framework (2025). Its auto-generated OpenAPI docs and type safety make it preferred for backend roles.

**If Behind:**
Just create one GET route that returns `{"message": "Hello"}`. Test in browser.

---

### **Day 16: Pydantic 2.0 Models**

**Prerequisites:** Day 15 complete

**Where to Learn:**
1. [Pydantic 2.0 Documentation](https://docs.pydantic.dev/latest/)
2. [FastAPI: Request Body](https://fastapi.tiangolo.com/tutorial/body/)
3. [Pydantic Models Video](https://www.youtube.com/watch?v=XIdQ6gO3Anc) — ArjanCodes

**120-Minute Breakdown:**
- 0-35m: Learn Pydantic BaseModel, Field validators, type coercion
- 35-60m: Understand request/response models separation
- 60-100m: Build User model with validation (email format, password length)
- 100-115m: Create POST routes that accept Pydantic models
- 115-120m: Test validation errors in Postman

**Daily Exercise:**
Create `day16/user_api/`:
1. `models.py`: `UserCreate` (email, password, age), `UserResponse` (exclude password)
2. `main.py`: `POST /users` endpoint accepting `UserCreate`, returns `UserResponse`
3. Add Field validators (email regex, age > 0, password min 8 chars)
4. Test valid and invalid inputs

**Deliverable:**
- Pydantic models with validation rules
- POST endpoint with request/response model separation
- Documentation showing validation errors

**Why It Matters:**
Pydantic provides automatic data validation and serialization. Every production API uses request/response models to enforce contracts and prevent bad data.

**If Behind:**
Create one simple model with 2 fields (name, age). Skip complex validators.

---

### **Day 17: CRUD Operations (In-Memory)**

**Prerequisites:** Days 15-16 complete

**Where to Learn:**
1. [FastAPI CRUD Tutorial](https://fastapi.tiangolo.com/tutorial/body-updates/)
2. [REST API Best Practices](https://stackoverflow.blog/2020/03/02/best-practices-for-rest-api-design/)
3. Review HTTP methods from Day 15

**120-Minute Breakdown:**
- 0-25m: Plan CRUD endpoints (POST /users, GET /users, GET /users/{id}, PUT /users/{id}, DELETE /users/{id})
- 25-70m: Implement all CRUD operations storing users in list
- 70-105m: Add proper HTTP status codes (201 for create, 404 for not found)
- 105-115m: Handle edge cases (duplicate email, delete non-existent user)
- 115-120m: Test complete workflow in Postman

**Daily Exercise:**
Build `day17/crud_api/`:
1. In-memory storage (Python list)
2. POST /users → create user with auto-generated ID
3. GET /users → return all users
4. GET /users/{id} → return single user or 404
5. PUT /users/{id} → update user
6. DELETE /users/{id} → remove user
7. Handle errors with `HTTPException`

**Deliverable:**
- Complete CRUD API
- Proper status codes everywhere
- Error handling for all edge cases
- Postman collection with all requests

**Why It Matters:**
CRUD is 80% of backend work. Mastering REST conventions makes you immediately productive in any API project.

**If Behind:**
Just implement POST and GET all. Skip update and delete.

---

### **Day 18: Async Programming Basics**

**Prerequisites:** Days 15-17 complete

**Where to Learn:**
1. [Python Asyncio Documentation](https://docs.python.org/3/library/asyncio.html)
2. [Real Python: Async IO in Python](https://realpython.com/async-io-python/)
3. [FastAPI: Async Concurrency](https://fastapi.tiangolo.com/async/)

**120-Minute Breakdown:**
- 0-35m: Learn `async`/`await`, event loop, coroutines vs threads
- 35-60m: Understand when to use async (I/O-bound operations)
- 60-95m: Convert Day 17 routes to async functions
- 95-115m: Add simulated async operation (sleep, external API call)
- 115-120m: Compare performance with sync version

**Daily Exercise:**
Create `day18/async_api/`:
1. Convert all route functions to `async def`
2. Add `GET /slow` endpoint with `await asyncio.sleep(2)` simulating database call
3. Add `GET /external` that uses `httpx` (async HTTP client) to fetch data from JSONPlaceholder
4. Demonstrate concurrent requests (multiple `/slow` calls complete faster together)

**Deliverable:**
- Fully async FastAPI application
- Demo showing async benefits (concurrent request handling)
- Notes on when to use sync vs async

**Why It Matters:**
Modern backends handle thousands of concurrent connections. Async programming is essential for database queries, API calls, and real-time features.

**If Behind:**
Just convert one route to `async def`. Skip the external API call.

---

### **Day 19: Dependency Injection**

**Prerequisites:** Days 15-18 complete

**Where to Learn:**
1. [FastAPI Dependencies](https://fastapi.tiangolo.com/tutorial/dependencies/)
2. [ArjanCodes: Dependency Injection](https://www.youtube.com/watch?v=2ejbLVkCndI)
3. [FastAPI Advanced Dependencies](https://fastapi.tiangolo.com/advanced/advanced-dependencies/)

**120-Minute Breakdown:**
- 0-30m: Learn Depends() function, dependency hierarchy
- 30-55m: Understand separation of concerns (route logic vs business logic)
- 55-90m: Create reusable dependencies (get_current_user, pagination params)
- 90-115m: Implement pagination with `skip` and `limit` parameters
- 115-120m: Refactor Day 17 CRUD using dependencies

**Daily Exercise:**
Enhance `day19/di_api/`:
1. Create `dependencies.py` with `get_pagination()` returning `skip` and `limit`
2. Create `get_user_by_id()` dependency that validates user exists
3. Modify GET /users to use pagination dependency
4. Modify PUT/DELETE /users/{id} to use user validation dependency
5. Demonstrate dependency reuse across routes

**Deliverable:**
- Dependency functions separated from routes
- Pagination implemented via DI
- Validation logic extracted to dependencies
- Cleaner route handlers

**Why It Matters:**
Dependency injection is FastAPI's superpower. It enables testable code, shared logic, and is the foundation for database sessions and authentication.

**If Behind:**
Just create one dependency function for pagination. Use it in one route.

---

### **Day 20: Background Tasks & Middleware**

**Prerequisites:** Days 15-19 complete

**Where to Learn:**
1. [FastAPI Background Tasks](https://fastapi.tiangolo.com/tutorial/background-tasks/)
2. [FastAPI Middleware](https://fastapi.tiangolo.com/tutorial/middleware/)
3. [Real Python: Python Logging](https://realpython.com/python-logging/) — Review

**120-Minute Breakdown:**
- 0-30m: Learn BackgroundTasks for async operations (emails, logging)
- 30-60m: Understand middleware for cross-cutting concerns (logging, timing)
- 60-95m: Implement email simulation as background task
- 95-115m: Create request timing middleware
- 115-120m: Add logging middleware

**Daily Exercise:**
Build `day20/background_api/`:
1. POST /users endpoint triggers background task (simulate email with `asyncio.sleep`)
2. Add middleware that logs request method, path, and duration
3. Add middleware that adds custom header to all responses
4. Demonstrate background task doesn't block response

**Deliverable:**
- Background tasks implementation
- 2 custom middleware functions
- Logs showing request timing
- Proof that background tasks are non-blocking

**Why It Matters:**
Production APIs send emails, process images, and log analytics without slowing responses. Middleware handles auth, CORS, and monitoring in real systems.

**If Behind:**
Just implement one background task (simple logging). Skip middleware.

---

### **Day 21: PostgreSQL Setup**

**Prerequisites:** Days 15-20 complete

**Where to Learn:**
1. [PostgreSQL Official Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
2. [PostgreSQL Installation Guide](https://www.postgresql.org/download/)
3. [W3Schools SQL Tutorial](https://www.w3schools.com/sql/) — Sections 1-5

**120-Minute Breakdown:**
- 0-40m: Install PostgreSQL locally or via Docker (`docker run postgres`)
- 40-65m: Learn basic SQL (CREATE TABLE, INSERT, SELECT, WHERE, JOIN)
- 65-95m: Use psql or pgAdmin to create database, tables
- 95-115m: Practice CRUD operations in raw SQL
- 115-120m: Document connection details

**Daily Exercise:**
Setup `day21/postgres_practice/`:
1. Install PostgreSQL and create database `fastapi_db`
2. Create `users` table (id, email, name, created_at)
3. Write SQL file with CREATE TABLE, INSERT 5 users, SELECT queries
4. Execute queries manually and save results
5. Document connection string (`postgresql://user:pass@localhost/fastapi_db`)

**Deliverable:**
- Running PostgreSQL instance
- Database and table created
- SQL script with sample data
- Connection details documented

**Why It Matters:**
PostgreSQL is the most popular open-source database. Understanding SQL before ORMs makes you a better backend engineer.

**If Behind:**
Use Docker to avoid installation issues: `docker run -e POSTGRES_PASSWORD=password -p 5432:5432 postgres`. Just create one table.

---

### **Day 22: SQLAlchemy ORM Basics**

**Prerequisites:** Day 21 complete

**Where to Learn:**
1. [SQLAlchemy 2.0 Documentation](https://docs.sqlalchemy.org/en/20/tutorial/)
2. [FastAPI with SQLAlchemy](https://fastapi.tiangolo.com/tutorial/sql-databases/)
3. [Pretty Printed: SQLAlchemy Tutorial](https://www.youtube.com/watch?v=woKYyhLCcnU)

**120-Minute Breakdown:**
- 0-35m: Install SQLAlchemy and psycopg2 (`pip install sqlalchemy psycopg2-binary`)
- 35-60m: Learn ORM concepts (models, sessions, queries)
- 60-100m: Create User model, engine, session
- 100-115m: Perform CRUD via ORM (no raw SQL)
- 115-120m: Compare with Day 21's raw SQL

**Daily Exercise:**
Create `day22/sqlalchemy_basics/`:
1. `database.py`: engine, SessionLocal, Base setup
2. `models.py`: User model with SQLAlchemy (id, email, name, created_at)
3. `crud.py`: functions to create, read, update, delete users
4. `main.py`: test script demonstrating all CRUD operations
5. Alembic not needed yet — use `Base.metadata.create_all()`

**Deliverable:**
- SQLAlchemy models defined
- CRUD operations via ORM
- Database populated with test data
- Comparison notes: ORM vs raw SQL

**Why It Matters:**
ORMs abstract SQL complexity and provide type safety. SQLAlchemy is industry standard for Python backends — FastAPI, Flask, and Django use it.

**If Behind:**
Just create the User model and one function to insert a user.

---

### **Day 23: FastAPI + SQLAlchemy Integration**

**Prerequisites:** Days 21-22 complete

**Where to Learn:**
1. [FastAPI SQL Databases Tutorial](https://fastapi.tiangolo.com/tutorial/sql-databases/)
2. [SQLAlchemy Sessions](https://docs.sqlalchemy.org/en/20/orm/session_basics.html)
3. Review Day 19 (Dependency Injection)

**120-Minute Breakdown:**
- 0-30m: Learn database session management in FastAPI
- 30-60m: Create `get_db()` dependency for session handling
- 60-100m: Integrate Day 22's CRUD with FastAPI routes
- 100-115m: Add proper error handling (user not found, duplicate email)
- 115-120m: Test all endpoints with real database

**Daily Exercise:**
Build `day23/fastapi_sqlalchemy/`:
1. Copy Day 22's database setup
2. Create `dependencies.py` with `get_db()` session dependency
3. Update routes to use `db: Session = Depends(get_db)`
4. POST /users → insert to database
5. GET /users → query all from database
6. GET /users/{id} → query single user
7. PUT /users/{id} → update in database
8. DELETE /users/{id} → delete from database

**Deliverable:**
- FastAPI routes connected to PostgreSQL
- Session management via dependency injection
- All CRUD operations persisting to database
- Postman collection updated for real database

**Why It Matters:**
This is the foundation of every production API. Session management prevents database connection leaks — a critical production skill.

**If Behind:**
Just implement POST and GET routes with database. Skip update/delete.

---

### **Day 24: Relationships & Joins**

**Prerequisites:** Days 21-23 complete

**Where to Learn:**
1. [SQLAlchemy Relationships](https://docs.sqlalchemy.org/en/20/orm/basic_relationships.html)
2. [FastAPI Advanced SQL Tutorial](https://fastapi.tiangolo.com/advanced/sql-databases/)
3. [SQL Joins Explained](https://www.w3schools.com/sql/sql_join.asp)

**120-Minute Breakdown:**
- 0-35m: Learn one-to-many relationships (User has many Posts)
- 35-60m: Understand foreign keys, relationship(), backref
- 60-100m: Add Post model related to User
- 100-115m: Create endpoints to create posts and fetch user with posts
- 115-120m: Test nested data retrieval

**Daily Exercise:**
Enhance `day24/relationships_api/`:
1. Add `Post` model (id, title, content, user_id, created_at)
2. Define relationship: `User.posts = relationship("Post", back_populates="owner")`
3. POST /posts → create post for user
4. GET /users/{id}/posts → get user with all posts (eager loading)
5. Demonstrate join query with `selectinload()`

**Deliverable:**
- Related models (User, Post)
- Foreign key constraint
- Nested data retrieval working
- Demo showing user with multiple posts

**Why It Matters:**
Real applications have complex relationships (users, orders, products). Understanding ORMs relationships prevents N+1 query problems in production.

**If Behind:**
Just add the Post model with foreign key. Create one post. Skip the nested retrieval.

---

### **Day 25-26: Complete CRUD API Project**

**Prerequisites:** Days 15-24 complete

**Where to Learn:**
- Review all Week 3-4 materials
- [FastAPI Best Practices](https://github.com/zhanymkanov/fastapi-best-practices)
- [REST API Naming Conventions](https://restfulapi.net/resource-naming/)

**120-Minute Breakdown (Each Day):**
- Day 25: 0-60m: Design complete API (Users, Posts, Comments)
- Day 25: 60-120m: Implement all models and relationships
- Day 26: 0-90m: Implement all CRUD endpoints with proper error handling
- Day 26: 90-120m: Add filtering, sorting, pagination to GET endpoints

**Daily Exercise:**
Build `day25-26/blog_api/`:
```text
Structure:
blog_api/
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── database.py
│   ├── models/
│   │   ├── __init__.py
│   │   ├── user.py
│   │   ├── post.py
│   │   └── comment.py
│   ├── schemas/
│   │   ├── __init__.py
│   │   ├── user.py
│   │   ├── post.py
│   │   └── comment.py
│   ├── crud/
│   │   ├── __init__.py
│   │   ├── user.py
│   │   ├── post.py
│   │   └── comment.py
│   ├── routers/
│   │   ├── __init__.py
│   │   ├── users.py
│   │   ├── posts.py
│   │   └── comments.py
│   └── dependencies.py
├── requirements.txt
└── README.md
```

Features:
1. Users CRUD
2. Posts CRUD (belongs to user)
3. Comments CRUD (belongs to post)
4. GET /posts?limit=10&skip=0&sort=created_at
5. GET /users/{id}/posts (all posts by user)
6. GET /posts/{id}/comments (all comments on post)

**Deliverable:**
- Production-quality folder structure
- 3 related models with proper relationships
- All CRUD endpoints for each resource
- Pagination, filtering, sorting
- Complete Postman collection
- Professional README with API documentation

**Weekly Deliverables Checklist (Week 3-4):**
- ✅ FastAPI basics mastered (routing, request/response)
- ✅ Pydantic 2.0 models with validation
- ✅ Async programming implemented
- ✅ Dependency injection throughout
- ✅ PostgreSQL + SQLAlchemy integrated
- ✅ Relationships and joins working
- ✅ Complete CRUD API with 3 entities
- ✅ Professional API documentation

**Why It Matters:**
This project demonstrates API design skills required for 90% of backend positions. Clean structure and proper relationships show you understand production patterns.

**If Behind:**
Just implement Users and Posts. Skip Comments. Minimal endpoints (POST, GET).

---

### **Day 27-28: Polish & Documentation**

**Prerequisites:** Days 25-26 complete

**120-Minute Breakdown (Each Day):**
- Day 27: Add comprehensive docstrings to all functions
- Day 27: Improve OpenAPI docs with descriptions, examples
- Day 27: Add response models for error cases
- Day 28: Create detailed README with endpoint documentation
- Day 28: Add environment variable configuration
- Day 28: Create demo data seeding script

**Daily Exercise:**
Polish `day27-28/blog_api_final/`:
1. Add docstrings with parameter descriptions
2. Use `response_model` and `response_description` in decorators
3. Add examples to Pydantic models (`Config.json_schema_extra`)
4. Create `.env.example` file
5. Write `seed_data.py` to populate database
6. Professional README with curl examples

**Deliverable:**
- Fully documented codebase
- Rich OpenAPI documentation
- Environment configuration setup
- Seeding script for testing
- Portfolio-ready README

**Why It Matters:**
Documentation quality separates junior from mid-level developers. Good docs show professionalism and make collaboration easier.

**If Behind:**
Just write a basic README with setup instructions.

---

# 🗓️ WEEK 5-6: Database Layer & ORM Mastery

**Weekly Objective:** Master advanced SQLAlchemy patterns including migrations (Alembic), complex queries, transactions, the repository pattern, and async database operations. Build a multi-entity relational API with proper architectural layers.

---

### **Day 29: Alembic Database Migrations**

**Prerequisites:** Weeks 3-4 complete

**Where to Learn:**
1. [Alembic Documentation](https://alembic.sqlalchemy.org/en/latest/tutorial.html)
2. [FastAPI with Alembic](https://testdriven.io/blog/fastapi-sqlalchemy/)
3. [Database Migrations Explained](https://www.youtube.com/watch?v=YJibNSI_npI)

**120-Minute Breakdown:**
- 0-30m: Understand migrations concept (version control for database schema)
- 30-55m: Install Alembic, initialize in project
- 55-90m: Create initial migration from existing models
- 90-115m: Practice schema changes (add column, modify column, add index)
- 115-120m: Apply and rollback migrations

**Daily Exercise:**
Setup `day29/migrations_practice/`:
1. Initialize Alembic: `alembic init alembic`
2. Configure `alembic.ini` and `env.py` to use SQLAlchemy models
3. Generate migration: `alembic revision --autogenerate -m "Initial"`
4. Apply: `alembic upgrade head`
5. Add `bio` field to User model
6. Generate new migration, apply it
7. Test rollback: `alembic downgrade -1`

**Deliverable:**
- Alembic configured in project
- Migration files for schema changes
- Documentation on migration workflow
- Commands cheat sheet

**Why It Matters:**
Production databases require safe schema evolution. Alembic migrations enable zero-downtime deployments and team collaboration on schema changes.

**If Behind:**
Just initialize Alembic and create one migration. Don't worry about rollback.

---

### **Day 30: Complex Queries & Filtering**

**Prerequisites:** Day 29 complete

**Where to Learn:**
1. [SQLAlchemy Querying Guide](https://docs.sqlalchemy.org/en/20/orm/queryguide/)
2. [Advanced SQLAlchemy Queries](https://www.youtube.com/watch?v=51RpDZKShiw)
3. [SQL WHERE Clause](https://www.w3schools.com/sql/sql_where.asp)

**120-Minute Breakdown:**
- 0-30m: Learn filter(), filter_by(), and complex conditions (AND, OR)
- 30-60m: Understand order_by(), limit(), offset()
- 60-95m: Implement search functionality (ILIKE for case-insensitive)
- 95-115m: Add date range filtering
- 115-120m: Optimize with indexes

**Daily Exercise:**
Enhance `day30/advanced_queries/`:
1. GET /posts?search=python (searches title and content)
2. GET /posts?author=john&sort=created_at&order=desc
3. GET /posts?from_date=2025-01-01&to_date=2025-12-31
4. GET /posts?tags=python,fastapi (if you add tags)
5. Add database indexes on frequently filtered columns

**Deliverable:**
- Advanced filtering endpoints
- Search functionality working
- Date range queries implemented
- Database indexes added via migration

**Why It Matters:**
Real APIs need powerful search and filtering. LinkedIn, Twitter, e-commerce — all use complex queries. Understanding query optimization prevents slow endpoints.

**If Behind:**
Just implement simple search on one field (e.g., title contains keyword).

---

### **Day 31: Transactions & Data Integrity**

**Prerequisites:** Days 29-30 complete

**Where to Learn:**
1. [SQLAlchemy Transactions](https://docs.sqlalchemy.org/en/20/orm/session_transaction.html)
2. [Database Transactions Explained](https://www.postgresql.org/docs/current/tutorial-transactions.html)
3. [ACID Properties](https://en.wikipedia.org/wiki/ACID)

**120-Minute Breakdown:**
- 0-30m: Learn ACID properties and transaction isolation
- 30-55m: Understand session.commit(), session.rollback()
- 55-95m: Implement multi-step operation with transaction
- 95-115m: Handle transaction failures and rollbacks
- 115-120m: Add unique constraints and handle integrity errors

**Daily Exercise:**
Build `day31/transactions_demo/`:
1. Create transfer operation: deduct from one user, add to another
2. Wrap in transaction — if second step fails, rollback first
3. Add unique constraint on User.email
4. Handle IntegrityError when duplicate email
5. Demonstrate transaction rollback on error

**Deliverable:**
- Multi-step transactional operations
- Proper error handling with rollback
- Database constraints enforced
- Demo showing atomicity (all-or-nothing)

**Why It Matters:**
Financial apps, inventory systems, bookings — all require transactions. Understanding atomicity prevents data corruption in production.

**If Behind:**
Just demonstrate one commit() and one rollback(). Skip the complex multi-step operation.

---

### **Day 32: Repository Pattern**

**Prerequisites:** Days 29-31 complete

**Where to Learn:**
1. [Repository Pattern Explained](https://www.cosmicpython.com/book/chapter_02_repository.html)
2. [ArjanCodes: Repository Pattern](https://www.youtube.com/watch?v=MhKPgbYC2Gg)
3. Review Week 1-2 OOP principles

**120-Minute Breakdown:**
- 0-35m: Understand separation of concerns (data access vs business logic)
- 35-60m: Learn repository pattern structure
- 60-100m: Create UserRepository class with CRUD methods
- 100-115m: Refactor routes to use repository instead of direct CRUD
- 115-120m: Compare old vs new structure

**Daily Exercise:**
Refactor `day32/repository_pattern/`:
1. Create `repositories/` folder
2. `base_repository.py`: Generic base class with common methods
3. `user_repository.py`: UserRepository(BaseRepository) with user-specific queries
4. Move all database logic from `crud/` to repositories
5. Update routers to use `user_repo.get_all()` instead of direct queries
6. Routes should only have: validation → repository call → response

**Deliverable:**
- Repository classes implemented
- Clear separation: routes → repositories → database
- Business logic isolated from data access
- Cleaner, testable code structure

**Why It Matters:**
Repository pattern makes code testable and maintainable. It's standard in enterprise applications and improves code quality dramatically.

**If Behind:**
Just create one repository class with get_all() and get_by_id(). Use it in one route.

---

### **Day 33: Service Layer Pattern**

**Prerequisites:** Day 32 complete

**Where to Learn:**
1. [Service Layer Pattern](https://www.cosmicpython.com/book/chapter_04_service_layer.html)
2. [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
3. Review Day 19 (Dependency Injection)

**120-Minute Breakdown:**
- 0-30m: Understand service layer (business logic orchestration)
- 30-60m: Learn difference between repository (data) and service (logic)
- 60-100m: Create UserService with business operations
- 100-115m: Add validation and business rules to service
- 115-120m: Update routes to use services

**Daily Exercise:**
Add `day33/service_layer/`:
1. Create `services/` folder
2. `user_service.py`: UserService class
3. Methods like `create_user_with_validation()`, `deactivate_user()`, `get_user_with_posts()`
4. Business rules: check email uniqueness, validate age, auto-generate username
5. Routes become thin: request → service → response
6. Services use repositories for data access

**Deliverable:**
- Service layer implemented
- Business logic extracted from routes
- Clear architecture: routes → services → repositories → database
- Comprehensive comments explaining layers

**Why It Matters:**
Service layer is where complex business logic lives. This three-layer architecture (controller-service-repository) is industry standard for scalable APIs.

**If Behind:**
Just create one service class with one method that uses the repository.

---

### **Day 34: Async SQLAlchemy**

**Prerequisites:** Days 29-33 complete

**Where to Learn:**
1. [SQLAlchemy Async Documentation](https://docs.sqlalchemy.org/en/20/orm/extensions/asyncio.html)
2. [FastAPI Async SQL](https://fastapi.tiangolo.com/advanced/async-sql-databases/)
3. Review Day 18 (Async Programming)

**120-Minute Breakdown:**
- 0-35m: Learn async database engine and session
- 35-60m: Convert models to async (AsyncSession)
- 60-100m: Update repositories to use async methods
- 100-115m: Convert all routes to async database calls
- 115-120m: Test performance improvement

**Daily Exercise:**
Convert `day34/async_database/`:
1. Install `asyncpg`: `pip install asyncpg`
2. Update `database.py` to use `create_async_engine`
3. Change session to `AsyncSession`
4. Update repositories: `async def get_all()`, use `await session.execute()`
5. Update all routes to `async def` with `await`
6. Test concurrent requests

**Deliverable:**
- Fully async database layer
- All repositories async
- Performance comparison with sync version
- Notes on when async provides benefits

**Why It Matters:**
Async database operations allow handling thousands of concurrent users. Required for high-traffic applications and real-time features.

**If Behind:**
Just convert one repository method to async. Keep the rest synchronous.

---

### **Day 35: Many-to-Many Relationships**

**Prerequisites:** Days 29-34 complete

**Where to Learn:**
1. [SQLAlchemy Many-to-Many](https://docs.sqlalchemy.org/en/20/orm/basic_relationships.html#many-to-many)
2. [Association Tables](https://docs.sqlalchemy.org/en/20/orm/basic_relationships.html#association-object)
3. [SQL Many-to-Many Tutorial](https://www.databasestar.com/many-to-many-relationships/)

**120-Minute Breakdown:**
- 0-30m: Understand many-to-many relationships (students ↔ courses)
- 30-60m: Learn association tables and secondary parameter
- 60-95m: Implement Post ↔ Tag relationship
- 95-115m: Create endpoints to manage tags
- 115-120m: Query posts by tags

**Daily Exercise:**
Add to `day35/many_to_many/`:
1. Create `Tag` model (id, name)
2. Create association table `post_tags`
3. Add relationship: `Post.tags = relationship("Tag", secondary=post_tags, back_populates="posts")`
4. POST /tags → create tag
5. POST /posts/{id}/tags → add tag to post
6. GET /tags/{id}/posts → get all posts with tag
7. Alembic migration for new tables

**Deliverable:**
- Many-to-many relationship implemented
- Association table created
- CRUD operations for managing relationships
- Demo showing posts with multiple tags

**Why It Matters:**
E-commerce (products ↔ categories), social media (users ↔ groups), education (students ↔ courses) — all use many-to-many. Critical for complex data models.

**If Behind:**
Just create the models and association table. Skip the endpoints.

---

### **Day 36-38: E-Commerce API Project (Part 1)**

**Prerequisites:** Days 29-35 complete

**Where to Learn:**
- Review all Week 5-6 materials
- [E-Commerce Database Design](https://vertabelo.com/blog/designing-a-database-for-an-online-shop/)

**120-Minute Breakdown (3 Days):**
- Day 36: Design schema (Users, Products, Categories, Orders, OrderItems)
- Day 36: Create all models with relationships
- Day 37: Implement repositories for all entities
- Day 37: Implement service layer with business logic
- Day 38: Create all CRUD endpoints
- Day 38: Add product filtering and search

**Daily Exercise:**
Build `day36-38/ecommerce_api/`:

**Models:**
1. User (id, email, name, role: customer/admin)
2. Category (id, name, description)
3. Product (id, name, price, stock, category_id) — many categories via association
4. Order (id, user_id, total, status, created_at)
5. OrderItem (id, order_id, product_id, quantity, price)

**Relationships:**
- User → Orders (one-to-many)
- Product → Categories (many-to-many)
- Order → OrderItems (one-to-many)
- Product → OrderItems (one-to-many)

**Features:**
- Products CRUD with category assignment
- Search products by name, filter by category, price range
- Create order (reduces product stock)
- Get user's order history
- Admin endpoints (protected by role)

**Deliverable:**
- Complete e-commerce data model
- All relationships properly defined
- Repository and service layers
- CRUD endpoints for all entities
- Order creation with stock validation
- Alembic migrations

**Why It Matters:**
E-commerce APIs demonstrate complex business logic, transactions, and relationships — exactly what interviewers ask about. Perfect portfolio piece.

**If Behind:**
Just implement Users, Products, and Orders. Skip Categories and OrderItems.

---

### **Day 39-42: E-Commerce API Project (Part 2)**

**Prerequisites:** Days 36-38 complete

**120-Minute Breakdown (4 Days):**
- Day 39: Add inventory management (stock tracking, low stock alerts)
- Day 39: Implement order status workflow (pending → paid → shipped → delivered)
- Day 40: Add product reviews (User reviews Product, rating + comment)
- Day 40: Calculate average product ratings
- Day 41: Implement shopping cart (CartItem model, add/remove/clear)
- Day 41: Cart checkout creates Order
- Day 42: Add advanced queries (top products, user spending, sales reports)
- Day 42: Polish and documentation

**Daily Exercise:**
Enhance `day39-42/ecommerce_api_complete/`:

**New Features:**
1. Stock validation on order (transaction rollback if insufficient)
2. Order status transitions with validation
3. Review system with rating aggregation
4. Cart functionality (session-based or user-based)
5. Analytics endpoints:
   - GET /admin/products/top-selling
   - GET /admin/users/{id}/spending
   - GET /admin/sales/report?from_date&to_date

**Deliverable:**
- Complete e-commerce platform
- Complex business logic with transactions
- Analytics and reporting features
- Professional documentation
- Postman collection with all workflows
- ER diagram of database schema

**Weekly Deliverables Checklist (Week 5-6):**
- ✅ Alembic migrations mastered
- ✅ Complex queries and filtering implemented
- ✅ Transaction handling with ACID properties
- ✅ Repository pattern applied
- ✅ Service layer with business logic
- ✅ Async database operations
- ✅ Many-to-many relationships
- ✅ Complete e-commerce API with 5+ entities

**Why It Matters:**
This project showcases advanced backend skills: complex data models, business logic, transactions, and real-world features. Interviewers will be impressed by this level of complexity.

**If Behind:**
Focus on core e-commerce features: Products, Orders, OrderItems. Skip reviews and cart.

---

# WEEK 7-8: Modular Architecture & Authentication

**Weekly Objective:** Master modular application design, authentication (JWT, OAuth2), authorization (role-based access), and build a production-grade multi-module FastAPI application with secure endpoints.

---

### **Day 43: Monolithic vs Modular Architecture**

**Prerequisites:** Weeks 1-6 complete

**Where to Learn:**
1. [Microservices vs Monolith](https://microservices.io/patterns/monolithic.html)
2. [FastAPI Project Structure](https://fastapi.tiangolo.com/tutorial/bigger-applications/)
3. [ArjanCodes: Software Architecture](https://www.youtube.com/watch?v=DluNeFM4kX0)

**120-Minute Breakdown:**
- 0-35m: Understand monolithic, modular monolith, microservices
- 35-60m: Learn when to use each architecture
- 60-95m: Design modular FastAPI structure
- 95-115m: Refactor previous project into modules
- 115-120m: Document architecture decisions

**Daily Exercise:**
Refactor `day43/modular_structure/`:
```text
app/
├── main.py               # App factory
├── config.py             # Settings
├── database.py           # DB connection
├── dependencies.py       # Global dependencies
├── modules/
│   ├── users/
│   │   ├── __init__.py
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── repository.py
│   │   ├── service.py
│   │   └── router.py
│   ├── products/
│   │   └── (same structure)
│   └── orders/
│       └── (same structure)
└── shared/
    ├── exceptions.py
    ├── utils.py
    └── middleware.py
```

**Deliverable:**
- Modular folder structure
- Each module self-contained
- Shared utilities extracted
- App factory pattern with module registration
- Documentation explaining structure

**Why It Matters:**
Modular design enables team collaboration and independent deployment. Understanding this separates mid-level from senior engineers.

**If Behind:**
Just separate your code into `users/` and `products/` folders. Basic separation is fine.

---

### **Day 44: Configuration Management**

**Prerequisites:** Day 43 complete

**Where to Learn:**
1. [Pydantic Settings](https://docs.pydantic.dev/latest/concepts/pydantic_settings/)
2. [FastAPI Settings](https://fastapi.tiangolo.com/advanced/settings/)
3. [12-Factor App Config](https://12factor.net/config)

**120-Minute Breakdown:**
- 0-25m: Learn environment-based configuration
- 25-50m: Install `pydantic-settings`, create Settings class
- 50-90m: Move all config to environment variables
- 90-115m: Create `.env`, `.env.example`, `.env.test`
- 115-120m: Add config dependency

**Daily Exercise:**
Add to `day44/config_management/`:
1. Install: `pip install pydantic-settings python-dotenv`
2. Create `config.py`:
```python
# Empty code structure placeholder
class Settings(BaseSettings):
    # DATABASE_URL, SECRET_KEY, DEBUG, etc.
    model_config = SettingsConfigDict(env_file=".env")
```
3. Create `.env.example` (safe to commit)
4. Add `.env` to `.gitignore`
5. Use `settings = Settings()` dependency in routes

**Deliverable:**
- Centralized configuration
- Environment variables for all secrets
- Different configs for dev/test/prod
- Security improved (no hardcoded secrets)

**Why It Matters:**
Production apps run in multiple environments. Configuration management is mandatory for deployment and security.

**If Behind:**
Just create `.env` file with database URL. Use `python-dotenv` to load it.

---

### **Day 45: Password Hashing & Security**

**Prerequisites:** Day 44 complete

**Where to Learn:**
1. [Passlib Documentation](https://passlib.readthedocs.io/)
2. [Password Hashing Best Practices](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
3. [FastAPI Security](https://fastapi.tiangolo.com/tutorial/security/)

**120-Minute Breakdown:**
- 0-30m: Learn password hashing (bcrypt), why never store plaintext
- 30-55m: Install passlib, create password utilities
- 55-90m: Implement user registration with hashed passwords
- 90-115m: Implement login verification
- 115-120m: Test security

**Daily Exercise:**
Build `day45/password_security/`:
1. Install: `pip install passlib[bcrypt]`
2. Create `security.py`:
```python
# Empty code structure placeholder
def hash_password(password: str) -> str:
    # Use bcrypt
    pass

def verify_password(plain: str, hashed: str) -> bool:
    # Verify with bcrypt
    pass
```
3. Update User model: `hashed_password` field
4. POST /register → hash password before saving
5. POST /login → verify password, return success/failure

**Deliverable:**
- Password hashing implemented
- Registration with secure storage
- Login verification working
- Never log or return passwords

**Why It Matters:**
Security breaches destroy companies. Proper password handling is non-negotiable for any production application.

**If Behind:**
Just implement hash_password() and use it during registration.

---

### **Day 46-47: JWT Authentication**

**Prerequisites:** Day 45 complete

**Where to Learn:**
1. [JWT.io Introduction](https://jwt.io/introduction)
2. [FastAPI JWT Tutorial](https://fastapi.tiangolo.com/tutorial/security/oauth2-jwt/)
3. [Python-JOSE Documentation](https://python-jose.readthedocs.io/)

**120-Minute Breakdown (2 Days):**
- Day 46: 0-40m: Learn JWT structure (header.payload.signature)
- Day 46: 40-80m: Install python-jose, create token utilities
- Day 46: 80-120m: Implement token creation on login
- Day 47: 0-60m: Implement token validation dependency
- Day 47: 60-100m: Protect routes with authentication
- Day 47: 100-120m: Add token expiration and refresh

**Daily Exercise:**
Build `day46-47/jwt_auth/`:
1. Install: `pip install python-jose[cryptography]`
2. Create `security.py`:
```python
# Empty code structure placeholder
def create_access_token(data: dict, expires_delta: timedelta) -> str:
    # Create JWT
    pass

def decode_token(token: str) -> dict:
    # Verify and decode JWT
    pass
```
3. POST /login → returns `{"access_token": "...", "token_type": "bearer"}`
4. Create `get_current_user()` dependency that validates token
5. Protect routes: `GET /users/me` requires authentication
6. Handle expired tokens, invalid tokens

**Deliverable:**
- JWT token generation on login
- Token validation dependency
- Protected routes requiring authentication
- Token expiration handling
- Postman collection with Bearer token

**Why It Matters:**
JWT is the industry standard for stateless authentication. Every modern API uses it — mastering JWT is mandatory for backend roles.

**If Behind:**
Just implement token creation and return it on login. Skip validation and protected routes.

---

### **Day 48: OAuth2 Password Flow**

**Prerequisites:** Days 46-47 complete

**Where to Learn:**
1. [FastAPI OAuth2](https://fastapi.tiangolo.com/tutorial/security/simple-oauth2/)
2. [OAuth 2.0 Explained](https://www.oauth.com/oauth2-servers/server-side-apps/)
3. Review FastAPI security documentation

**120-Minute Breakdown:**
- 0-30m: Understand OAuth2 password flow
- 30-60m: Implement OAuth2PasswordBearer scheme
- 60-95m: Create token endpoint following OAuth2 spec
- 95-115m: Update authentication to use OAuth2
- 115-120m: Test with FastAPI's built-in auth UI

**Daily Exercise:**
Enhance `day48/oauth2_flow/`:
1. Use `OAuth2PasswordBearer(tokenUrl="token")`
2. POST /token (not /login) accepting `username` and `password` as form data
3. Return OAuth2-compliant response
4. Update all protected routes to use OAuth2 scheme
5. Test authentication in `/docs` interactive UI

**Deliverable:**
- OAuth2-compliant authentication
- Interactive docs with "Authorize" button working
- All protected endpoints using OAuth2 scheme
- Demo video showing authentication flow in Swagger UI

**Why It Matters:**
OAuth2 is the standard for API authentication. Following the spec ensures compatibility with API gateways, mobile apps, and third-party integrations.

**If Behind:**
Just rename your /login endpoint to /token and make it accept form data instead of JSON.

---

### **Day 49: Role-Based Access Control (RBAC)**

**Prerequisites:** Day 48 complete

**Where to Learn:**
1. [RBAC Explained](https://auth0.com/docs/manage-users/access-control/rbac)
2. [FastAPI Advanced Dependencies](https://fastapi.tiangolo.com/advanced/advanced-dependencies/)
3. [Authorization Best Practices](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html)

**120-Minute Breakdown:**
- 0-30m: Learn roles vs permissions, RBAC principles
- 30-60m: Add role field to User model (admin, user, moderator)
- 60-95m: Create role-checking dependencies
- 95-115m: Protect admin routes with role validation
- 115-120m: Test different user roles

**Daily Exercise:**
Build `day49/rbac/`:
1. Add `role: str` to User model with Enum (admin, user)
2. Update registration to set default role
3. Create dependencies:
```python
# Empty code structure placeholder
def require_role(required_role: str):
    def role_checker(current_user: User = Depends(get_current_user)):
        if current_user.role != required_role:
            raise HTTPException(403, "Insufficient permissions")
        return current_user
    return role_checker
```
4. Protect admin routes: `dependencies=[Depends(require_role("admin"))]`
5. Test: regular user cannot access admin endpoints

**Deliverable:**
- User roles implemented
- Role-based access control working
- Admin-only endpoints protected
- Proper 403 Forbidden responses
- Test cases for different roles

**Why It Matters:**
Every production app has different user types. RBAC prevents unauthorized access and is fundamental to security architecture.

**If Behind:**
Just add an `is_admin` boolean field and check it in one protected route.

---

### **Day 50: Refresh Tokens**

**Prerequisites:** Days 46-49 complete

**Where to Learn:**
1. [Refresh Tokens Explained](https://auth0.com/blog/refresh-tokens-what-are-they-and-when-to-use-them/)
2. [FastAPI Refresh Token Pattern](https://testdriven.io/blog/fastapi-jwt-auth/)
3. Review JWT documentation

**120-Minute Breakdown:**
- 0-30m: Understand access vs refresh tokens
- 30-60m: Design token storage strategy
- 60-95m: Implement refresh token generation
- 95-115m: Create token refresh endpoint
- 115-120m: Handle token rotation

**Daily Exercise:**
Enhance `day50/refresh_tokens/`:
1. Modify login to return both tokens:
```python
{
    "access_token": "...",
    "refresh_token": "...",
    "token_type": "bearer"
}
```
2. Store refresh tokens in database (RefreshToken model)
3. Create POST /token/refresh accepting refresh token
4. Return new access token
5. Implement token rotation (invalidate old refresh token)
6. Add token revocation endpoint

**Deliverable:**
- Dual token system (access + refresh)
- Token refresh working
- Refresh tokens stored in database
- Token revocation capability
- Security documentation

**Why It Matters:**
Long-lived access tokens are security risks. Refresh tokens enable secure, seamless user sessions — standard in mobile and SPA applications.

**If Behind:**
Just return a longer-lived access token. Skip the refresh token complexity.

---

### **Day 51-52: Permission System**

**Prerequisites:** Days 43-50 complete

**Where to Learn:**
1. [Permission-Based Access Control](https://casbin.org/docs/overview)
2. [FastAPI Advanced Security](https://fastapi.tiangolo.com/advanced/security/)
3. Review RBAC from Day 49

**120-Minute Breakdown (2 Days):**
- Day 51: 0-60m: Design permission system (create:post, delete:user, etc.)
- Day 51: 60-120m: Create Permission and RolePermission models
- Day 52: 0-60m: Implement permission checking dependency
- Day 52: 60-100m: Assign permissions to roles
- Day 52: 100-120m: Test granular permissions

**Daily Exercise:**
Build `day51-52/permissions/`:
1. Models:
   - Permission (id, name, description)
   - RolePermission (role, permission_id) — many-to-many
2. Seed permissions: create:post, edit:post, delete:post, manage:users
3. Assign permissions to roles
4. Create permission checker:
```python
# Empty code structure placeholder
def require_permission(permission: str):
    async def permission_checker(current_user: User = Depends(get_current_user)):
        # Check if user's role has permission
        pass
    return permission_checker
```
5. Protect endpoints with specific permissions

**Deliverable:**
- Granular permission system
- Roles with assigned permissions
- Permission-based route protection
- Admin interface to manage permissions
- Complete authorization flow

**Why It Matters:**
Complex applications need fine-grained access control. Permission systems enable scalable authorization that doesn't require code changes for new rules.

**If Behind:**
Just create a list of permissions as strings and check if user's role has the required permission.

---

### **Day 53-56: Multi-Module Application Project**

**Prerequisites:** Days 43-52 complete

**120-Minute Breakdown (4 Days):**
- Day 53: Set up project structure with 4 modules
- Day 53: Configure shared authentication and database
- Day 54: Implement users module (registration, login, profile)
- Day 54: Implement auth middleware
- Day 55: Implement products module (CRUD with permissions)
- Day 55: Implement orders module (checkout, history)
- Day 56: Implement admin module (user management, reports)
- Day 56: Integration testing and documentation

**Daily Exercise:**
Build `day53-56/modular_ecommerce/`:
```text
app/
├── main.py
├── config.py
├── database.py
├── modules/
│   ├── auth/
│   │   ├── models.py (User, RefreshToken, Permission)
│   │   ├── schemas.py (Login, Register, Token)
│   │   ├── service.py (authentication logic)
│   │   ├── dependencies.py (get_current_user, require_permission)
│   │   └── router.py (register, login, refresh, logout)
│   ├── users/
│   │   ├── models.py (UserProfile)
│   │   ├── service.py (profile management)
│   │   └── router.py (GET/PUT /me, GET /users/{id})
│   ├── products/
│   │   ├── models.py (Product, Category, Review)
│   │   ├── service.py (business logic)
│   │   └── router.py (CRUD with permissions)
│   ├── orders/
│   │   ├── models.py (Order, OrderItem)
│   │   ├── service.py (checkout, stock management)
│   │   └── router.py (create, list, track)
│   └── admin/
│       ├── service.py (user management, analytics)
│       └── router.py (admin-only endpoints)
├── shared/
│   ├── exceptions.py
│   ├── pagination.py
│   └── responses.py
└── tests/ (basic structure)
```

**Features:**
1. **Auth Module:**
   - Registration with email verification flag
   - Login with JWT + refresh token
   - Token refresh and revocation
   - Role and permission management

2. **Users Module:**
   - User profile CRUD
   - Public profile view
   - Profile picture URL field
   - User search (admin only)

3. **Products Module:**
   - CRUD with category support
   - Search and filtering
   - Review system
   - Stock tracking

4. **Orders Module:**
   - Cart to order conversion
   - Stock validation with transactions
   - Order history
   - Status tracking

5. **Admin Module:**
   - User management (ban, role changes)
   - Sales analytics
   - System monitoring endpoints

**Deliverable:**
- Complete modular application
- All modules independently functional
- Shared authentication across modules
- RBAC with permissions
- Professional API documentation
- Postman collection organized by modules
- ER diagram showing all relationships

**Weekly Deliverables Checklist (Week 7-8):**
- ✅ Modular architecture implemented
- ✅ Environment-based configuration
- ✅ Secure password hashing
- ✅ JWT authentication with refresh tokens
- ✅ OAuth2 compliance
- ✅ Role-based access control
- ✅ Granular permission system
- ✅ Production-ready multi-module application

**Why It Matters:**
This architecture mirrors real production applications. Modular design + authentication + authorization demonstrates senior-level backend engineering skills.

**If Behind:**
Focus on Auth and Users modules with basic RBAC. Products and Orders can be simplified (no reviews, basic order creation).

---

# WEEK 9: Event-Driven Architecture

**Weekly Objective:** Understand event-driven design patterns, implement message queues with Redis/RabbitMQ, build producer-consumer systems, and learn when event-driven architecture provides value over synchronous communication.

---

### **Day 57: Event-Driven Architecture Concepts**

**Prerequisites:** Weeks 1-8 complete

**Where to Learn:**
1. [Event-Driven Architecture Explained](https://aws.amazon.com/event-driven-architecture/)
2. [Message Queue Patterns](https://www.cloudamqp.com/blog/part1-rabbitmq-for-beginners-what-is-rabbitmq.html)
3. [ArjanCodes: Event-Driven Design](https://www.youtube.com/watch?v=rJHTK2TfZ1I)

**120-Minute Breakdown:**
- 0-35m: Learn events, producers, consumers, message brokers
- 35-60m: Understand pub/sub vs queue patterns
- 60-90m: Compare synchronous vs asynchronous processing
- 90-110m: Identify use cases (notifications, analytics, background jobs)
- 110-120m: Design event system for e-commerce

**Daily Exercise:**
Plan `day57/event_design/`:
1. Document event types for e-commerce:
   - UserRegistered
   - OrderCreated
   - OrderPaid
   - ProductReviewed
   - StockLow
2. Design event flow diagrams
3. List which events need immediate processing vs background
4. Compare solutions: Redis vs RabbitMQ vs Kafka
5. Write architectural decision document

**Deliverable:**
- Event catalog with descriptions
- Flow diagrams showing event propagation
- Use case analysis (when to use events)
- Technology comparison document
- Architecture proposal

**Why It Matters:**
Event-driven architecture enables scalability, loose coupling, and real-time features. Understanding when to use it separates good engineers from great ones.

**If Behind:**
Just list 5 events that could happen in your application and what should happen when they occur.

---

### **Day 58: Redis Setup & Basics**

**Prerequisites:** Day 57 complete

**Where to Learn:**
1. [Redis Official Tutorial](https://redis.io/docs/getting-started/)
2. [Redis Python Client](https://redis-py.readthedocs.io/)
3. [Redis Pub/Sub](https://redis.io/docs/manual/pubsub/)

**120-Minute Breakdown:**
- 0-30m: Install Redis (Docker: `docker run -p 6379:6379 redis`)
- 30-60m: Learn basic Redis commands (SET, GET, LPUSH, RPUSH, PUBLISH)
- 60-95m: Install redis-py, connect from Python
- 95-115m: Implement basic queue operations
- 115-120m: Test Redis persistence

**Daily Exercise:**
Setup `day58/redis_basics/`:
1. Install: `pip install redis`
2. Create `redis_client.py`:
```python
# Empty code structure placeholder
class RedisClient:
    def __init__(self, url: str):
        self.client = redis.from_url(url)
    
    def publish_event(self, channel: str, data: dict):
        pass
    
    def push_to_queue(self, queue: str, data: dict):
        pass
```
3. Test publishing messages
4. Test queue operations (push/pop)
5. Monitor with `redis-cli`

**Deliverable:**
- Redis running locally/Docker
- Python client connection working
- Basic pub/sub demonstrated
- Queue operations tested
- Redis commands cheat sheet

**Why It Matters:**
Redis is the most popular in-memory data store. Used for caching, sessions, queues, and real-time features in production.

**If Behind:**
Just install Redis and connect to it from Python. Run one SET and GET command.

---

### **Day 59: Producer-Consumer Pattern**

**Prerequisites:** Day 58 complete

**Where to Learn:**
1. [Producer-Consumer Pattern](https://en.wikipedia.org/wiki/Producer%E2%80%93consumer_problem)
2. [Python Threading with Queues](https://docs.python.org/3/library/queue.html)
3. Review async programming from Day 18

**120-Minute Breakdown:**
- 0-30m: Understand producer-consumer problem
- 30-60m: Learn task queue pattern
- 60-95m: Build email notification queue system
- 95-115m: Implement worker process to consume tasks
- 115-120m: Test with multiple workers

**Daily Exercise:**
Build `day59/task_queue/`:
1. Create `producer.py`:
   - FastAPI endpoint POST /send-email
   - Pushes task to Redis queue
   - Returns immediately (non-blocking)
2. Create `consumer.py`:
   - Standalone script polling Redis queue
   - Processes tasks (simulated email sending)
   - Runs indefinitely
3. Create `tasks.py` with task definitions
4. Test: API adds tasks, worker processes them
5. Run multiple workers to demonstrate parallelism

**Deliverable:**
- Producer API adding tasks to queue
- Consumer worker processing tasks
- Demonstrate async processing (API responds instantly)
- Multiple workers handling tasks concurrently
- Logs showing task flow

**Why It Matters:**
Background jobs (emails, reports, image processing) must not block API responses. Task queues are fundamental to scalable systems.

**If Behind:**
Just create the producer that pushes to Redis. Consumer can be a simple script that pops and prints.

---

### **Day 60: Event Publishing in FastAPI**

**Prerequisites:** Day 59 complete

**Where to Learn:**
1. Review FastAPI Background Tasks (Day 20)
2. [Redis Pub/Sub Pattern](https://redis.io/docs/manual/pubsub/)
3. [Event-Driven Microservices](https://microservices.io/patterns/data/event-driven-architecture.html)

**120-Minute Breakdown:**
- 0-30m: Design event schema with Pydantic
- 30-60m: Create event publisher service
- 60-95m: Integrate events into existing endpoints
- 95-115m: Publish events on user actions (register, order created)
- 115-120m: Log all events for visibility

**Daily Exercise:**
Enhance `day60/event_publisher/`:
1. Create `events/schemas.py`:
```python
# Empty code structure placeholder
class UserRegisteredEvent(BaseModel):
    event_type: str = "user.registered"
    user_id: int
    email: str
    timestamp: datetime

class OrderCreatedEvent(BaseModel):
    event_type: str = "order.created"
    order_id: int
    user_id: int
    total: float
    timestamp: datetime
```
2. Create `events/publisher.py` with publish() method
3. Update registration endpoint to publish UserRegisteredEvent
4. Update order creation to publish OrderCreatedEvent
5. Add event logging

**Deliverable:**
- Typed event schemas with Pydantic
- Event publisher service
- Events published on key actions
- Event logs for debugging
- Non-blocking event publishing

**Why It Matters:**
Events decouple services. When Order is created, multiple systems (notifications, analytics, inventory) can react independently without tight coupling.

**If Behind:**
Just publish one event type (e.g., user registration) to Redis. Log when it's published.

---

### **Day 61: Event Subscribers**

**Prerequisites:** Day 60 complete

**Where to Learn:**
1. [Redis Pub/Sub with Python](https://redis-py.readthedocs.io/en/stable/examples/pubsub_examples.html)
2. [Event Handler Pattern](https://refactoring.guru/design-patterns/observer)
3. Review Week 1-2 design patterns

**120-Minute Breakdown:**
- 0-30m: Design subscriber/listener pattern
- 30-60m: Create event handler registry
- 60-95m: Implement specific handlers (SendWelcomeEmail, LogAnalytics)
- 95-115m: Create subscriber service that routes events to handlers
- 115-120m: Test end-to-end flow

**Daily Exercise:**
Build `day61/event_subscribers/`:
1. Create `events/handlers.py`:
```python
# Empty code structure placeholder
class EventHandler(ABC):
    @abstractmethod
    async def handle(self, event: dict):
        pass

class SendWelcomeEmailHandler(EventHandler):
    async def handle(self, event: dict):
        # Simulate email sending
        pass

class LogAnalyticsHandler(EventHandler):
    async def handle(self, event: dict):
        # Log to analytics system
        pass
```
2. Create `events/subscriber.py` that listens to Redis
3. Route events to appropriate handlers based on event_type
4. Run subscriber as separate process
5. Test: publish event → subscriber processes it

**Deliverable:**
- Event handler pattern implemented
- Multiple handlers for different event types
- Subscriber routing events correctly
- Separate subscriber process running
- Complete event flow working

**Why It Matters:**
Subscribers enable reactive systems. When an event occurs, multiple independent systems can respond — the foundation of microservices architecture.

**If Behind:**
Just create one handler that prints received events. Skip the routing complexity.

---

### **Day 62-63: Event-Driven Notification System**

**Prerequisites:** Days 57-61 complete

**120-Minute Breakdown (2 Days):**
- Day 62: 0-60m: Design notification system (email, SMS, push)
- Day 62: 60-120m: Create Notification model and templates
- Day 63: 0-60m: Implement notification handlers for each event type
- Day 63: 60-100m: Add notification preferences for users
- Day 63: 100-120m: Test complete notification flow

**Daily Exercise:**
Build `day62-63/notification_system/`:

**Models:**
1. Notification (id, user_id, type, title, message, read, created_at)
2. NotificationPreference (user_id, email_enabled, sms_enabled)

**Event Handlers:**
1. UserRegisteredHandler → Send welcome email, create notification
2. OrderCreatedHandler → Send order confirmation, create notification
3. StockLowHandler → Notify admin
4. OrderShippedHandler → Notify customer

**Features:**
- Template system for notifications
- User preferences (opt-in/opt-out)
- In-app notification storage
- GET /notifications (user's notifications)
- PATCH /notifications/{id}/read (mark as read)
- Background workers processing notification events

**Deliverable:**
- Complete notification system
- Event-driven notification delivery
- User notification preferences
- In-app notification history
- Multiple notification channels (email simulation, in-app)
- Demo showing event → notification flow

**Why It Matters:**
Every production app needs notifications. Event-driven design ensures notifications don't slow down core operations and can be scaled independently.

**If Behind:**
Just create in-app notifications (stored in database). Skip email simulation and preferences.

---

# WEEK 10-11: LLM API Integration

**Weekly Objective:** Master integration of Large Language Models (Gemini, OpenAI, open-source) into FastAPI backends, implement secure API key management, handle streaming responses, build rate limiting, and create production-ready AI-powered endpoints.

---

### **Day 64: LLM APIs Overview & Setup**

**Prerequisites:** Weeks 1-9 complete

**Where to Learn:**
1. [Google Gemini API Documentation](https://ai.google.dev/docs)
2. [OpenAI API Documentation](https://platform.openai.com/docs/introduction)
3. [LLM API Comparison 2025](https://artificialanalysis.ai/)

**120-Minute Breakdown:**
- 0-30m: Compare LLM providers (Gemini, OpenAI, Anthropic, open-source)
- 30-60m: Create accounts and get API keys (Gemini free tier, OpenAI trial)
- 60-90m: Test APIs with curl/Postman
- 90-115m: Understand pricing, rate limits, token usage
- 115-120m: Document API capabilities and limitations

**Daily Exercise:**
Setup `day64/llm_setup/`:
1. Create Google AI Studio account, get Gemini API key
2. Create OpenAI account, get API key (if available in 2025 free tier)
3. Test Gemini API:
```bash
curl -X POST "https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key=YOUR_KEY" \
  -H 'Content-Type: application/json' \
  -d '{"contents":[{"parts":[{"text":"Explain quantum computing"}]}]}'
```
4. Document response structure
5. Calculate token costs
6. Store keys in `.env`

**Deliverable:**
- API keys obtained and secured
- Test requests documented
- Response formats understood
- Pricing comparison chart
- Rate limit documentation

**Why It Matters:**
LLM integration is the hottest skill in 2025. Backends that leverage AI are in massive demand — this capability significantly increases your market value.

**If Behind:**
Just get one API key (Gemini) and make one successful API call.

---

### **Day 65: Gemini API Integration**

**Prerequisites:** Day 64 complete

**Where to Learn:**
1. [Google Generative AI Python SDK](https://github.com/google/generative-ai-python)
2. [Gemini API Quickstart](https://ai.google.dev/tutorials/python_quickstart)
3. Review async programming (Day 18)

**120-Minute Breakdown:**
- 0-25m: Install `google-generativeai` library
- 25-55m: Create Gemini client service
- 55-90m: Build FastAPI endpoint for text generation
- 90-115m: Add error handling and validation
- 115-120m: Test with various prompts

**Daily Exercise:**
Build `day65/gemini_integration/`:
1. Install: `pip install google-generativeai`
2. Create `services/gemini_service.py`:
```python
# Empty code structure placeholder
import google.generativeai as genai

class GeminiService:
    def __init__(self, api_key: str):
        genai.configure(api_key=api_key)
        self.model = genai.GenerativeModel('gemini-pro')
    
    async def generate_text(self, prompt: str) -> str:
        # Generate content
        pass
```
3. Create endpoint POST /ai/generate
4. Accept prompt, return AI response
5. Handle API errors gracefully

**Deliverable:**
- Gemini SDK integrated
- Text generation endpoint working
- Error handling for API failures
- Request/response logging
- Postman collection with examples

**Why It Matters:**
Gemini offers generous free tier and powerful capabilities. Integrating it shows you can work with cutting-edge AI APIs.

**If Behind:**
Just make one synchronous call to Gemini API without FastAPI integration.

---

### **Day 66: OpenAI API Integration**

**Prerequisites:** Day 65 complete

**Where to Learn:**
1. [OpenAI Python Library](https://github.com/openai/openai-python)
2. [OpenAI API Reference](https://platform.openai.com/docs/api-reference)
3. [Chat Completions Guide](https://platform.openai.com/docs/guides/chat)

**120-Minute Breakdown:**
- 0-25m: Install OpenAI library
- 25-55m: Create OpenAI client service
- 55-90m: Implement chat completion endpoint
- 90-115m: Add conversation history support
- 115-120m: Compare with Gemini responses

**Daily Exercise:**
Build `day66/openai_integration/`:
1. Install: `pip install openai`
2. Create `services/openai_service.py`:
```python
# Empty code structure placeholder
from openai import AsyncOpenAI

class OpenAIService:
    def __init__(self, api_key: str):
        self.client = AsyncOpenAI(api_key=api_key)
    
    async def chat_completion(self, messages: list) -> str:
        # Call chat API
        pass
```
3. Create POST /ai/chat endpoint
4. Accept message history, return AI response
5. Handle rate limits and errors

**Deliverable:**
- OpenAI SDK integrated
- Chat completion endpoint
- Conversation context management
- Error handling with retries
- Cost tracking implementation

**Why It Matters:**
OpenAI's GPT models are industry-leading. Many companies use OpenAI — showing proficiency makes you immediately valuable.

**If Behind:**
If OpenAI API is unavailable/expensive, skip this day and focus on Gemini. Document the limitation.

---

### **Day 67: Streaming Responses**

**Prerequisites:** Days 65-66 complete

**Where to Learn:**
1. [FastAPI Streaming Response](https://fastapi.tiangolo.com/advanced/custom-response/#streamingresponse)
2. [Server-Sent Events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events)
3. [Async Generators in Python](https://peps.python.org/pep-0525/)

**120-Minute Breakdown:**
- 0-30m: Learn streaming vs batch responses
- 30-60m: Understand async generators
- 60-95m: Implement streaming for Gemini
- 95-115m: Create SSE endpoint for real-time updates
- 115-120m: Test with streaming client

**Daily Exercise:**
Build `day67/streaming_ai/`:
1. Update Gemini service with streaming:
```python
# Empty code structure placeholder
async def generate_text_stream(self, prompt: str):
    response = self.model.generate_content(prompt, stream=True)
    for chunk in response:
        yield chunk.text
```
2. Create GET /ai/stream endpoint:
```python
# Empty code structure placeholder
@router.get("/stream")
async def stream_response(prompt: str):
    return StreamingResponse(
        gemini_service.generate_text_stream(prompt),
        media_type="text/event-stream"
    )
```
3. Test with curl or JavaScript EventSource
4. Add proper error handling in stream

**Deliverable:**
- Streaming responses working
- SSE endpoint for real-time AI output
- Client test code (JavaScript/curl)
- Performance comparison (streaming vs batch)
- Demo video showing incremental response

**Why It Matters:**
Streaming provides better UX for AI applications (like ChatGPT's typing effect). Shows understanding of advanced HTTP patterns.

**If Behind:**
Just return the complete response at once. Skip streaming complexity.

---

### **Day 68: Rate Limiting & Cost Control**

**Prerequisites:** Days 64-67 complete

**Where to Learn:**
1. [FastAPI Rate Limiting](https://slowapi.readthedocs.io/)
2. [Token Usage Tracking](https://platform.openai.com/docs/guides/rate-limits)
3. Review Redis (Day 58)

**120-Minute Breakdown:**
- 0-30m: Install slowapi for rate limiting
- 30-60m: Implement per-user rate limits
- 60-90m: Track token usage per user
- 90-115m: Add cost calculation and budget limits
- 115-120m: Create usage dashboard

**Daily Exercise:**
Build `day68/rate_limiting/`:
1. Install: `pip install slowapi`
2. Add rate limiter:
```python
# Empty code structure placeholder
from slowapi import Limiter
from slowapi.util import get_remote_address

limiter = Limiter(key_func=get_remote_address)

@router.post("/generate")
@limiter.limit("5/minute")
async def generate(request: Request, prompt: str):
    pass
```
3. Create TokenUsage model (user_id, tokens_used, cost, timestamp)
4. Track usage on each AI call
5. GET /ai/usage endpoint showing user's consumption
6. Block users exceeding budget

**Deliverable:**
- Rate limiting on AI endpoints
- Token usage tracking
- Cost calculation per request
- User usage dashboard
- Budget enforcement

**Why It Matters:**
AI APIs are expensive. Production systems need cost control and abuse prevention. This shows business awareness and production-readiness.

**If Behind:**
Just add basic rate limiting (5 requests per minute). Skip token tracking.

---

### **Day 69-70: AI Chatbot Backend**

**Prerequisites:** Days 64-68 complete

**120-Minute Breakdown (2 Days):**
- Day 69: 0-60m: Design chat system (conversations, messages)
- Day 69: 60-120m: Implement conversation storage
- Day 70: 0-60m: Build chat endpoint with history
- Day 70: 60-100m: Add streaming chat responses
- Day 70: 100-120m: Polish and test

**Daily Exercise:**
Build `day69-70/chatbot_api/`:

**Models:**
1. Conversation (id, user_id, title, created_at, updated_at)
2. Message (id, conversation_id, role: user/assistant, content, tokens, created_at)

**Endpoints:**
1. POST /chat/conversations → create new conversation
2. GET /chat/conversations → list user's conversations
3. GET /chat/conversations/{id}/messages → get chat history
4. POST /chat/conversations/{id}/messages → send message, get AI response
5. GET /chat/conversations/{id}/stream → streaming chat

**Features:**
- Store conversation history
- Send full context to LLM (last N messages)
- Support both Gemini and OpenAI (selectable)
- Track tokens per message
- Implement context window management (trim old messages)
- Add conversation titles (auto-generated from first message)

**Deliverable:**
- Complete chat backend
- Conversation persistence
- Context-aware AI responses
- Streaming chat working
- Token usage tracked
- Professional API documentation

**Why It Matters:**
Chatbots are the most common LLM application. This project demonstrates you can build production AI features — highly marketable skill.

**If Behind:**
Just implement basic chat without streaming. Store conversations but don't worry about context window management.

---

### **Day 71-72: AI-Powered Features**

**Prerequisites:** Days 69-70 complete

**120-Minute Breakdown (2 Days):**
- Day 71: Implement text summarization endpoint
- Day 71: Implement content moderation (toxic language detection)
- Day 72: Implement text classification (sentiment, category)
- Day 72: Implement text generation with templates (emails, articles)

**Daily Exercise:**
Build `day71-72/ai_features/`:

**Endpoints:**
1. POST /ai/summarize
   - Input: long text
   - Output: concise summary
   - Use case: article summarization

2. POST /ai/moderate
   - Input: user content
   - Output: toxicity score, flagged terms
   - Use case: content moderation

3. POST /ai/classify
   - Input: text
   - Output: category, sentiment, confidence
   - Use case: ticket routing, review analysis

4. POST /ai/generate
   - Input: template type (email, blog), parameters
   - Output: generated content
   - Use case: content creation tools

**Implementation:**
- Use prompt engineering for each task
- Add caching for repeated requests (Redis)
- Implement fallback between Gemini/OpenAI
- Add validation and sanitization
- Track success rates

**Deliverable:**
- 4 AI-powered endpoints working
- Prompt engineering documented
- Response caching implemented
- Multi-provider fallback logic
- Example use cases for each feature
- Performance metrics

**Why It Matters:**
These are practical AI applications businesses pay for. Showing diverse AI capabilities demonstrates you can build real revenue-generating features.

**If Behind:**
Just implement summarization. Skip the other features.

---

### **Day 73-74: LLM Integration Polish & Security**

**Prerequisites:** Days 64-72 complete

**120-Minute Breakdown (2 Days):**
- Day 73: 0-60m: Implement prompt injection protection
- Day 73: 60-120m: Add content filtering and safety checks
- Day 74: 0-60m: Optimize prompt design for cost reduction
- Day 74: 60-100m: Add comprehensive error handling
- Day 74: 100-120m: Create AI service documentation

**Daily Exercise:**
Polish `day73-74/llm_security/`:

**Security Measures:**
1. Input validation and sanitization
2. Prompt injection detection:
```python
# Empty code structure placeholder
def detect_prompt_injection(user_input: str) -> bool:
    # Check for common injection patterns
    dangerous_patterns = ["ignore previous", "system:", "forget all"]
    return any(pattern in user_input.lower() for pattern in dangerous_patterns)
```
3. Output filtering (remove sensitive data, PII)
4. Rate limiting per user tier (free vs paid)
5. API key rotation strategy

**Optimization:**
1. Reduce token usage with better prompts
2. Cache common queries
3. Use cheaper models for simple tasks
4. Implement request batching
5. Add response quality monitoring

**Documentation:**
1. API usage guide
2. Best practices for prompts
3. Cost optimization guide
4. Security considerations
5. Troubleshooting common issues

**Deliverable:**
- Security measures implemented
- Cost-optimized prompting
- Comprehensive error handling
- Professional documentation
- Security audit checklist

**Weekly Deliverables Checklist (Week 10-11):**
- ✅ Gemini API integrated
- ✅ OpenAI API integrated (or documented limitation)
- ✅ Streaming responses working
- ✅ Rate limiting and cost tracking
- ✅ Complete chatbot backend
- ✅ Multiple AI-powered features
- ✅ Security and optimization implemented
- ✅ Production-ready AI service

**Why It Matters:**
AI integration without security and cost control is dangerous. This shows production-level thinking and makes you stand out from developers who only know basic API calls.

**If Behind:**
Focus on basic security (input validation, rate limiting). Skip advanced optimization.

---

# WEEK 12-13: Deployment & Production Capstone

**Weekly Objective:** Master containerization with Docker, deployment to cloud platforms (Render, Railway, Vercel), environment configuration, logging, monitoring, CI/CD basics, and build a complete production-ready AI-powered FastAPI application as your capstone project.

---

### **Day 75: Docker Fundamentals**

**Prerequisites:** All previous weeks complete

**Where to Learn:**
1. [Docker Official Tutorial](https://docs.docker.com/get-started/)
2. [Docker for Python Developers](https://realpython.com/docker-in-action-python/)
3. [FastAPI Docker Deployment](https://fastapi.tiangolo.com/deployment/docker/)

**120-Minute Breakdown:**
- 0-35m: Install Docker Desktop, understand containers vs VMs
- 35-60m: Learn Dockerfile syntax and best practices
- 60-95m: Create Dockerfile for FastAPI application
- 95-115m: Build and run container locally
- 115-120m: Test containerized application

**Daily Exercise:**
Create `day75/docker_basics/`:

1. Create `Dockerfile`:
```dockerfile
# Empty code structure placeholder
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
```

2. Create `.dockerignore`:
```
__pycache__
*.pyc
.env
.git
venv/
```

3. Build image: `docker build -t my-fastapi-app .`
4. Run container: `docker run -p 8000:8000 my-fastapi-app`
5. Test API endpoints on localhost:8000

**Deliverable:**
- Dockerfile for FastAPI application
- Successfully built Docker image
- Running containerized application
- Documentation for Docker commands
- Container testing checklist

**Why It Matters:**
Docker is industry standard for deployment. Every production system uses containers. This skill is mandatory for backend roles in 2025.

**If Behind:**
Just create a basic Dockerfile and build it. Don't worry about optimization or `.dockerignore`.

---

### **Day 76: Docker Compose for Multi-Container Apps**

**Prerequisites:** Day 75 complete

**Where to Learn:**
1. [Docker Compose Documentation](https://docs.docker.com/compose/)
2. [Compose for Development](https://docs.docker.com/compose/gettingstarted/)
3. Review PostgreSQL and Redis setup

**120-Minute Breakdown:**
- 0-30m: Learn Docker Compose syntax and use cases
- 30-60m: Define services (app, database, redis)
- 60-95m: Configure networking and volumes
- 95-115m: Run complete stack with one command
- 115-120m: Test service communication

**Daily Exercise:**
Create `day76/docker_compose/`:

1. Create `docker-compose.yml`:
```yaml
# Empty code structure placeholder
version: '3.8'

services:
  app:
    build: .
    ports:
      - "8000:8000"
    environment:
      - DATABASE_URL=postgresql://user:pass@db:5432/mydb
      - REDIS_URL=redis://redis:6379
    depends_on:
      - db
      - redis

  db:
    image: postgres:15
    environment:
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=pass
      - POSTGRES_DB=mydb
    volumes:
      - postgres_data:/var/lib/postgresql/data

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  postgres_data:
```

2. Update application to use environment variables
3. Run: `docker-compose up`
4. Test full stack functionality
5. Check logs: `docker-compose logs -f`

**Deliverable:**
- Docker Compose configuration
- Multi-container application running
- Database and Redis connected
- Volume persistence working
- Complete stack documentation

**Why It Matters:**
Real applications have multiple services. Docker Compose enables local development that mirrors production and simplifies team onboarding.

**If Behind:**
Just run app and database. Skip Redis if needed.

---

### **Day 77: Environment Configuration for Deployment**

**Prerequisites:** Day 76 complete

**Where to Learn:**
1. [12-Factor App Methodology](https://12factor.net/)
2. [FastAPI Settings Management](https://fastapi.tiangolo.com/advanced/settings/)
3. Review Day 44 (Configuration Management)

**120-Minute Breakdown:**
- 0-30m: Review configuration best practices
- 30-60m: Create environment-specific config files
- 60-95m: Implement configuration validation
- 95-115m: Add secrets management strategy
- 115-120m: Document configuration options

**Daily Exercise:**
Enhance `day77/deployment_config/`:

1. Create `config.py` with environment validation:
```python
# Empty code structure placeholder
from pydantic_settings import BaseSettings, SettingsConfigDict

class Settings(BaseSettings):
    # Database
    DATABASE_URL: str
    
    # Redis
    REDIS_URL: str
    
    # API Keys
    GEMINI_API_KEY: str
    OPENAI_API_KEY: str | None = None
    
    # Security
    SECRET_KEY: str
    ALGORITHM: str = "HS256"
    ACCESS_TOKEN_EXPIRE_MINUTES: int = 30
    
    # App
    DEBUG: bool = False
    ENVIRONMENT: str = "production"
    
    model_config = SettingsConfigDict(
        env_file=".env",
        case_sensitive=True,
        extra="forbid"  # Reject unknown variables
    )
```

2. Create environment templates:
   - `.env.example` (committed to git)
   - `.env.development` (local development)
   - `.env.production` (production values placeholder)

3. Add validation:
   - Check all required variables are set
   - Validate URL formats
   - Ensure secrets are not default values

4. Document each configuration option

**Deliverable:**
- Validated configuration system
- Environment templates
- Configuration documentation
- Secrets management guide
- Deployment checklist

**Why It Matters:**
Misconfiguration is a top cause of production failures. Proper config management prevents security breaches and downtime.

**If Behind:**
Just create `.env.example` with your current variables. Skip validation.

---

### **Day 78: Logging & Monitoring**

**Prerequisites:** Day 77 complete

**Where to Learn:**
1. [Python Logging Best Practices](https://docs.python.org/3/howto/logging.html)
2. [FastAPI Logging](https://philstories.medium.com/fastapi-logging-f6237b84ea64)
3. [Structured Logging](https://www.structlog.org/)

**120-Minute Breakdown:**
- 0-30m: Configure structured logging
- 30-60m: Add request/response logging middleware
- 60-90m: Implement error tracking
- 90-115m: Add performance monitoring
- 115-120m: Create logging dashboard queries

**Daily Exercise:**
Build `day78/logging_monitoring/`:

1. Configure logging:
```python
# Empty code structure placeholder
import logging
from pythonjsonlogger import jsonlogger

def setup_logging():
    logger = logging.getLogger()
    handler = logging.StreamHandler()
    formatter = jsonlogger.JsonFormatter(
        "%(asctime)s %(name)s %(levelname)s %(message)s"
    )
    handler.setFormatter(formatter)
    logger.addHandler(handler)
    logger.setLevel(logging.INFO)
```

2. Add request logging middleware:
```python
# Empty code structure placeholder
@app.middleware("http")
async def log_requests(request: Request, call_next):
    start_time = time.time()
    response = await call_next(request)
    duration = time.time() - start_time
    
    logger.info(
        "request_completed",
        extra={
            "method": request.method,
            "path": request.url.path,
            "status": response.status_code,
            "duration": duration
        }
    )
    return response
```

3. Add error tracking
4. Log AI API usage (tokens, costs, latency)
5. Create health check endpoint

**Deliverable:**
- Structured JSON logging
- Request/response logging
- Error tracking with context
- Performance metrics logged
- Health check endpoint
- Log analysis examples

**Why It Matters:**
Production debugging is impossible without good logs. Structured logging enables monitoring tools and quick issue resolution.

**If Behind:**
Just add basic logging to a few endpoints. Use Python's standard logger.

---

### **Day 79: Deployment to Render**

**Prerequisites:** Days 75-78 complete

**Where to Learn:**
1. [Render Documentation](https://render.com/docs)
2. [Deploying FastAPI to Render](https://render.com/docs/deploy-fastapi)
3. [Render Free Tier Guide](https://render.com/docs/free)

**120-Minute Breakdown:**
- 0-30m: Create Render account, explore dashboard
- 30-60m: Configure deployment settings
- 60-95m: Deploy FastAPI application
- 95-115m: Configure PostgreSQL database
- 115-120m: Test production deployment

**Daily Exercise:**
Deploy `day79/render_deployment/`:

1. Create `render.yaml` (Infrastructure as Code):
```yaml
# Empty code structure placeholder
services:
  - type: web
    name: my-fastapi-app
    env: python
    buildCommand: "pip install -r requirements.txt"
    startCommand: "uvicorn app.main:app --host 0.0.0.0 --port $PORT"
    envVars:
      - key: DATABASE_URL
        fromDatabase:
          name: mydb
          property: connectionString
      - key: SECRET_KEY
        generateValue: true
      - key: GEMINI_API_KEY
        sync: false  # Set manually in dashboard

databases:
  - name: mydb
    databaseName: fastapi_db
    user: admin
```

2. Push to GitHub repository
3. Connect Render to GitHub
4. Deploy and monitor build logs
5. Run database migrations in Render
6. Test production API

**Deliverable:**
- Application deployed to Render
- Database provisioned and connected
- Environment variables configured
- Production URL working
- Deployment documentation

**Why It Matters:**
Render offers generous free tier and simple deployment. Shows you can ship applications to production, not just code locally.

**If Behind:**
Deploy without database. Use SQLite or in-memory storage for testing.

---

### **Day 80: Alternative Deployment Options**

**Prerequisites:** Day 79 complete

**Where to Learn:**
1. [Railway Documentation](https://docs.railway.app/)
2. [Fly.io FastAPI Guide](https://fly.io/docs/languages-and-frameworks/python/)
3. [Platform Comparison 2025](https://www.g2.com/categories/platform-as-a-service-paas)

**120-Minute Breakdown:**
- 0-40m: Explore Railway deployment
- 40-80m: Understand serverless options (Vercel, AWS Lambda)
- 80-110m: Document pros/cons of each platform
- 110-120m: Create deployment decision guide

**Daily Exercise:**
Research `day80/deployment_options/`:

1. **Railway:**
   - Deploy same app to Railway
   - Compare with Render (speed, features, pricing)
   - Document Railway-specific configuration

2. **Serverless:**
   - Research Vercel Python support (note: limited FastAPI support)
   - Document when serverless makes sense
   - List limitations for FastAPI

3. Create comparison matrix:
   - Render vs Railway vs Fly.io vs AWS
   - Free tier limits
   - Database options
   - Build times
   - Geographic regions

4. Decision guide: which platform for which use case

**Deliverable:**
- Multi-platform deployment experience
- Platform comparison document
- Deployment checklist for each platform
- Cost analysis
- Recommendation guide

**Why It Matters:**
Different projects need different platforms. Understanding trade-offs shows architectural thinking and helps with freelancing consultations.

**If Behind:**
Just document Render deployment. Skip trying other platforms.

---

### **Day 81: CI/CD Basics with GitHub Actions**

**Prerequisites:** Day 80 complete

**Where to Learn:**
1. [GitHub Actions Documentation](https://docs.github.com/en/actions)
2. [CI/CD for Python](https://realpython.com/python-continuous-integration/)
3. [FastAPI CI/CD Tutorial](https://testdriven.io/blog/fastapi-ci-cd/)

**120-Minute Breakdown:**
- 0-30m: Understand CI/CD concepts
- 30-60m: Create GitHub Actions workflow
- 60-95m: Add linting and basic checks
- 95-115m: Set up automatic deployment
- 115-120m: Test workflow with a commit

**Daily Exercise:**
Setup `day81/ci_cd/`:

1. Create `.github/workflows/deploy.yml`:
```yaml
# Empty code structure placeholder
name: Deploy to Render

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      
      - name: Install dependencies
        run: pip install -r requirements.txt
      
      - name: Run linting
        run: |
          pip install ruff
          ruff check .
      
      - name: Trigger Render Deploy
        run: |
          curl -X POST ${{ secrets.RENDER_DEPLOY_HOOK }}
```

2. Add Render deploy hook to GitHub secrets
3. Configure branch protection rules
4. Test: push code → automatic deployment
5. Monitor workflow execution

**Deliverable:**
- GitHub Actions workflow configured
- Automatic deployment on push to main
- Linting checks in pipeline
- Deployment notifications
- CI/CD documentation

**Why It Matters:**
Manual deployment is error-prone. CI/CD enables rapid iteration and ensures code quality before deployment.

**If Behind:**
Just create a basic workflow that runs on push. Skip automatic deployment.

---

### **Day 82-90: Final Capstone Project - AI-Powered Platform**

**Prerequisites:** All previous days complete

**Project Overview:**
Build a complete **AI-Powered Content Platform** that combines everything learned:

### **Capstone Requirements:**

**Core Features:**
1. **User Management Module:**
   - Registration/login with JWT
   - Role-based access (admin, creator, viewer)
   - User profiles with avatars
   - OAuth2 compliant authentication

2. **Content Module:**
   - Create/edit/delete articles
   - AI-powered content generation
   - AI-powered summarization
   - Tag system (many-to-many)
   - Full-text search

3. **AI Chat Module:**
   - Personal AI assistant for each user
   - Conversation history
   - Streaming responses
   - Context-aware chat
   - Token usage tracking

4. **Notification System (Event-Driven):**
   - Redis-based event queue
   - Email notifications (simulated)
   - In-app notifications
   - User notification preferences

5. **Admin Dashboard:**
   - User management
   - Content moderation with AI
   - Analytics (users, articles, AI usage)
   - System health monitoring

**Technical Requirements:**
- Modular architecture (separate modules for auth, content, chat, admin)
- Repository + Service layers
- PostgreSQL with complex relationships
- Redis for events and caching
- Alembic migrations
- Docker containerization
- Deployed to Render/Railway
- CI/CD pipeline
- Comprehensive logging
- API documentation

**120-Minute Breakdown (9 Days):**

**Day 82:** Project setup, database design, initial models
**Day 83:** Authentication module (JWT, OAuth2, RBAC)
**Day 84:** Content module (CRUD, search, tags)
**Day 85:** AI integration (Gemini, content generation, summarization)
**Day 86:** Chat module (conversations, streaming)
**Day 87:** Event-driven notifications (Redis, handlers)
**Day 88:** Admin dashboard (user management, analytics)
**Day 89:** Deployment (Docker, Render, environment setup)
**Day 90:** Polish, documentation, video demo

**Deliverable Structure:**
```text
ai_content_platform/
├── app/
│   ├── main.py
│   ├── config.py
│   ├── database.py
│   ├── modules/
│   │   ├── auth/
│   │   ├── users/
│   │   ├── content/
│   │   ├── chat/
│   │   ├── notifications/
│   │   └── admin/
│   ├── shared/
│   │   ├── dependencies.py
│   │   ├── middleware.py
│   │   └── utils.py
│   └── events/
│       ├── publisher.py
│       ├── subscriber.py
│       └── handlers/
├── alembic/
├── tests/ (basic structure)
├── docker-compose.yml
├── Dockerfile
├── render.yaml
├── .github/workflows/
├── requirements.txt
├── README.md
└── docs/
    ├── API.md
    ├── ARCHITECTURE.md
    └── DEPLOYMENT.md
```

**Final Deliverables:**
1. **Complete GitHub Repository:**
   - Clean commit history (90 days of commits)
   - Professional README with:
     - Project description
     - Features list
     - Architecture diagram
     - Setup instructions
     - API documentation link
     - Screenshots/GIFs
     - Live demo link
   - Comprehensive documentation
   - Example `.env` file

2. **Live Deployment:**
   - Production URL on Render/Railway
   - Working database
   - All features functional
   - Monitoring enabled

3. **Portfolio Materials:**
   - 3-5 minute demo video
   - Architecture diagram
   - Key features showcase
   - Technical challenges solved

4. **Documentation:**
   - API reference (OpenAPI/Swagger)
   - Architecture decisions document
   - Deployment guide
   - Local development guide

**Why It Matters:**
This capstone combines every skill learned: Python OOP, FastAPI, PostgreSQL, Redis, LLM APIs, Docker, deployment, and architecture. It's a portfolio piece that demonstrates production-ready backend engineering skills.

**If Behind:**
Simplify by removing chat module and notification system. Focus on content CRUD with basic AI features and authentication.

---

## Final Week Deliverables Checklist (Week 12-13):

- ✅ Docker containerization mastered
- ✅ Docker Compose for local development
- ✅ Production configuration management
- ✅ Structured logging and monitoring
- ✅ Deployed to cloud platform
- ✅ CI/CD pipeline configured
- ✅ Complete capstone project
- ✅ Portfolio-ready documentation
- ✅ Live production deployment
