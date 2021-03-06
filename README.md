![logo](logo.png)

# Docker Registry Compose File

## About

This docker compose file starts the docker [registry](https://hub.docker.com/_/registry/) to listen on
the port `5000`. It also starts a [web ui](https://github.com/klausmeyer/docker-registry-browser)
 to browse the registry on port `5001`. The registry is started as insecure so you will need
to modify your clients to support your host as an insecure registry. The storage of the registry will
be put in a data folder relative to the compose file. If you want to change the storage folder you
will have to edit the `docker-compose.yml` file.

*Note:* The data will be stored with `root` as the owner.

## Starting

```
$ docker-compose up
```

## Setting up the clients

* *Linux* https://docs.docker.com/registry/insecure/#/deploying-a-plain-http-registry
* *Docker for Mac* https://docs.docker.com/docker-for-mac/#/advanced

## Pushing
```
$ docker tag hello-world <my registry host>:5000/hello-world
$ docker push <my registry host>:5000/hello-world
```

## Running
```
$ docker run <my registry host>:5000/hello-world
```

