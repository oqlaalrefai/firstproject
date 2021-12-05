# django
- Django is a high-level Python web framework that enables rapid development of secure and maintainable websites
- Django can be (and has been) used to build almost any type of website It can work with any client-side framework, and can deliver content in almost any format
- Django helps developers avoid many common security mistakes by providing a framework that has been engineered to "do the right things" to protect the website automatically
- *password hash* is a fixed-length value created by sending the password through a cryptographic hash function
- Django enables protection against many vulnerabilities by default, including SQL injection, cross-site scripting, cross-site request forgery and clickjacking
- Django code is written using design principles and patterns that encourage the creation of maintainable and reusable code.
- Django is well-supported by many web hosting providers, who often provide specific infrastructure and documentation for hosting Django sites


- Django web applications typically group the code that handles each of these steps into separate files:
  - URLs: While it is possible to process requests from every single URL via a single function, it is much more maintainable to write a separate view function to handle each resource. A URL mapper is used to redirect HTTP requests to the appropriate view based on the request URL
  - View: A view is a request handler function, which receives HTTP requests and returns HTTP responses.
  - Models: Models are Python objects that define the structure of an application's data, and provide mechanisms to manage (add, modify, delete) and query records in the database
  - Templates: A template is a text file defining the structure or layout of a file (such as an HTML page), with placeholders used to represent actual content
- A URL mapper is typically stored in a file named urls.py

- other things provided by Django include:
  - Forms: HTML Forms are used to collect user data for processing on the server. Django simplifies form creation, validation, and processing.


## Creating a project
`django-admin startproject mysite`
-  startproject created:
  - manage.py: A command-line utility that lets you interact with this Django project in various ways
  - The inner mysite/ directory is the actual Python package for your project
  - mysite/__init__.py: An empty file that tells Python that this directory should be considered a Python package
  - mysite/settings.py: Settings/configuration for this Django project. Django settings will tell you all about how settings work
  - mysite/urls.py: The URL declarations for this Django project; a “table of contents” of your Django-powered site
  - mysite/asgi.py: An entry-point for ASGI-compatible web servers to serve your project
  - mysite/wsgi.py: An entry-point for WSGI-compatible web servers to serve your project
- to run the server :
` python manage.py runserver`
  - By default, the runserver command starts the development server on the internal IP at port 8000.
  - If you want to change the server’s port, pass it as a command-line argument`python manage.py runserver 8080`
  - to listen on all available public IPs (which is useful if you are running Vagrant or want to show off your work on other computers on the network), use:`python manage.py runserver 0:8000`
  - The development server automatically reloads Python code for each request as needed.
  - some actions like adding files don’t trigger a restart, so you’ll have to restart the server in these cases.

- What’s the difference between a project and an app? 
app is a Web application that does something 
A project is a collection of configuration and apps for a particular website.
  - A project can contain multiple apps. An app can be in multiple projects.

- To create your app, make sure you’re in the same directory as manage.py and type this command:
`python manage.py startapp polls`
- The include() function
  - allows referencing other URLconfs. Whenever Django encounters include(), it chops off whatever part of the URL matched up to that point and sends the remaining string to the included URLconf for further processing.
  - The idea behind include() is to make it easy to plug-and-play URLs
  - You should always use include() when you include other URL patterns. admin.site.urls is the only exception to this.

- The path() function 
is passed four arguments, two required: route and view, and two optional: kwargs, and name. At this point, it’s worth reviewing what these arguments are for.
  - route: is a string that contains a URL pattern. When processing a request, Django starts at the first pattern in urlpatterns and makes its way down the list, comparing the requested URL against each pattern until it finds one that matches.
  - view : When Django finds a matching pattern, it calls the specified view function with an HttpRequest object as the first argument and any “captured” values from the route as keyword arguments. We’ll give an example of this in a bit.
  - kwargs : Arbitrary keyword arguments can be passed in a dictionary to the target view. We aren’t going to use this feature of Django in the tutorial.
  - name : Naming your URL lets you refer to it unambiguously from elsewhere in Django, especially from within templates. This powerful feature allows you to make global changes to the URL patterns of your project while only touching a single file.

## How Django Works Behind the Scenes

- *Corporate Sponsor*  A group of engineers within a larger, for-profit company decide to open-source internal code
Typically engineers at the company are paid, in part, to work on open source though community involvement from developers outside of the core company occurs as well
- *Solo* An individual developer initially creates code, open sources it, and retains default control
- *Non-profit* Django’s approach when the Django Software Foundation was formed to promote, support, and advance Django.

### Django Software Foundation (DSF)
upports and maintains Django in a number of capacities. The largest expense, by far, is the Fellows Program, paid contractors who triage tickets, manage releases
