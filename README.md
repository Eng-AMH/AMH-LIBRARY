# AMH Library

A web-based library management system built with Flask, designed around catalog discovery, user accounts, saved books, and an administrative workspace.

**Live demo:** https://amhlibrary.pythonanywhere.com/

## Overview

AMH Library brings common library workflows into one web application: browsing and searching the catalog, viewing book details, saving favorites, tracking recently viewed items, and managing catalog data from an admin area.

## Features

- **Accounts and access control:** registration, login, logout, password reset, and role-aware access.
- **Catalog:** browse, search, filter by category, and open individual book pages.
- **Personal library tools:** favorites and recently viewed books.
- **Admin workspace:** manage books, categories, users, contact messages, and dashboard statistics.
- **Security foundations:** password hashing, CSRF protection, and validation controls documented by the project.
- **Interface:** responsive pages with a dark, typography-led visual design.

## Technology

| Area | Technology |
|---|---|
| Backend | Python, Flask |
| Data access | Flask-SQLAlchemy, SQLAlchemy |
| Authentication | Flask-Login |
| Forms and CSRF | Flask-WTF, WTForms |
| Database migrations | Flask-Migrate |
| Email | Flask-Mail |
| Frontend | Jinja templates, CSS, vanilla JavaScript |

The checked-in sample environment defaults to SQLite for local development. The previous documentation also described PostgreSQL deployment; validate the database driver and configuration in the extracted source package before treating that path as deployment-ready.

## Repository contents

The current GitHub repository stores the application source as `AMH LIBRARY.zip` rather than exposing the source tree file-by-file. Extract the archive before working on the app. For easier code review, contributions, and hiring review, the next repository-maintenance step is to commit the actual source tree directly and keep generated archives out of the main browsing path.

## Local setup

1. Clone this repository and extract `AMH LIBRARY.zip`.
2. Create and activate a virtual environment from the extracted application directory.
3. Install the dependencies listed in the repository's `requirements.txt`.
4. Copy `.env.example` into the extracted application directory as `.env`.
5. Set a unique `SECRET_KEY`, review `DATABASE_URL`, and add mail credentials only when email features are needed.
6. Follow the migration and startup instructions in the extracted source package, then run the application with its documented entry point.

The source archive should be inspected before assuming exact migration commands or production deployment settings.

## Configuration

The root `.env.example` contains placeholders only. Key settings include:

- `FLASK_CONFIG` — selects the application configuration.
- `SECRET_KEY` — set a long, randomly generated secret; do not reuse a public value.
- `DATABASE_URL` — defaults to a local SQLite database for development.
- `MAIL_SERVER`, `MAIL_PORT`, `MAIL_USERNAME`, `MAIL_PASSWORD` — SMTP settings, if email is enabled.
- `ADMIN_EMAIL` — administrator contact/configuration value.

Never commit a real `.env` file, API key, email password, or production secret.

## Security notes

- **No admin password is published in this README.** Do not rely on hard-coded or seeded demo credentials in a public deployment.
- Before exposing a deployment publicly, verify how the initial administrator is provisioned and change/remove any default account.
- Use a unique production secret, set production-safe configuration, and confirm HTTPS, database permissions, and email credentials.
- If a credential has ever been committed to Git history, changing the current file alone does not invalidate it; rotate the credential at its source.

## Project status

This repository currently provides a packaged source archive and setup documentation. A source-tree review, dependency verification, and fresh-install test are still needed before making stronger claims about reproducible deployment.

---

Maintained by **Ammar Mostafa Hendam**.
