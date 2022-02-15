# Django Vue Tutorial

Have mostly followed [this tutorial from "ProgrammingwithMosh"](https://www.youtube.com/watch?v=rHux0gMZ3Eg&ab_channel=ProgrammingwithMosh).

## Walkthrough

### Setup

- Switching to `pipenv` over `venv` as it seems to be cleaner from a directory perspective.
- Created project with `django-admin startproject storefront .` (the `.` avoids redundant subdirectories with the same name).
- Start project with `python manage.py runserver`.

### My First App

- Every Django project has an `INSTALLED_APPS` array by default in the project's settings.py file.
- `python manage.py startapp APPNAME` creates new app with app name `APPNAME`. Every time you create a new app, you need to register it in the `INSTALLED_APPS` section of the settings file. Format `appname.apps.appnameConfig`

### Views

- A view is a function which takes a request and gives a response. More accurately called a request handler. It lives in views.py in the app subfolder.

### Mapping URLS to Views

- Create `url.py` file in your **app** folder. There should already be a `url.py` in the project folder.
- Import the view you want into a `urlpatterns` (all lower case) array.

```
from django.urls import path
from . import views

urlpatterns = [path("hello/", views.say_hello)]
```

- Import into your **project** `url.py` file, as per the instructions at the top of the file. In our case, this meant adding `path("playground/", include("playground.urls")),` to the `urlpatterns` list.

## Todo

- [ ] Where are all the files in my virtual environment?
- [ ] Connect to PlanetScale CLI with the instructions [HERE](https://github.com/planetscale/cli).
