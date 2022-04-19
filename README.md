
# Table of Contents

1.  [Set up the project](#org3193b47)
2.  [first Django app](#orgfe27993)
    1.  [create a project](#orge0a8116)
    2.  [run dev server](#org528dc86)
    3.  [create an app](#org971bb42)
3.  [&#x2026;continue](#org9adfd7d)
    1.  [some notes](#org61e3ed9)
4.  [playing with the API](#orgba8c44c)
5.  [site admin](#orgdf4e4cf)



<a id="org3193b47"></a>

# Set up the project

1.  create a repository on **GitHub** then it suggests the follow commands
    
        echo "# django_zth" >> README.md
        git init
        git add README.md
        git commit -m "first commit"
        git branch -M main
        git remote add origin https://github.com/littl3-R/django_zth.git
        git push -u origin main
2.  install `pip`
3.  create a new environment [pyenv](https://realpython.com/intro-to-pyenv/) and activate it
    
    1.  new enviroment
    
        pyenv install --list # choose the python version e.g. pyenv install 3.10.2 
    
        pyenv virtualenv 3.10.2 django-virtual-enviroment
4.  create a `.gitignore`
    
        # Byte-compiled / optimized / DLL files
        __pycache__/
        *.py[cod]
        *$py.class
        
        # C extensions
        *.so
        
        # Distribution / packaging
        .Python
        build/
        develop-eggs/
        dist/
        downloads/
        eggs/
        .eggs/
        lib/
        lib64/
        parts/
        sdist/
        var/
        wheels/
        pip-wheel-metadata/
        share/python-wheels/
        *.egg-info/
        .installed.cfg
        *.egg
        MANIFEST
        
        # PyInstaller
        #  Usually these files are written by a python script from a template
        #  before PyInstaller builds the exe, so as to inject date/other infos into it.
        *.manifest
        *.spec
        
        # Installer logs
        pip-log.txt
        pip-delete-this-directory.txt
        
        # Unit test / coverage reports
        htmlcov/
        .tox/
        .nox/
        .coverage
        .coverage.*
        .cache
        nosetests.xml
        coverage.xml
        *.cover
        *.py,cover
        .hypothesis/
        .pytest_cache/
        
        # Translations
        *.mo
        *.pot
        
        # Django stuff:
        *.log
        local_settings.py
        db.sqlite3
        db.sqlite3-journal
        
        # Flask stuff:
        instance/
        .webassets-cache
        
        # Scrapy stuff:
        .scrapy
        
        # Sphinx documentation
        docs/_build/
        
        # PyBuilder
        target/
        
        # Jupyter Notebook
        .ipynb_checkpoints
        
        # IPython
        profile_default/
        ipython_config.py
        
        # pyenv
        .python-version
        
        # pipenv
        #   According to pypa/pipenv#598, it is recommended to include Pipfile.lock in version control.
        #   However, in case of collaboration, if having platform-specific dependencies or dependencies
        #   having no cross-platform support, pipenv may install dependencies that don't work, or not
        #   install all needed dependencies.
        #Pipfile.lock
        
        # PEP 582; used by e.g. github.com/David-OConnor/pyflow
        __pypackages__/
        
        # Celery stuff
        celerybeat-schedule
        celerybeat.pid
        
        # SageMath parsed files
        *.sage.py
        
        # Environments
        .env
        .venv
        env/
        venv/
        ENV/
        env.bak/
        venv.bak/
        
        # Spyder project settings
        .spyderproject
        .spyproject
        
        # Rope project settings
        .ropeproject
        
        # mkdocs documentation
        /site
        
        # mypy
        .mypy_cache/
        .dmypy.json
        dmypy.json
        
        # Pyre type checker
        .pyre/
        
        # Compiled
        *.elc
        
        # Packaging
        .cask
        
        # Backup files
        *~
        
        # Undo-tree save-files
        *.~undo-tree
5.  commits and push
    1.  `C-x g` follow the instructions create first repository, new
        buffer will be open
    2.  **stage** and **commits**
        1.  `S`
        2.  `c` `c`
        3.  `C-c C-c`
    3.  rename the branch in **main**
    4.  add the remote branch:
        1.  `M`
        2.  `a`
        3.  `origin`
        4.  <https://github.com/littl3-R/django_zth.git>
        5.  `y`
    5.  push
        1.  `P`
        2.  `p`
        3.  insert password
6.  install **django** and check if it works
    
        python -m pip install Django
    
        python
        import django
        print(django.get_version())


<a id="orgfe27993"></a>

# first Django app


<a id="orge0a8116"></a>

## create a project

    django-admin startproject mysite

    tree ./mysite/

The `__init__.py` file tells to django that this is a [package in python](https://docs.python.org/3/tutorial/modules.html#tut-packages)


<a id="org528dc86"></a>

## run dev server

    python mysite/manage.py runserver # you can run in .org too


<a id="org971bb42"></a>

## create an app

    cd mysite
    python manage.py startapp polls

    tree ./mysite/polls/


<a id="org9adfd7d"></a>

# &#x2026;continue

The project and the first app are set them up, form now I'll write the
files directly instead editing the .org


<a id="org61e3ed9"></a>

## some notes

The `include()` function allows referencing the URLconfs.

The migrate command looks at the **INSTALLED<sub>APPS</sub>** setting and creates
any necessary database tables according to the database settings in
your mysite/settings.py

Once you have create or updated the `models.py` and `migrate` you have
to add the new app in django. See the `polls/apps.py`

This command is helpful:

    python mysite/manage.py check

this checks for any problems in the project


<a id="orgba8c44c"></a>

# playing with the API

    python mysite/manage.py shell

    >>> from polls.models import Question, Choice
    >>> Question.objects.all()
    >>> Question.objects.all()
    <QuerySet []>
    >>> from django.utils import timezone
    >>> timezone.now()
    datetime.datetime(2022, 4, 19, 16, 35, 38, 486045, tzinfo=datetime.timezone.utc)
    >>> q = Question(question_text="What's new?", pub_date=timezone.now())
    >>> q
    <Question: Question object (None)>
    >>> q.save()
    >>> q
    <Question: Question object (1)>
    >>> q.id
    1
    >>> q.pub_date
    datetime.datetime(2022, 4, 19, 16, 36, 13, 941778, tzinfo=datetime.timezone.utc)
    >>> q.question_text
    "What's new?"
    >>> q.question_text = "What's up?"
    >>> q.save()
    >>> Questio.objects.all()
    Traceback (most recent call last):
      File "<console>", line 1, in <module>
    NameError: name 'Questio' is not defined
    >>> Questions.objects.all()
    Traceback (most recent call last):
      File "<console>", line 1, in <module>
    NameError: name 'Questions' is not defined
    >>> Question.objects.all()
    <QuerySet [<Question: Question object (1)>]>
    >>>


<a id="orgdf4e4cf"></a>

# site admin

    python manage.py createsuperuser

