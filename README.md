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
## JWT Support (JSON web token)

By default dj-rest-auth uses Django’s Token-based authentication. If you want to use JWT authentication, follow these steps:

    pip Install djangorestframework-simplejwt
djangorestframework-simplejwt is currently the only supported JWT library.

Add a simple_jwt auth configuration to the list of authentication classes.

    REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES':(
        'exarth_rest_auth.jwt_auth.JWTCookieAuthentication',
    )
    }
Add the following configuration value to your settings file to enable JWT authentication in dj-rest-auth.

REST_USE_JWT = True

    Declare what you want the cookie key to be called. If you want to use the refresh token feature, also be sure to set that variable.

JWT_AUTH_COOKIE = 'my-app-auth'

JWT_AUTH_REFRESH_COOKIE = 'my-refresh-token'


This example value above will cause dj-rest-auth to return a Set-Cookie header that looks like this:

Set-Cookie: my-app-auth=xxxxxxxxxxxxx; expires=Sat, 28 Mar 2020 18:59:00 GMT; HttpOnly; Max-Age=300; Path=/

If JWT_AUTH_REFRESH_COOKIE is also set, it will also set a comparable cookie for that. JWT_AUTH_COOKIE is also used while authenticating each request against protected views.

## Note
- The remaining features are same as rest auth , the only difference is it support latest version of Django