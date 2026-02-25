# EXERCISES — SQL Fundamentals (SQLite + Python)

## Objective
Practice the core SQL patterns you will need before we introduce SQLAlchemy:
- `INSERT`, `SELECT`, `UPDATE`, `DELETE`
- `JOIN`
- transactions (`BEGIN` / `COMMIT` / `ROLLBACK`)
- **parameterized queries** (no string concatenation!)

## Files
- `exercises.py` — implement the TODO functions.
- `tests/test_exercises.py` — autograder tests.

## Setup
```bash
python -m venv .venv
source .venv/bin/activate   # mac/linux
# .venv\Scripts\activate  # windows
pip install -r requirements.txt
```

## Run
```bash
python src/exercises.py
pytest -q tests/test_exercises.py
```

## Rules
✅ Use parameterized queries with `?` placeholders:
```python
conn.execute("SELECT * FROM students WHERE email = ?;", (email,))
```

❌ Do not do this:
```python
conn.execute("SELECT * FROM students WHERE email = '" + email + "';")
```

## What the autograder checks
- `add_student()` inserts and returns the new id
- `find_student_by_email()` returns correct row or `None`
- `rename_student()` returns correct `rowcount`
- `delete_student()` returns correct `rowcount`
- `enroll_student()` inserts into enrollments without committing
- `list_enrollments()` correctly joins and orders results
- Transaction rollback behavior works (duplicate enrollment triggers rollback)
