# Django HTMX Tailwind Todo List Project

This project demonstrates a modern web application built with Django, HTMX, and Tailwind CSS. The application includes a simple to-do list with a live search feature.

## Table of Contents

- [Django HTMX Tailwind Todo List Project](#django-htmx-tailwind-todo-list-project)
- [Setup Instructions](#setup-instructions)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
- [Running the Project](#running-the-project)
- [Features](#features)
- [Contribution](#contribution)
- [License](#license)

## Setup Instructions

Follow these steps to set up and run the project on your local machine.

### Prerequisites

- Python 3.12.4
- HTMX from <https://unpkg.com/htmx.org@2.0.0/dist/htmx.js>

### Installation

1. **Clone the repository:**

   ```sh
   git clone https://github.com/BAXTOR95/django-todo-list-htmx-tailwind.git
   cd django-todo-list-htmx-tailwind
   ```

2. **Create and activate a virtual environment:**

   ```sh
   python -m venv venv
   source venv/bin/activate
   ```

3. **Install the required Python packages:**

   ```sh
   pip install -r requirements.txt
   ```

4. **Install Tailwind CSS:**

   ```sh
   tailwindcss
   ```

5. **Initialize Tailwind CSS:**

   ```sh
   tailwindcss init
   ```

### Configuration

1. **Update `config/settings.py`:**

   - Add `'todos'` and `'compressor'` to `INSTALLED_APPS`.
   - Configure template directories and static files:

     ```python
     TEMPLATES = [
         {
             ...
             'DIRS': [BASE_DIR / 'templates'],
             ...
         },
     ]

     STATICFILES_FINDERS = [
         ...
         'compressor.finders.CompressorFinder',
     ]

     COMPRESS_ROOT = BASE_DIR / 'static'
     COMPRESS_ENABLED = True
     ```

2. **Configure Tailwind CSS:**
   Update `tailwind.config.js`:

   ```javascript
   module.exports = {
    content: ['./templates/**/*.html'],
    theme: {
     extend: {},
    },
    plugins: [],
   };
   ```

3. **Create necessary directories and files:**

   ```sh
   mkdir -p static/src
   touch static/src/main.css
   ```

4. **Add Tailwind CSS directives to `static/src/main.css`:**

   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

### Running the Project

1. **Generate Tailwind CSS output:**

   ```sh
   tailwindcss -i ./static/src/main.css -o ./static/src/output.css --minify
   ```

2. **Apply migrations and start the development server:**

   ```sh
   python manage.py migrate
   python manage.py runserver
   ```

3. **Open your browser and navigate to:**

   ```text
   http://localhost:8000
   ```

### Features

- **Home Page:** Displays a list of to-do list items on a table.
- **Live Search:** Allows real-time searching through the to-do list using HTMX.

### Contribution

Feel free to fork this project, open issues, and submit pull requests. Contributions are always welcome.

### License

This project is licensed under the [MIT License](LICENSE). See the [LICENSE](LICENSE) file for more information.
