
## tutorial for django 1.10

### 01. setup .gitignore and requirements.txt

    echo "*.py[cod]" > .gitignore
    echo "Django==1.10" > requirements.txt

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
