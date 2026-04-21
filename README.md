# AMH Library — Artificial Mind Hub
https://amhlibrary.pythonanywhere.com/

A premium, production-ready library management system built with Flask + PostgreSQL.

**Created by:** Ammar Mostafa Hendam  
**Stack:** Python Flask · PostgreSQL · Bootstrap Icons · Vanilla JS

---

## 🚀 Quick Start

### 1. Clone & Create Virtual Environment
```bash
cd amh_library
python3 -m venv venv
source venv/bin/activate       # Linux/Mac
venv\Scripts\activate          # Windows
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure Environment
```bash
cp .env.example .env
# Edit .env with your database URL and secret key
```

### 4. Setup Database (PostgreSQL)
```sql
-- In psql:
CREATE DATABASE amh_library;
CREATE USER amh_user WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE amh_library TO amh_user;
```

Update `DATABASE_URL` in `.env`:
```
DATABASE_URL=postgresql://amh_user:yourpassword@localhost/amh_library
```

### 5. Initialize & Seed Database
```bash
flask db init
flask db migrate -m "initial"
flask db upgrade
python seed.py
```

### 6. Run the App
```bash
python run.py
```

Visit: **http://localhost:5000**

---

## 🔑 Default Admin Credentials

| Field    | Value                    |
|----------|--------------------------|
| Email    | admin@amhlibrary.com     |
| Password | Admin@1234               |

> ⚠️ **Change the admin password immediately after first login!**

Admin panel: **http://localhost:5000/admin**

---

## 📁 Project Structure

```
amh_library/
├── app/
│   ├── __init__.py          # App factory
│   ├── models.py            # Database models
│   ├── forms.py             # WTForms
│   ├── utils.py             # Helpers & decorators
│   ├── errors.py            # Error handlers
│   ├── auth/                # Authentication blueprint
│   ├── main/                # Main pages blueprint
│   ├── library/             # Library browse blueprint
│   ├── admin/               # Admin panel blueprint
│   ├── templates/           # Jinja2 HTML templates
│   └── static/              # CSS, JS, uploads
├── config.py                # Configuration classes
├── run.py                   # Development server
├── wsgi.py                  # PythonAnywhere entry point
├── seed.py                  # Database seeder
└── requirements.txt
```

---

## 🌐 Deploying on PythonAnywhere

1. Upload project files (or clone from GitHub)
2. Create a virtual environment and install requirements
3. Set up a PostgreSQL database in the PythonAnywhere dashboard
4. Edit `wsgi.py` with your username/path
5. Set environment variables in the PythonAnywhere web app config
6. Run `python seed.py` from the PythonAnywhere console
7. Reload the web app

### Environment Variables on PythonAnywhere
In your web app's WSGI config, add:
```python
os.environ['SECRET_KEY'] = 'your-secret-key'
os.environ['DATABASE_URL'] = 'postgresql://...'
os.environ['FLASK_CONFIG'] = 'production'
```

---

## ✨ Features

- **Authentication**: Register, login, logout, password reset, role-based access
- **Admin Dashboard**: Stats, charts, manage books/categories/users/messages
- **Library**: Browse, search, filter by category, book detail pages
- **User Features**: Favorites, recently viewed, profile
- **Security**: CSRF protection, password hashing, SQL injection prevention, XSS protection
- **Design**: Dark-mode premium UI with Cormorant Garamond typography
- **14 Categories**: Pre-seeded with 60+ books from your collection

---

## 📦 Database Schema

| Table             | Description                              |
|-------------------|------------------------------------------|
| `users`           | User accounts with role-based access     |
| `categories`      | Book categories with icons & colors      |
| `books`           | Full book records with links & metadata  |
| `favorites`       | User ↔ book saved relationships          |
| `recently_viewed` | Per-user reading history (last 20)       |
| `activity_logs`   | All user actions for admin monitoring    |
| `contact_messages`| Contact form submissions                 |

---

*AMH Library © 2025 — Artificial Mind Hub*
