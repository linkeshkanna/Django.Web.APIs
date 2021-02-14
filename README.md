# django.web.apis
Web APIs Developed Using Python Django

Getting Started:
python -m pip install django
python -m django --version
django-admin startproject MyBlogProject
python .\MyBlogProject\manage.py runserver

Applications and Routes:
python manage.py startapp blog - This will create folder "blog" and py files in MyBlogProject
create urls.py in blog folder
add urlpatterns in urls.py
create def home(request): in views.py
add path("blog/", include("blog.urls")) in MyBlogProject/urls.py