# HOMEWORK — Mini Gradebook Database (Raw SQL)

## Objective
Build a small normalized gradebook schema and write query helpers using **raw SQL**.
This will prepare you for next lesson when we do the same thing with SQLAlchemy ORM.

## Files
- `src/homework.py` — implement TODO functions and then uncomment the demo blocks in `main()`.
- `tests/test_homework.py` — autograder tests.

## Requirements (Schema)
You must create and use these tables:

### `students`
- `id` (PK)
- `name` (required)
- `email` (required, UNIQUE)

### `assignments`
- `id` (PK)
- `title` (required)
- `max_points` (required, > 0)

### `grades`
- `id` (PK)
- `student_id` (FK -> students.id)
- `assignment_id` (FK -> assignments.id)
- `score` (required, >= 0)
- `UNIQUE(student_id, assignment_id)` to prevent duplicates

## Rules
- Use **parameterized SQL** for any variables (`?` placeholders).
- Keep the schema normalized (no storing lists in a single column).
- Don’t commit inside helper functions unless explicitly required — let the caller decide.

## How to run
```bash
pip install -r requirements.txt
python homework.py
pytest -q tests/test_homework.py
```

## What the autograder checks
- schema exists and enforces basic constraints
- insert helper functions return ids
- `list_students()` orders by name
- `student_grade_report()` computes percent correctly
- `leaderboard()` aggregates average percent per student
