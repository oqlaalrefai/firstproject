# Django Custum User Model
- Django ships with a built-in User model for authentication
-  always use a custom user model for all new Django projects.

### AbstractUser vs AbstractBaseUser
modern ways to create a custom user model in Django
- AbstractUser actually subclasses AbstractBaseUser but provides more default configuration.
### Superuser
It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out.

# DjangoX
which is an open-source Django starter framework that includes a custom user model, email/password by default instead of username/email/password, social authentication, and more.

- Reusable apps shouldn’t implement a custom user model. A project may use many apps, and two reusable apps that implemented a custom user model couldn’t be used together.
- If you need to store per user information in your app, use a ForeignKey or OneToOneField to settings.AUTH_USER_MODEL as described below.

