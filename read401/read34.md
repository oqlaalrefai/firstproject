# Django Settings Best Practices
- Managing Django Settings
  - you have several environments Each environment can have its own specific settings
  - Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.
  - Sharing settings between team members :You need a general approach to eliminate human error when working with the settings. 
  - Django settings are a Python code. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

- settings_local.py :The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS
  - Pros:
Secrets not in VCS.
  - Cons:
1. settings_local.py is not in VCS, so you can lose some of your Django environment settings.
2. The Django settings file is a Python code, so settings_local.py can have some non-obvious logic.
3. You need to have settings_local.example (in VCS) to share the default configurations for developers.

- Separate settings file for each environment
This is an extension of the previous approach. It allows you to keep all configurations in VCS and to share default settings between developers.
  - Pros:
1. All environments are in VCS.
2. It’s easy to share settings between developers.
  - Cons:
1. You need to find a way to handle secret passwords and tokens.
2. “Inheritance” of settings can be hard to trace and maintain.

- Environment variables
  - Pros:
1. Configuration is separated from code.
2. Environment parity – you have the same code for all environments.
3. No inheritance in settings, and cleaner and more consistent code.
4. There is a theoretical grounding for using environment variables – 12 Factors.
  - Cons:
1. You need to handle sharing default config between developers.

### 12 Factors
 is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. the collection consists of twelve parts:

Codebase
Dependencies
Config
Backing services
Build, release, run
Processes
Port binding
Concurrency
Disposability
Dev/prod parity
Logs
Admin processes

- django-environ
we see that environment variables are the perfect place to store settings.

- Setting Structure
Instead of splitting settings by environments, you can split them by the source: Django, third- party apps (Celery, DRF, etc.), and your custom settings.

- Naming Conventions
Naming of variables is one of the most complex parts of development. So is naming of settings. We can’t imply on Django or third-party applications, but we can follow these simple rules for our custom (project) settings:

Give meaningful names to your settings.
Always use the prefix with the project name for your custom (project) settings.
Write descriptions for your settings in comments.

### Django Settings: Best practices
- Keep settings in environment variables.
- Write default values for production configuration (excluding secret keys and tokens).
- Don’t hardcode sensitive settings, and don’t put them in VCS.
- Split settings into groups: Django, third-party, project.
- Follow naming conventions for custom (project) settings.