Project created for learning basics of django framework.

Tutorial source: https://www.youtube.com/channel/UCW5YeuERMmlnqo4oq8vwUpg

Below you can find some information about creating app, managing it etc...

# Part 1 - basics
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


## ORM
* You can use django object-relational mapping
* Open shell
  > python manage.py shell
* Adding object to database (article example):
  > from articles.models import article
  > my_article = Article() # creating object
  > my_article.title = "Lion"
  > my_article.body = "Big lion eats a lot of meat!"
  > my_article.save() # object -> query translation -> database
  > 
  > Article.objects.all() # print created articles
* This article is now in database!
* Use sql browser or shell to show created records


## Django admin
* In browser open
  > localhost:8000/admin
* CMS at your service


<br>
# Part 2 - Creating API
## Django Rest Framework
* The only thing to do is
  > pip instal djangorestframework
* And make separate app for api (optional)
  > python manage.py startapp api
* Don't forget about updating packages list in settings.py 'INSTALLED_APPS'


## Authentication
* Register, log-in, logout, token authentication
* You will need
  > pip install django-rest-auth django-allauth

## CRUD
* Create, Read, Update, Delete fucntions in views.py
* Serializers: Python <-> JSON conversion

