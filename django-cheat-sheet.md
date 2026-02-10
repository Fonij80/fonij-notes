### Fonij Vocabulary

- VE: virtual environment
- proj: project
- env: environment
- var: variables
- dep: dependency

### Django Cheat Sheet

- Create django project steps:

  1- Create VE: # make sure that python is installed on your system
  - `python -m venv .venv`

  2- Activate VE:
  - `source .venv/bin/activate`

  3- Install django:
  - `python -m pip install django~=<version>`

  4- Create proj:
  - `django-admin startproject <project_name> .` # . means create project in the current folder

  5- Run proj:
  - `python manage.py runserver`

  6- Deactivate VE:
  - `deactivate`

- Database-related commands:
  - Make migrations:
    - `python manage.py makemigrations`

  - Apply available migrations:
    - `python manage.py migrate`

  - Postgres DB URL: $ DATABASE_URL: postgres://<username>:<password>@<host>:<port>/<database>

- App-related commands:
  - Create app:
    - `python manage.py startapp <app_name>`

- Test-related commands:
  - Run Tests:
    - `python manage.py test`

- Dep-related commands:
  - Update pip:
    - `python -m pip install –upgrade pip`

  - Output content of current VE:
    - `pip freeze > requirements.txt`

  - Env vars manager lib:
    - `pip install django-environ`

- VS-code-related commands:
  - Create .gitignore: CTRL + Shift + P

- ngrok-related commands:
  - Install:
    - `sudo snap install ngrok`

  - Connect:
    - `ngrok http 8000`

- API Schema Generation: $ python manage.py spectacular --file api.yaml

- For SSH Access: $ git@github.com:username/repo_name.git
- PAT: $ https://username:PERSONAL_ACCESS_TOKEN@github.com/username/repo.git
