# Beginner’s Guide to Docker
**Docker** is really just Linux containers which are a type of virtualization docker is a way to run Linux containers

## Containers vs Virtual Environments
- Virtual environments are used to isolate Python software packages locally
- virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version.
- Also we can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.

## Images and containers
Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.
- Dockerfile is a list of instructions for creating an image

## A baking analogy we can use here is as follows:
- A Dockerfile is the recipe for a cake
- An image is a snapshot of the recipe at a given time
- A docker-compose.yml says how to make the cake
- And the container is the actual, baked cake
## Image Layers
Every image is made up of one or more image layers. The base layer is often a flavor of Linux, like alpine.
- each image layer is immutable–unchanged–like a git commit
- Docker caches the steps in a Dockerfile to speed up subsequent builds.
- When a change is made to a step, all steps following it will be executed from scratch.

## Containers
as a Dockerfile is a list of image instructions there is also a docker-compose.yml file that is a list of container instructions.
- Containers are a lightweight alternative to Virtual Machines
- Containers are a running instance of an image
- docker-compose.yml controls how to run the container
- containers are stateless and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases (which we didn’t cover here).

## Dockerized Django
We’ll now create a Dockerfile for our image which will completely replace our local dev environment, so this will have Python 3 and Django. Then we’ll add a docker-compose.yml for the container instructions. 

# Django for APIs - Library Website

- Django REST Framework works alongside the Django web framework to create web APIs

-  First we need a dedicated directory on our computer to store the code The location really does not matter; it just needs to be easily accessible.
- A traditional Django website consists of a single project and one (or more) apps representing discrete functionality
- Django automatically generates a new project for us
  - The files have the following roles:  
    - `__init__.py` is a Python way to treat a directory as a package; it is empty
    - `asgi.py` stands for Asynchronous Server Gateway Interface and is a new option in Django 3.0+
    - `settings.py` contains all the configuration for our project
    - `urls.py` controls the top-level URL routes
    - `wsgi.py` stands for Web Server Gateway Interface and helps Django serve the eventual web pages
    - `manage.py` executes various Django commands such as running the local web server or creating a new app.

- Run migrate to sync the database with Django’s default settings and start up the local Django web server.

- Each app has a `__init__.py` file identifying it as a Python package. There are 6 new files created:

  - `admin.py` is a configuration file for the built-in Django Admin app
  - `apps.py` is a configuration file for the app itself
  - the `migrations/` directory stores migrations files for database changes
  - `models.py` is where we define our database models
  - `tests.py` is for our app-specific tests
  - `views.py` is where we handle the request/response logic for our web app

- Typically developers will also create an urls.py file within each app too for routing.

- Open the text editor of your choice to the config/settings.py file. The first step is to add the new app to our INSTALLED_APPS configuration.
- Then run migrate to sync our database with the changes.
### models
This is a basic Django model where we import models from Django on the top line and then create a Book class that extends it

### Admin
We can start entering data into our new model via the built-in Django app. But we must do two things first: create a superuser account and update admin.py so the app is displayed

### Views
The views.py file controls how the database model content is displayed.

### URLs
We need to set up both the project-level urls.py file and then one within the app. When a user visits our site they will first interact with the config/urls.py file so let’s configure that first. Add the include import on the second line and then a new path for our  app.

## Django REST Framework
The api app will not have its own database models so there is no need to create a migration file and run migrate to update the database.

- URLs
Let’s start with our URL configs. Adding an API endpoint is just like configuring a traditional Django app’s routes. First at the project-level we need to include the api app and configure its URL route, which will be api/.Then create a urls.py file within the api app. and update it

- Views
Next up is our views.py file which relies on Django REST Framework’s built-in generic class views.

- serializer
is to translates data into a format that is easy to consume over the internet, typically JSON, and is displayed at an API endpoint. 
