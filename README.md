# Live!Zilla - Docker Image

This is a unofficial Live!Zilla Docker image created to support Cloud Native way of deploying a Live!Zilla server

This project is only a wrapper of the actual product and maintains the though alread easy deployment of Live!Zilla - and i don't provide any support etc.

To fint the actual project you can visit the [Live!Zilla website](https://www.livezilla.net)

Please don't use this in production - since its only for testing at the moment.

## Supported features

* Base installation - and auto fetch of current / specific version
* SSL Deployment

## Dependencies

* Docker installed and running
* MySQL Server running

## Running the Container

I have provided a Docker Compose file which gets the current MariaDB Database and installs this as well

When the container starts the first time it checks if there is an installation of LiveZilla in /var/www/html if not it will install the version of the current docker file.

Example
```
docker run -d --name livezilla \
 -p 8080:80 \
 -v /opt/livezilla:/var/www/html \
 zenturacp/livezilla-docker:latest
```

Now you can access the site on http://\<ip\>:8080

To troubleshoot check the logs

```
docker logs livezilla
```

## Docker Compose

There is also a Docker Compose deployment you can run with

```
docker-compose up -d
```

Please change the MySQL root password before deployment

## Static Volumes

```
/var/www/html
```

## Roadmap

* Build in CronJob