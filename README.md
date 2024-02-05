
# Pizzato infrastructure project

This project is the docker side of a web application named Pizzato.
Pizzato is a Django-based web application where you can make your custom pizza using different ingredients.
## Logo
![Logo](https://i.postimg.cc/W3tLsDVQ/res-logo.png)

## Deployment

> To run all services of this projcet clone back, front and Infrastructure together and put back and front project in infrastructure project.
> Back: https://github.com/shalchianmh/web_backend \
> Front: https://github.com/shalchianmh/Infrastructure \
> infrastructure: https://github.com/Ali-Sadeghi-Gh/web-project-front 

To deploy this project after cloning it from Git Hub(you shuold clone web_backend and web-project-front separately), you must build docker images and run them. Since we use `docker-compose`.
you can just run the below instruction to run all the project services together:

```bash
  docker-compose up -d --build
```
This will build all needed images and then run them, but if you want you can simply first build and then run:
```bash
  docker-compose build
  docker-compose up -d
```
The `-d` flag stands for "detached" mode.
When you use `docker-compose up -d`,
it instructs Docker Compose to start the services defined in your docker-compose.yml file in the background, allowing you to continue using your terminal for other commands without being attached to the container logs.

## Migrations
Using this command you can migrate, but note that you just need to do it in the first run, because we used `volume` to keep database data even after stopping and removing images.
```bash
docker-compose exec web python manage.py migrate --noinput
```
## Admin
You can create admins with this command for django app:
```bash
docker-compose exec web python manage.py createsuperuser
```
Thanks to docker-compose you can access and run commands in each service using `docker-compose exec [service-name] [your command]`.

## Tech Stack

docker, docker-compose, postgres, Django, Django REST framework(drf), React, Nginx




## Authors

- [@Ali Banayeean](https://www.github.com/Alibanayeean)
- [@Ali Sadeghi](https://www.github.com/Ali-Sadeghi-Gh)
- [@Mohammad Hossein Shalchian](https://www.github.com/shalchianmh)



