# Little Lemon — Restaurant Booking & Menu

A small Django web app for a fictional Mediterranean restaurant, built as the
capstone project for Meta's **Back-End Developer** professional certificate
(Django Web Framework course).

It uses Django's ORM, model forms, class- and function-based views, and custom
templates to provide a booking form backed by the database plus a browsable,
image-rich menu.

## Features

- **Home / About / Menu** pages built on Django templates with static assets
- **Book a table** — `BookingForm` (Django model form) persists to SQLite
- **Menu detail** pages (`/menu_item/<id>`) that pull from the database
- **Admin back end** (`/admin/`) for managing bookings and menu items
- SQLite storage (zero setup), plus a seed fixture so the menu has data on
  first run

## Tech stack

- Python 3.11
- Django 5.2
- SQLite (default Django backing DB)

## Getting started

```bash
# 1. Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Create the database schema
python manage.py migrate

# 4. (Optional) Load the sample menu data
python manage.py loaddata menu

# 5. Create an admin account so you can log into /admin/
python manage.py createsuperuser

# 6. Run it
python manage.py runserver
```

Then open http://127.0.0.1:8000/.

### Quick smoke test

```bash
python manage.py check          # no issues
python manage.py test           # Django test runner
```

## Routes

| Path | View |
|---|---|
| `/` | Home |
| `/about/` | About |
| `/book/` | Booking form |
| `/menu/` | Full menu (from DB) |
| `/menu_item/<int:pk>/` | Single menu item detail |
| `/admin/` | Django admin |

## Project layout

```
littlelemon/
  settings.py        project configuration
  urls.py            root URLconf
restaurant/
  models.py          Booking, Menu
  forms.py           BookingForm
  views.py           home / about / book / menu / menu_item
  templates/         HTML templates
  static/            CSS + images
  fixtures/menu.json sample menu data
manage.py
requirements.txt
```

## Credits

Built as part of the Meta Back-End Developer Professional Certificate (Coursera).
Restaurant photography is part of the course materials / Little Lemon brand assets.