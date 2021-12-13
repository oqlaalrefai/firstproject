# DRF Permissions

### Permissions
- Together with authentication and throttling, permissions determine whether a request should be granted or denied access.
- Permission checks are always run at the very start of the view, before any other code is allowed to proceed.
- Permission checks will typically use the authentication information in the `request.user` and `request.auth` properties to determine if the incoming request should be permitted.
- The simplest style of permission would be to allow access to any authenticated user, and deny access to any unauthenticated user. This corresponds to the `IsAuthenticated` class in REST framework.
- A slightly less strict style of permission would be to allow full access to authenticated users, but allow read-only access to unauthenticated users. This corresponds to the `IsAuthenticatedOrReadOnly` class in REST framework.
### How permissions are determined
- Permissions in REST framework are always defined as a list of permission classes.
- If any permission check fails, an `exceptions.PermissionDenied` or `exceptions.NotAuthenticated`
- The request was successfully authenticated, but permission was denied. — An `HTTP 403 Forbidden` response will be returned.
- The request was not successfully authenticated, and the highest priority authentication class does not use WWW-Authenticate headers.  An `HTTP 403 Forbidden` response will be returned.
- The request was not successfully authenticated, and the highest priority authentication class does use WWW-Authenticate headers. — An `HTTP 401 Unauthorized` response, with an appropriate WWW-Authenticate header will be returned.

### Object level permissions 
- are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.
- its run by REST framework's generic views when .get_object() is called. 

### Setting the permission policy
- The default permission policy may be set globally, using the DEFAULT_PERMISSION_CLASSES setting.
- You can also set the authentication policy on a per-view, or per-viewset basis, using the APIView class-based views.


- The `AllowAny` permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.
- The `IsAuthenticated` permission class will deny permission to any unauthenticated user, and allow permission otherwise.
- The `IsAdminUser` permission class will deny permission to any user, unless `user.is_staff` is `True` in which case permission will be allowed.
- The `IsAuthenticatedOrReadOnly` will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; `GET`, `HEAD` or `OPTIONS`.

## DjangoModelPermissions
This permission must only be applied to views that have a .queryset property or get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned.

  - `POST` requests require the user to have the `add` permission on the model.
  - `PUT` and PATCH requests require the user to have the `change` permission on the model.
  - `DELETE` requests require the user to have the `delete` permission on the model.

- **`DjangoModelPermissionsOrAnonReadOnly`** Similar to DjangoModelPermissions, but also allows unauthenticated users to have read-only access to the API.

- `DjangoObjectPermissions` does not require the `django-guardian` package

### Custom permissions
To implement a custom permission, override BasePermission and implement either, or both, of the following methods:

`.has_permission(self, request, view)`
`.has_object_permission(self, request, view, obj)`
The methods should return `True` if the request should be granted access, and `False` otherwise.

### The following third party packages are also available.
- **DRF - Access Policy** :
provides a way to define complex access rules in declarative policy classes that are attached to view sets or function-based views.
- **Composed Permissions**
provides a simple way to define complex and multi-depth (with logic operators) permission objects, using small and reusable components.
- **REST Condition**
is another extension for building complex permissions in a simple and convenient way. The extension allows you to combine permissions with logical operators.
- **DRY Rest Permissions**
provides the ability to define different permissions for individual default and custom actions. This package is made for apps with permissions that are derived from relationships defined in the app's data model.
- **Django Rest Framework Roles**
 makes it easier to parameterize your API over multiple types of users.
- **Django REST Framework API Key**
provides permissions classes, models and helpers to add API key authorization to your API. It can be used to authorize internal or third-party backends and services which do not have a user account.
- **Django Rest Framework Role Filters**
provides simple filtering over multiple types of roles.
- **Django Rest Framework PSQ**
is an extension that gives support for having action-based permission_classes, serializer_class, and queryset dependent on permission-based rules.