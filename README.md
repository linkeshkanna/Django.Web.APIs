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


Admin Page:
python manage.py createsuperuser - No such table auth_user, because no tables created
python manage.py makemigrations - to detect changes
python manage.py migrate
superuser username: linkesh
superuser password: linkesh
superuser email: linkeshkanna@gmail.com


Database and Migrations:
create "Post" model in models.py
add columns aka attributes
python manage.py makemigrations - create 0001_initials.py under migrations
python .\manage.py sqlmigrate blog 0001 - show the SQL Query of the model
python .\manage.py migrate - Run migration
python manage.py shell - python django interactive shell

>>> from blog.models import Post
>>> from django.contrib.auth.models import User
>>> User.objects.all()
>>> User.objects.first()
>>> User.objects.filter(username='linkesh')
>>> User.objects.filter(username='linkesh').first()
>>> user = User.objects.filter(username='linkesh').first()
>>> user
>>> user.id
>>> user.pk
>>> user = User.objects.get(id=1)                             
>>> user.name
>>> Post.objects.all()                                     
>>> post_1 = Post(title='Blog 1', content='First post content!', author=user)
>>> Post.objects.all()
>>> post_1.save()
>>> Post.objects.all()
>>> exit()

>>> from blog.models import Post
>>> from django.contrib.auth.models import User
>>> Post.objects.all()
>>> user = User.objects.filter(username='linkesh').first()
>>> post_1 = Post(title='Blog 2', content='Second post content!', author_id=user.id)
>>> post_1.save() 
>>> Post.objects.all()
>>> post = Post.objects.first()
>>> post.content
>>> post.date_posted
>>> post.author
>>> post.author.email
>>> user.post_set.all()
>>> user.post_set.create(title='Blog 1', content='Third post content!')                  
>>> Post.objects.all()
>>> exit()


User Registration:
python manage.py startapp users - This will create folder "users" and py files in MyBlogProject
add 'users.apps.UsersConfig' in settings.py
add forms.py and inherit UserCreationForm in users app
create register.html in users apps /templates/users
add 'register' method in views.py
in project urls.py add path("register/", user_views.register, name="register")
in base.html add messages loop
add CRISPY_TEMPLATE_PACK = 'bootstrap4' in settings.py
add 'crispy_forms' in settings.py


Login/Logout:
https://github.com/linkeshkanna/Django.Web.APIs/commit/3e5e2c3e04977a3b8ab92c7f77ebb86bcf2360ce




