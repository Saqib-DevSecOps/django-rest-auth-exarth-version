# Django Rest Auth!
This library is a fork of the popular django-rest-auth library, with some customizations and additional features added to suit my specific use case.

## Features
- User registration and authentication using email and password
- User management (view, update, and delete)
- Token-based authentication
- Password reset and change functionality
- Social authentication (e.g. Facebook, Google)

## Installation
To install this library, simply run the following command:
Copy code
```
pip install git+https://github.com/saqib-devops/django-rest-auth-exarth-version.git
-------------------------OR-------------------------------------
pip install exarth-rest-auth
```


## Usage
To use this library in your Django project, follow these steps:
- Add exarth_rest_auth to your INSTALLED_APPS in settings.py

```python
INSTALLED_APPS = [
    'exarth_rest_auth',
    'exarth_rest_auth.registration'
]
```

- Add the library's URLs to your urls.py:

```python
urlpatterns += [
    re_path(r'^rest-auth/', include('exarth_rest_auth.urls')),
    re_path(r'^rest-auth/registration/', include('exarth_rest_auth.registration.urls')),
]

```
## JWT Support

By default django-rest-auth uses Django’s Token-based authentication. If you want to use JWT authentication, follow these steps:

    Install djangorestframework-jwt
djangorestframework-jwt is currently the only supported JWT library.

The JWT_PAYLOAD_HANDLER and JWT_ENCODE_HANDLER settings are imported from the django-rest-framework-jwt settings object.
Refer to the library’s documentation for information on using different encoders.

Add the following configuration value to your settings file to enable JWT authentication.

    REST_USE_JWT = True

By default Token authentication is used 

## Note
- The remaining features are same as rest auth , the only difference is it support latest version of Django