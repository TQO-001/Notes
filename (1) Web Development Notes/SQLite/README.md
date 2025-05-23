# 📝 SQLite for YouTube Clone (FastAPI)

---

## 📦 What Is SQLite?

- A lightweight, file-based database — no server needed.
- Great for small to medium web apps (like your YouTube clone).
- Stored in a single `.db` file (e.g., `videos.db`).

---

## 🔧 Tools You’ll Use:

- `sqlite3` (Python module)
- SQL queries (like `SELECT`, `INSERT`, `UPDATE`)
- SQLite browser (optional for visual inspection)

---

## 📁 Project Structure (Example)

```
mytube/
│
├── main.py               ← FastAPI app
├── database.py           ← DB setup & functions
├── videos.db             ← SQLite DB file
└── models.py             ← Video model (Pydantic/ORM)
```

---

## 📚 Basic SQL Concepts (with Examples)

### ✅ Create Table

```sql
CREATE TABLE videos (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    filename TEXT NOT NULL,
    description TEXT,
    uploaded_at TEXT
);
```

### ➕ Insert Video

```sql
INSERT INTO videos (title, filename, description, uploaded_at)
VALUES ('Funny Cats', 'funnycats.mp4', 'A compilation of cat videos', '2025-05-23');
```

### 📥 Fetch Videos

```sql
SELECT * FROM videos;
```

### 🔍 Search by Title

```sql
SELECT * FROM videos WHERE title LIKE '%cat%';
```

### 🗑️ Delete

```sql
DELETE FROM videos WHERE id = 1;
```

---

## 🐍 Python Code with SQLite (basic usage)

### 🛠️ Connect & Execute

```python
import sqlite3

con = sqlite3.connect("videos.db")
cur = con.cursor()

cur.execute("SELECT * FROM videos")
rows = cur.fetchall()
for row in rows:
    print(row)

con.close()
```

---

## 🧠 Important Concepts You’ll Need:

|Concept|Example Use|
|---|---|
|`PRIMARY KEY`|Uniquely identify each video|
|`AUTOINCREMENT`|Auto-increase video ID|
|`TEXT`|Store strings like titles, filenames|
|`REAL`|(Optional) Store ratings, durations|
|`DATE/TEXT`|Save upload time|
|`LIKE`|For search (`WHERE title LIKE '%cat%'`)|

---

## 🛠️ FastAPI + SQLite Integration

In `database.py`:

```python
import sqlite3

def get_db_connection():
    conn = sqlite3.connect("videos.db")
    conn.row_factory = sqlite3.Row  # So you can access columns by name
    return conn
```

In `main.py`:

```python
from fastapi import FastAPI
from database import get_db_connection

app = FastAPI()

@app.get("/videos")
def list_videos():
    conn = get_db_connection()
    videos = conn.execute("SELECT * FROM videos").fetchall()
    conn.close()
    return [dict(video) for video in videos]
```

---

## 📌 Next Steps to Learn More

- Practice SQL here: [https://sqliteonline.com](https://sqliteonline.com/)
- Try making simple queries using the terminal:  
    Run: `sqlite3 videos.db` → You can now type SQL directly.
- Use a GUI tool like **DB Browser for SQLite** (Windows/Mac/Linux) to inspect the `.db` file.

---

Would you like me to scaffold the whole **FastAPI + SQLite YouTube clone project** for you to build from? I can generate that next.