# Flask Todo App

A simple, full-featured Todo web application built with [Flask](https://flask.palletsprojects.com/) and [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/). This project demonstrates basic CRUD (Create, Read, Update, Delete) operations using a SQLite database and a minimal web interface.

---

## Features

- **Add Tasks:** Create new todo items using a simple form.
- **View Tasks:** See a list of all tasks, ordered by creation date.
- **Update Tasks:** Edit the content of existing tasks.
- **Delete Tasks:** Remove tasks you no longer need.
- **Persistent Storage:** All tasks are stored in a local SQLite database.
- **Error Handling:** User-friendly error messages for database operations.

---

## Requirements

- Python 3.x
- The packages listed in `requirements.txt`:
  - Flask
  - Flask-SQLAlchemy
  - Jinja2
  - Werkzeug
  - (and others)

---

## Installation

1. **Clone the repository or copy the files to your local machine.**

2. **(Optional) Create and activate a virtual environment:**
   ```sh
   python -m venv .venv
   .venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

4. **Initialize the database:**
   Open a Python shell in your project directory and run:
   ```python
   from app import app, db
   with app.app_context():
       db.create_all()
   ```

5. **Run the application:**
   ```sh
   python app.py
   ```

6. **Open your browser and go to:**
   ```
   http://localhost:5000/
   ```

---

## Project Structure

```
MyLocalCodeSpace/
│
├── app.py
├── requirements.txt
├── templates/
│   ├── index.html
│   └── update.html
└── test.db  # Created after running the app
```

- `app.py`: Main Flask application with routes and database models.
- `requirements.txt`: Python dependencies.
- `templates/`: HTML templates for the web interface.
- `test.db`: SQLite database file (auto-created).

---

## Usage

### Add a Task
- Use the form on the homepage to add a new todo item.

### Update a Task
- Click the "Update" link next to a task, edit the content, and submit.

### Delete a Task
- Click the "Delete" link next to a task to remove it.

---

## Code Overview

- **Model:**  
  The `Todo` class defines the database schema for tasks, including an `id`, `content`, and `date_created`.

- **Routes:**  
  - `/` : Main page to view and add tasks.
  - `/delete/<id>` : Delete a specific task.
  - `/update/<id>` : Update a specific task.

- **Templates:**  
  - `index.html`: Displays the list of tasks and the add form.
  - `update.html`: Form to update a task.

---

## Customization

- You can extend the app by adding user authentication, due dates, task categories, or other features.
- To use a different database (e.g., PostgreSQL), update the `SQLALCHEMY_DATABASE_URI` in `app.py`.

---

## License

This project is provided for educational purposes and as a starting point for your own Flask projects.

---