## Djando with PostgreSQL using Docker

### The idea of this project is can init of the easy way and quickly a project right from the start using as database engine PostgreSQL.
### The arrangement of folders and the way as create the project may vary depend of needs.

Steps
---

##### Step 1: Build the image and create proyect in the container
    sudo docker-compose run web django-admin startproject <proyect_name> .

##### Step 2: Run the containers
    docker-compose up -d

##### Step 3: Migrate Data Base
    docker-compose exec web python manage.py migrate --noinput

How to
---

##### Create super user
    docker-compose exec web python manage.py createsuperuser

##### Stop containers
    docker-compose stop
