Project created for learning basics of django framework.
Tutorial source: https://www.youtube.com/channel/UCW5YeuERMmlnqo4oq8vwUpg
Below you can find some information about creating app, managing it etc...

## Installation
* Python required
* For vscode: https://code.visualstudio.com/docs/python/tutorial-django
* Creating project
  > django-admin startproject [name]
* Running server
	> python manage.py runserver
* Default location
	> localhost:8000
* There is also built-in database (SQLite)

## URLs, Views
How does it work?
* browser ---request---> urls.py
* urls.py runs function from views.py (ex. 'about') 
* views.py ---response---> browser

## Html templates
* It's good to place them in templates directory
* Remember to add 'templates' to DIRS in settings
* Just create the template, then call it from views.py

## Apps
* Split project into smaller modules
* Each app controls a certain section
* For example: App can include articles, accounts, shopping etc.
* Creating app
  > python manage.py startapp [name]
* Each app have own templates
* Remember to include app.urls in main app urls.py

## Models
* Class which represent a table in database
* Each type of data is represented by it's own model (articles, users, books...)
* Each model maps to a single table in database
* There are many field types in models.Model class, you can inherit from it ofc

## Migrations
* Create DB table based on written code in models
* You need to make migration file first, django will do it automatically
  > python manage.py makemigrations
* Migrate
  > python manage.py migrate