# Guide to deploy Conjur OSS on MacOS with Apple Silicon 

To run Conjur OSS on Docker on MacOS with Apple Silicon, we can simply add `platform: linux/amd64` option

```
  conjur:
    image: cyberark/conjur
    platform: linux/amd64
    container_name: conjur_server
    command: server
    environment:
      DATABASE_URL: postgres://postgres@database/postgres
      CONJUR_DATA_KEY:
      CONJUR_AUTHENTICATORS:
    depends_on:
    - database
    restart: on-failure
    ports:
      - 8080:80
```
see [docker-compose.yml](https://github.com/quincycheng/conjur-on-mac/blob/main/docker-compose.yml) for complete sample
