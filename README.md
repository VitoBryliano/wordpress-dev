# WordPress for development

Docker for quick start project in WordPress


## Commands Docker

- Run project WordPress with Docker
```bash
  docker compose up
  # where [-d] is run in background
  # where [--build] is build image
```

- Stop project WordPress with Docker:
```bash
  docker compose down
  # [-v] is remove volume (database data)
```

- Restart project WordPress with Docker:
```bash
  docker compose restart
```


## Variables environment

1. Create file `.env` in root project
```bash
  cp .env.example .env
```
1. Edit file `.env` with your configuration
2. Restart project WordPress with Docker
3. Access [http://localhost](http://localhost) in browser
4. Install WordPress with your configuration
5. Enjoy!


## Docker images

- wordpress:6.6.2-php8.1
- mariadb:10.7.8-focal
- phpmyadmin/phpmyadmin
- axllent/mailpit:latest


## Ports

- [WordPress](http://localhost/): 80
- [phpMyAdmin](http://localhost:3307/): 3307
- MariaDB: 3306 - you can use any client to connect to the database
- [Mailpit](http://localhost:8025/): 8025
