# Databases + SQL Fundamentals (Prep for ORM / SQLAlchemy)

Welcome! This repository is your starter project for learning **relational databases**, **SQL**, and (next lesson) the motivation for using an **ORM** like **SQLAlchemy**.

---

## Repo Structure (What each file/folder is for)

### Top-level files
- **`README.md`**  
  You are here. Explains the project layout and how to run everything.

- **`databases_orm_prep_canvas.html`**  
  Lesson page (Canvas-ready HTML) introducing:
  - what relational databases are
  - basic SQL
  - keys, relationships, joins
  - transactions
  - why ORMs exist

- **`demo.py`** (Instructor demo / reference)  
  A complete working example that:
  - creates a SQLite database from scratch
  - creates tables + constraints
  - inserts sample data
  - runs queries (including joins + aggregation)
  - demonstrates safe **parameterized queries**
  - demonstrates transaction rollback

- **`exercises.py`** (In-class practice)  
  Your practice file with **TODOs**. You will implement functions for:
  - `INSERT`, `SELECT`, `UPDATE`, `DELETE`
  - a `JOIN` query
  - transaction behavior  
  This file is designed for you to run repeatedly while you work.

- **`homework.py`** (Homework assignment)  
  A mini project: build a normalized gradebook schema and write query helpers.
  You will implement schema + insert helpers + report queries.

- **`EXERCISES_README.md`**  
  Detailed instructions specific to `exercises.py`.

- **`HOMEWORK_README.md`**  
  Detailed instructions specific to `homework.py`.

- **`requirements.txt`**  
  Python dependencies used by the autograder (primarily `pytest`).

- **`.gitignore`**  
  Prevents committing generated files like SQLite databases (`*.db`) and caches.

---

## Autograding / Tests

### `tests/`
- **`tests/test_exercises.py`**  
  Unit tests for the functions you implement in `exercises.py`.

- **`tests/test_homework.py`**  
  Unit tests for the functions you implement in `homework.py`.

### GitHub Classroom files
- **`.github/workflows/classroom.yml`**  
  GitHub Actions workflow that runs the tests on every push / pull request.

- **`.github/classroom/autograding.json`**  
  GitHub Classroom autograding configuration (how points are assigned).

---

## Database Files (Important)
This project uses **SQLite** for convenience (no server setup).  
When you run the scripts, they will create local database files such as:

- `demo_school.db`
- `exercises.db`
- `homework_gradebook.db`

✅ These files are **generated artifacts** and should **NOT** be committed to Git.  
They are ignored by `.gitignore`.

---

## How to Run (Local)

### 1) Create and activate a virtual environment
```bash
python -m venv .venv
source .venv/bin/activate   # mac/linux
# .venv\Scripts\activate  # windows
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Run the lesson demo / exercises / homework
```bash
python demo.py
python exercises.py
python homework.py
```

### 4) Run tests (what the autograder runs)
```bash
pytest -q
```

---

## Recommended workflow
1. Read **`databases_orm_prep_canvas.html`** (concepts).
2. Run **`demo.py`** and study the output and SQL.
3. Complete TODOs in **`exercises.py`** and run:
   - `python exercises.py`
   - `pytest -q tests/test_exercises.py`
4. Complete TODOs in **`homework.py`** and run:
   - `python homework.py`
   - `pytest -q tests/test_homework.py`

---

## Next Lesson Preview: SQLAlchemy ORM
Next lesson you’ll learn how SQLAlchemy lets you:
- define models as Python classes
- use a session to manage transactions
- query using Python expressions
- reduce boilerplate while staying safe with parameterization

But: SQLAlchemy generates SQL under the hood — so today’s SQL practice is essential.
