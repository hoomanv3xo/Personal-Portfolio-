# Personal Portfolio (Django)

A personal portfolio website built with Django. It has a home page and a projects section where each project is managed through the Django admin, including its title, description, technology, image, and GitHub link.

## Features

- Home page with an intro and links
- Projects page with animated cards that fade in on scroll
- Project detail page with the full description, technology used, and a GitHub button
- Projects managed from the Django admin, with no code changes needed to add or edit one
- Optional GitHub link per project (the button is hidden when no link is set)
- Neon dark theme built with Bootstrap 5 and custom CSS

## Tech Stack

- Python 3
- Django 6.0
- SQLite
- HTML, CSS, JavaScript
- Bootstrap 5.3 (via CDN)

## Project Structure

```
rp-portfolio/
├── manage.py
├── db.sqlite3
├── personal_portfolio/      # project settings and root URLs
├── pages/                   # home page app
├── projects/                # projects app (model, views, urls, admin)
│   └── templates/projects/
│       ├── project_index.html
│       └── project_detail.html
├── templates/               # shared templates
│   ├── base.html
│   └── home.html
└── uploads/                 # uploaded project images (created automatically)
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/hoomanv3xo/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Create a virtual environment

```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux
```

### 3. Install dependencies

```bash
pip install django
```

If your project image field is an `ImageField`, also run `pip install pillow`.

### 4. Set up the database

```bash
python manage.py migrate
```

### 5. Create an admin user

```bash
python manage.py createsuperuser
```

### 6. Run the development server

```bash
python manage.py runserver
```

Then open:

- Home: http://127.0.0.1:8000/
- Projects: http://127.0.0.1:8000/projects/
- Admin: http://127.0.0.1:8000/admin/

## Adding a Project

1. Log in at `/admin/`.
2. Open **Projects** and click **Add project**.
3. Fill in the title, description, technology, and image, and optionally the GitHub URL.
4. Save. The project appears on `/projects/` right away.

## Configuration Notes

- `MEDIA_URL` in `settings.py` should be `"/media/"` (with the leading slash) so uploaded images load on every page.
- Templates are loaded from the top-level `templates/` folder first, then from each app's `templates/` folder.
- `DEBUG = True` and the included `SECRET_KEY` are for development only. Before deploying, set `DEBUG = False`, set `ALLOWED_HOSTS`, and load the secret key from an environment variable.

## Roadmap

- Navigation bar linking Home and Projects
- Live demo link field for each project
- Technology tags on project cards
- Deployment

## Author

**Hooman Vahdat**
GitHub: [hoomanv3xo](https://github.com/hoomanv3xo)
Website: [hooman-codes.ca](http://www.hooman-codes.ca)

