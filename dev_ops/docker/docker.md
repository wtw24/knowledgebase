# Docker

## Links:
 - [Шпаргалки по безопасности: Docker](https://habr.com/ru/company/acribia/blog/448704)

### Docker Exec as Root
~~~
docker exec -u 0 <container> <command>
~~~

### Docker Compose Exec as Root
~~~
docker-compose exec -u 0 <container> <command>
~~~

### Docker Run
~~~
docker run -it ubuntu:18.04 bash
~~~

### Docker Compose Run
~~~
docker-compose run --rm -p 8080:8080 node-cli npm run serve
~~~