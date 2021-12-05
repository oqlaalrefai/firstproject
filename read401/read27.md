# Django Models
- Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc.
- When designing your models it makes sense to have separate models for every "object" (a group of related information).
- Once we've decided on our models and field, we need to think about the relationships. Django allows you to define relationships that are one to one (OneToOneField), one to many (ForeignKey) and many to many (ManyToManyField)

## Model primer
- **Models** are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata.
- **Fields** A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables. Each database record (row) will consist of one of each field value.
  - `models.CharField` which means that this field will contain strings of alphanumeric characters.
  - `max_length=20`  States that the maximum length of a value in this field is 20 characters.
  - `help_text='Enter field documentation'`  provides a text label to display to help users know what value to provide when this value is to be entered by a user via an HTML form.
  - Common field arguments:help_text,verbose_name,default,null,blank,choices,primary_key
  - Common field types : CharField,TextField,IntegerField,DateField and DateTimeField,EmailField,FileField and ImageField,AutoField,ForeignKey,ManyToManyField

## Metadata
You can declare model-level metadata for your Model by declaring class Meta
```
class Meta:
    ordering = ['-my_field_name']
```
One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type. You do this by specifying the match order in a list of field names to the ordering attribute, as shown above.

## Methods
- Minimally, in every model you should define the standard Python class method __str__() to return a human-readable string for each object.
- Minimally, in every model you should define the standard Python class method __str__() to return a human-readable string for each object.

## Model management
- Creating and modifying records
To create a record you can define an instance of the model and then call `save()`.
  - Create a new record using the model's constructor : `record = MyModelName(my_field_name="Instance #1")`
  - Save the object into the database : `record.save()`
  - You can access the fields in this new record using the dot syntax, and change the values
  ```
    print(record.id) # should return 1 for the first record.
    print(record.my_field_name) # should print 'Instance #1'
    # Change record by modifying the fields, then calling save().
    record.my_field_name = "New Instance Name"
    record.save()
  ```
- Searching for records
You can search for records that match certain criteria using the model's objects attribute
  - We can get all records for a model as a QuerySet, using objects.all(). The QuerySet is an iterable object, meaning that it contains a number of objects that we can iterate/loop through.
  - Django's filter() method allows us to filter the returned QuerySet to match a specified text or numeric field against particular criteria
  - The fields to match and the type of match are defined in the filter parameter name, using the format: field_name__match_type

## Re-run the database migrations
All your models have now been created. Now re-run your database migrations to add them to your database.
```
python3 manage.py makemigrations
python3 manage.py migrate
```
## Creating a superuser
In order to log into the admin site, we need a user account with Staff status enabled. In order to view and create records we also need this user to have permissions to manage all our objects.  You can create a "superuser" account that has full access to the site and all needed permissions using manage.py.
`python3 manage.py createsuperuser`

## Logging in and using the site
To login to the site, open the /admin URL (e.g. http://127.0.0.1:8000/admin) and enter your new superuser userid and password credentials

## Advanced configuration
Django does a pretty good job of creating a basic admin site using the information from the registered models:

Each model has a list of individual records, identified by the string created with the model's __str__() method, and linked to detail views/forms for editing. By default, this view has an action menu at the top that you can use to perform bulk delete operations on records.
The model detail record forms for editing and adding records contain all the fields in the model, laid out vertically in their declaration order.
- You can further customise the interface to make it even easier to use
1. List views:
   - Add additional fields/information displayed for each record.
   - Add filters to select which records are listed, based on date or some other selection value (e.g. Book loan status).
   - Add additional options to the actions menu in list views and choose where this menu is displayed on the form.
2. Detail views
   - Choose which fields to display (or exclude), along with their order, grouping, whether they are editable, the widget used, orientation
   - Add related fields to a record to allow inline editing 
## Register a ModelAdmin class
To change how a model is displayed in the admin interface you define a ModelAdmin class (which describes the layout) and register it with the model.














