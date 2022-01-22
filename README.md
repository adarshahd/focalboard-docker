focalboard Docker images [![Docker buildx CI](https://github.com/araven/focalboard-docker/actions/workflows/build.yml/badge.svg)](https://github.com/araven/focalboard-docker/actions/workflows/build.yml)
=========================

Cross platform Docker images for [focalboard](https://www.focalboard.com).

Usage
-----

### docker

```
docker run -p 8000:8000 nicoulaj/focalboard
```

### docker-compose

* `config.json`:

    ```
    {
        ["serverRoot": "http://focalboard.home",]
        "port": 8000,
        "dbtype": "sqlite3",
        "dbconfig": "/var/lib/focalboard/focalboard.db",
        "postgres_dbconfig": "dbname=focalboard sslmode=disable",
        "useSSL": false,
        "webpath": "./pack",
        "filespath": "/var/lib/focalboard/files",
        "telemetry": false,
        "session_expire_time": 2592000,
        "session_refresh_time": 18000,
        "localOnly": false,
        "enableLocalMode": true,
        "localModeSocketLocation": "/var/tmp/focalboard_local.socket"
    }
    ```

* `docker-compose.yml`:

    ```
    services:
      focalboard:
        image: araven/focalboard
        volumes:
        - ./config.json:/opt/focalboard/config.json
        - /var/lib/focalboard:/var/lib/focalboard
    ```
