# django.web.apis project
Web APIs Developed Using Python Django

Getting Started:
python -m pip install django
python -m pip install --upgrade pip
python -m ensurepip
pip install -r .\requirements.txt
pip list

python -m venv venv-django
venv-django\Scripts\Activate.ps1

python -m django --version

django-admin startproject MyBlogProject
python .\MyBlogProject\manage.py runserver


Applications and Routes:
python manage.py startapp blog - This will create folder "blog" and py files in MyBlogProject
create urls.py in blog folder
add urlpatterns in urls.py
create def home(request): in views.py
add path("blog/", include("blog.urls")) in MyBlogProject/urls.py

Templates:
create templates folder under blog
create blog folder under templates
create template.html in blog folder
blog -> templates -> blog -> home.html and about.html
add blog.apps.BlogConfig in settings.py 
add main.css in static\blog
copy code snippets from bootstrap starter template
bootstrap starter templates: https://getbootstrap.com/docs/4.0/getting-started/introduction/#starter-template
code snippets: https://github.com/CoreyMSchafer/code_snippets/tree/master/Django_Blog/snippets
django blog code: https://github.com/CoreyMSchafer/code_snippets/tree/master/Django_Blog

