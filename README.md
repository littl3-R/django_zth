
# Table of Contents

1.  [Set it up the project](#orga952b0e)



<a id="orga952b0e"></a>

# Set it up the project

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

