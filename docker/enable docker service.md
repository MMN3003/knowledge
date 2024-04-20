If your `docker.service` enabled on system startup

```yaml
$ sudo systemctl enable docker
```

and your services in your `docker-compose.yml` has

```yaml
restart: always
```

all of the services run when you reboot your system if you run below command only once

```yaml
docker compose up -d
```