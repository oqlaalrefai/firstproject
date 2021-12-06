# django forms

### HTML Forms :
- The form is defined in HTML as a collection of elements inside <form>...</form> tags, containing at least one input element of type="submit".
- The form attributes define the HTTP method used to send the data and the destination of the data on the server (action):
  - action: The resource/URL where data is to be sent for processing when the form is submitted. If this is not set (or set to an empty string), then the form will be submitted back to the current page URL.
  - method: The HTTP method used to send the data: post used if the data is going to result in a change to the server's database because this can be made more resistant to cross-site forgery request attacks or get used for forms that don't change user data It is recommended for when you want to be able to bookmark or share the URL

### Django form handling process
- the view gets a request, performs any actions required including reading data from the models, then generates and returns an HTML page
- main things that Django's form handling does are:
  - Display the default form the first time it is requested by the user
  - Receive data from a submit request and bind it to the form
  - Clean and validate the data.
  - If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
  - If all data is valid, perform required actions
  - Once all actions are complete, redirect the user to another page.

#### Form
The Form class is form handling system. It specifies the fields in the form, their layout, display widgets, labels, initial values, valid values, and (once validated) the error messages associated with invalid fields. rendering itself in templates using predefined formats (tables, lists, etc.) or for getting the value of any element 
- Declaring a Form:
```
from django import forms

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField()
```
- types of form fields :
BooleanField, CharField, ChoiceField, TypedChoiceField, DateField, DateTimeField, DecimalField, DurationField, EmailField, FileField, FilePathField, FloatField, ImageField, IntegerField, GenericIPAddressField, MultipleChoiceField, TypedMultipleChoiceField, NullBooleanField, RegexField, SlugField, TimeField, URLField, UUIDField, ComboField, MultiValueField, SplitDateTimeField, ModelMultipleChoiceField and ModelChoiceField.

- The arguments that are common to most fields are
required,label,label_suffix,initial,widget,help_text,error_messages,validators,localize and disabled

- Validation : The easiest way to validate a single field is to override the method clean_<fieldname>() for the field you want to check.

### View
he view has to render the default form when it is first called and then either re-render it with error messages if the data is invalid, or process the data and redirect to a new page if the data is valid

## ModelForms
Creating a Form class using the approach described above is very flexible, allowing you to create whatever sort of form page you like and associate it with any model or models.
