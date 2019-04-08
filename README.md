# docker-php-apache
Docker repository for PHP environment of Pilulka projects.

There is posibility to run initial scripts which are located in `/init.d`

*Example*
File: _echo.sh_

```bash
#!/bin/bash
echo "Hello World!"
```

with `docker-compose.yml`

```txt
version: '3'
services:
  web:
    build: .
    volumes:
      - ./echo.sh:/init.d/echo.sh
    ports:
      - 8080:80
      - 8443:443
```

Will produce `Hello World!` on container start.

*Where to use it?*

- enable some services on container start (e.g. `supervisor`)
- run some custom scripts on container build
- ...
