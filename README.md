## Djando with PostgreSQL using Docker

#### The idea of this project is can init of the easy way and quickly a project right from the start using as database engine PostgreSQL.
#### The arrangement of folders and the way as create the project may vary depend of needs.

Steps
---

##### Step 1: Build the image and create proyect in the container
    sudo docker-compose run web django-admin startproject <proyect_name> .

##### Step 2: Change the ownership of the new files.
    sudo chown -R $USER:$USER .

##### Step 3: Connect the database.
In this section, you set up the database connection for Django.

In your project directory, edit the settings.py file.
    
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'testing',
            'USER': 'postgres',
            'HOST': 'db',
            'PASSWORD': 'postgres',
            'PORT': 5432,
        }
    }

##### Step 4: Run the containers
    docker-compose up -d

##### Step 5: Migrate Data Base
    docker-compose exec web python manage.py migrate --noinput

How to
---

##### Create super user
    docker-compose exec web python manage.py createsuperuser

##### Stop containers
    docker-compose stop
