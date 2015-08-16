# Supported tags and respective `Dockerfile` links

-	[`5.6.12`, `5.6`, `5`, `latest` (*5.6/Dockerfile*)](https://github.com/srod/docker-apache-php/blob/master/5.6/Dockerfile)

# About this image?

This image come from the official [Docker php image](https://hub.docker.com/_/php/)

It was builded with the apache version with mod_rewrite and mysqli php extension.

And also with a `date.timezone = Europe/Paris`

![logo](https://raw.githubusercontent.com/docker-library/docs/master/php/logo.png)

# How to use this image

## Start a `apache` server instance with a Dockerfile

### Create a `Dockerfile` in your PHP project

```dockerfile
FROM srod/apache-php
COPY src/ /var/www/html/
```

Where `src/` is the directory containing all your php code. Then, run the commands to build and run the Docker image:

```console
$ docker build -t my-php-app .
$ docker run -it --rm --name my-running-app my-php-app
```

## Start a `apache` server instance with Docker Compose

### Create a `docker-compose.yml` in your PHP project

```dockerfile
web:
  image: srod/apache-php
  ports:
    - "8080:80"
  volumes:
    - "./src:/var/www/html"
```

Where `src/` is the directory containing all your php code. Then, run `docker-compose`:

```console
$ docker-compose up
```
