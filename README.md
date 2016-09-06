# How-to use this Dockerfile
## With MySQL

```
$ # Launch the MySQL DB
$ docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=password mysql
$ # Launch the FreshRSS container
$ docker run -d --name freshrss --link mysql:db -p 8080:80 kokaz/freshrss:latest
```

During the installation phase in the MySQL configuration put that:

* Host: `db`
* Username: `root`
* Password: `password`

## Without MySQL

```
$ # Launch the FreshRSS container
$ docker run -d --name freshrss -p 8080:80 kokaz/freshrss:latest
```

## Building the docker image

```
$ docker build -t kokaz/freshrss .
```

