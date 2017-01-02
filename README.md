
## tutorial for django 1.10

### 01. setup .gitignore and requirements.txt

    echo "*.py[cod]" > .gitignore
    echo "Django==1.10.4" > requirements.txt

### 01.1.special use of 'git tags'

    git log --oneline
    git tag Stage-01 f8c77e6
    git push --tags

### 02. build a virtual environment

    # make a new cloud9 workspace 
    #   name it tutorial
    #   cloned from git@github.com:5SA/tutorial.git
    #   select Blank template
    sudo pip install virtualenv   # admin auth
    virtualenv $HOME/.env
    source $HOME/.env/bin/activate
    # before pip set export HTTPS_PROXY=http://username:pass@proxyaddress:port
    pip install -r requirements.txt

### 03. creating a project and verify ...

    django-admin startproject mysite
    cd mysite
    python manage.py runserver $IP:$PORT
    # firefox https://tutorial-sdoro.c9users.io

### 04. creating the Polls app

    python manage.py startapp polls

### 05. write your first view

    # edit polls/views.py
    # create polls/urls.py
    # edit mysite/urls.py
    python manage.py runserver $IP:$PORT
    # firefox https://tutorial-sdoro.c9users.io/polls/

### 06. database setup

    # edit mysite/settings.py
    python manage.py migrate
    # edit polls/models.py

### 07. activating models

    # edit mysite/settings.py
    python manage.py makemigrations polls
    python manage.py sqlmigrate polls 0001
    python manage.py migrate

### 08. playing with the API

    # python manage.py shell
    # edit polls/models.py

### 09. creating an admin user

    python manage.py createsuperuser
    # Username: admin
    # Email address: admin@example.com
    # Password: not24get
    # Password (again): not24get

### 10. make the poll app modifiable in the admin

    # edit polls/admin.py
    python manage.py runserver $IP:$PORT
    # firefox https://tutorial-sdoro.c9users.io/admin

### 11. writing more views

    # edit polls/views.py
    # edit polls/urls.py

### 12. write views that actually do something

    # edit polls/views.py
    mkdir -p polls/templates/polls
    > polls/templates/polls/index.html
    # edit polls/templates/polls/index.html
    # edit polls/views.py

### 13. a shortcut: render() & Raising a 404 error

    # edit polls/views.py
    > polls/templates/polls/detail.html
    # edit polls/templates/polls/detail.html

### 14. a shortcut: get_object_or_404()

    # edit polls/views.py

### 15. use the template system

    # edit polls/templates/polls/detail.html

### 16. removing hardcoded URLs in templates

    # edit polls/templates/polls/index.html

### 17. namespacing URL names

    # edit polls/templates/polls/index.html
    # edit polls/urls.py

### 18. write a simple form

    # edit polls/templates/polls/detail.html
    # edit polls/views.py
    > polls/templates/polls/results.html
    # edit polls/templates/polls/results.html
    # edit polls.admin
    # warning: remember to add some Choices ;)

### 19. use generic views: Less code is better

    # edit polls/urls.py
    # edit polls/views.py

### 20. create a test to expose the bug

    > polls/tests.py
    # edit polls/tests.py
    python manage.py test polls

### 21. fixing the bug

    # edit polls/models.py
    python manage.py test polls

### 22. more comprehensive tests

    # edit polls/tests.py
    python manage.py test polls

### 23. improving our view

    # edit polls/views.py
    # edit polls/tests.py
    python manage.py test polls

### 24. customize your app’s look and feel

    mkdir polls/static/polls
    > polls/static/polls/style.css
    # edit polls/static/polls/style.css

### 25. adding a background-image

    # edit polls/static/polls/style.css
    mkdir -p polls/static/polls/images/
    # get LineageOS image into polls/static/polls/images/background.png

### 26. customize the admin form (1/2)

    # edit polls/admin.py

### 27. customize the admin form (2/2)

    # edit polls/admin.py

### 28. adding related objects (1/2)

    # edit polls/admin.py
