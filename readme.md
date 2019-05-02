# Python3 Django Docker Postgres

This is a simple pre-setup of Django, Docker, Docker Compose, and Postgres running together.
This is mostly so I can copy paste the container and docker-compose file and have a running app
on Windows/Linux without hassle.

Note you'll want to rename/change the `./code` directory and the reference in the docker-compose for your app.

The `./code` directory is removed. If you want to test this works then follow the docs here: https://docs.docker.com/compose/django/

*Docker login note* -- use ID _not_ email.

1. `docker-compose run web django-admin startproject sample_app .`
1. On windows wait for popup to "share" the drive
1. Replace the db in settings with: 
    ```py
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'postgres',
            'USER': 'postgres',
            'HOST': 'db',
            'PORT': 5432,
        }
    }
    ```
1. Run `docker-compose up` to start the service running
1. See it at `http://localhost:8000`
