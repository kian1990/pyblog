# settings.py

TEMPLATES = [
    {
        ......
        'DIRS': [BASE_DIR],
        ......
    },
]
ALLOWED_HOSTS = ['*']
STATIC_URL = '/static/'
STATICFILES_DIRS = [ os.path.join(BASE_DIR, "static"),]


# index.html

{% load staticfiles %} <link href="/static/.../..." rel="stylesheet"> 
or
<link href="{% static .../..." rel="stylesheet %}">


# urls.py

from django.conf.urls import url
from django.contrib import admin
from . import view

urlpatterns = [
    url(r'^$', view.blog),url(r'^admin/', admin.site.urls),
]


# view.py

from django.shortcuts import render


def blog(request):
    return render(request, 'index.html')


python manage.py migrate
python manage.py createsuperuser
python manage.py runserver 0:80
