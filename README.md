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
```

## Usage
To use this library in your Django project, follow these steps:
- Add rest_auth_custom to your INSTALLED_APPS in settings.py

```python
INSTALLED_APPS = [
    'rest_auth',
]
```

- Add the library's URLs to your urls.py:

```python
path('api/auth/', include('rest_auth_custom.urls')),
```

- Customize the library's settings in `settings.py` as needed (e.g. email settings for password reset functionality)

## Customizations
This library includes the following customizations:

## Additional Features
This library includes the following additional features:

## Contributing
If you would like to contribute to this library, please fork the repository and submit a pull request.

## Support
If you have any issues or questions about this library, please open an issue on this repository or contact
